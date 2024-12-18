---
id: saaj1uvy4pbswbl4i4f7zac
title: '2024-11-26'
desc: ''
updated: 1732637366822
created: 1732637359512
traitIds:
  - journalNote
---

## Morning

<!-- Morning Tasks -->

What I need to do today:

1. item
2. item

### Morning Tasks

- [ ] task
- [ ] task

## Afternoon

What needs done this afternoon:

1. item
2. item

### Afternoon Tasks

- [ ] task
- [ ] task

### Last thing

What needs to carry over:

1. item or task
2. item or task

### How could I have made today even better?

I could have made today better by


    @Bean
    public PlatformRestClient nextGenPlatformRestClient(
            ResponseErrorHandler responseErrorHandler,
            CorrelationIdRequestInterceptor correlationIdRequestInterceptor,
            CloseableHttpClient httpClient) {
        HttpComponentsClientHttpRequestFactory factory  = new HttpComponentsClientHttpRequestFactory(httpClient);

        ClientHttpRequestFactory httpRequestFactory =
                PropertiesHttpRequestFactory.builder()
                        .httpRequestFactory(factory)
                        .services(services)
                        .build();

        var restClient = RestClient.builder()
                .requestFactory(httpRequestFactory)
                .requestInterceptors(interceptors -> interceptors.add(correlationIdRequestInterceptor))
                .defaultStatusHandler(responseErrorHandler)
                .build();

        return new NextGenPlatformRestClient(restClient);
    }
