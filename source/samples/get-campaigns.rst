
.. code-block:: bash

    curl -s --user 'api:YOUR_API_KEY' -G \
	https://api.mailgun.net/v3/YOUR_DOMAIN_NAME/campaigns

.. code-block:: java

 public static ClientResponse GetCampaigns() {
 	Client client = new Client();
 	client.addFilter(new HTTPBasicAuthFilter("api",
 			"YOUR_API_KEY"));
 	WebResource webResource =
 		client.resource("https://api.mailgun.net/v3/YOUR_DOMAIN_NAME/campaigns");
 	MultivaluedMapImpl queryParams = new MultivaluedMapImpl();
 	queryParams.add("limit", 2);
 	return webResource.queryParams(queryParams).get(ClientResponse.class);
 }

.. code-block:: php

  # Include the Autoloader (see "Libraries" for install instructions)
  require 'vendor/autoload.php';
  use Mailgun\Mailgun;

  # Instantiate the client.
  $mgClient = new Mailgun('YOUR_API_KEY');
  $domain = 'YOUR_DOMAIN_NAME';

  # Issue the call to the client.
  $result = $mgClient->get("$domain/campaigns", array('limit' => 5, 'skip' => 5));

.. code-block:: py

 def get_campaigns():
     return requests.get(
         "https://api.mailgun.net/v3/YOUR_DOMAIN_NAME/campaigns",
         auth=('api', 'YOUR_API_KEY'))

.. code-block:: rb

 def get_campaigns
   RestClient.get("https://api:YOUR_API_KEY"\
                  "@api.mailgun.net/v3/YOUR_DOMAIN_NAME/campaigns")
 end

.. code-block:: csharp

 public static IRestResponse GetCampaigns() {
     RestClient client = new RestClient();
     client.BaseUrl = new Uri("https://api.mailgun.net/v3");
     client.Authenticator =
	new HttpBasicAuthenticator("api",
	                           "YOUR_API_KEY");
     RestRequest request = new RestRequest();
     request.AddParameter("domain",
                           "YOUR_DOMAIN_NAME", ParameterType.UrlSegment);
     request.Resource = "{domain}/campaigns";
     request.AddParameter("limit", 2);
     return client.Execute(request);
 }


.. code-block:: go

 // Not supported

