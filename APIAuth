public static void connect(String host, int port, String apiKeyId, String apiKeySecret)
{
  String apiKeyAuth = Base64.getEncoder().encodeToString((apiKeyId + ":" + apiKeySecret).getBytes(StandardCharsets.UTF_8));

  Header[] defaultHeaders = new Header[]
  {
    new BasicHeader("Authorization", "ApiKey " + apiKeyAuth)
  };

  RestClientBuilder restClientBuilder = RestClient.builder(new HttpHost(host, port, "https"));

  RestClient restClient = restClientBuilder.setDefaultHeaders(defaultHeaders).build();

  ElasticsearchTransport transport = new RestClientTransport(restClient, new JacksonJsonpMapper());

  ElasticsearchClient client = new ElasticsearchClient(_transport);
}
