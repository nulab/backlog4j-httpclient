# backlog4j-httpclient

## What is this?
It enables using Backlog4J with Java11 or later by providing an implementation of `com.nulabinc.backlog4j.http.BacklogHttpClient` using `java.net.http.HttpClient`.
(The HTTP PATCH method is not available in Java 9 or later for Backlog4J)

## Requirements
Java11 or later

## Getting started
1. Add a dependency to Backlog4J 2.5.1 or later to your project.
2. Create a instance of `com.nulabinc.backlog4j.BacklogClient` using `java.net.http.HttpClient` and `com.nulabinc.backlog4j.http.httpclient.HttpClientBacklogHttpClient` like below.
````
// Congigure
BacklogConfigure configure = ...;

// Create a builder instance to create the instance of HttpClient.
HttpClient.Builder httpClientBuilder = HttpClient.newBuilder(); 

// Use HttpClientBacklogHttpClient as an implementation of BacklogHttpClient.
BacklogHttpClient backlogHttpClient = new HttpClientBacklogHttpClient(httpClientBuilder);

// Create an instance of BacklogClient using the factory.
BacklogClient backlogClient = new BacklogClientFactory(configure, backlogHttpClient).newClient();
````
3. After that, you can access the Backlog4J API via the BacklogClient instance.
