# Notes about '[Designing Web APIs: Building APIs That Developers Love](https://www.goodreads.com/book/show/38396693-designing-web-apis)'

If your goal is to build web API for customers and you don't know where to start, what tech to choose, this book provides a good overview of principles, tech with pros and cons.

Things that the book touches on:
* Request-Response paradigm, REST vs RPC vs GraphQL
* Event-driven APIs, WebHooks vs WebSockets vs HTTP Streaming
* API security, OAuth2.0
* Steps to create API design specification
* Things to consider when scaling API

## Design Best Practices

1. Define real-life use cases. Think about devs who are using your API. What tasks should they be able to complete with your API? 
2. Make sure devs can actually do things you want them to do using your API.
3. Make sure that devs understand your API. Make it simple and concise, provide documentation.
4. You want your API to be intuitively consistent. The same resource should not hold different names when using different API endpoints.The consistency is important because it reduces the cognitive load on devs who are trying to figure out how to use your API.
5. Make troubleshooting easy. Return meaningful error messages and error codes that help devs understand the reason of failure. You can check all your API endpoints for possible response errors so you can categorize them and decide which should be exposed to devs.
6. (Optional) Consider using analytics platforms.
7. Consider giving pre-release API version to trusted devs for testing to get feedback on usability.
8. Consider versioning your API.

## Design in Practice

1. Define business objectives. Answer these questions: what problems are you trying to solve and what is the impact you want to have by building this API?
2. Outline key user stories. Write down some use cases ("user stories") your API is supposed to fulfill.\
Example:
```Markdown
As a [user type], I want [action] so that [outcome].
```
3. Select technology architecture. Choose the paradigm for the API you want to create (REST, RPC, GraphQL, WebHooks etc.). Choose authentication system.
4. Write an API specification.
5. Validate your decisions. Review your specification with stakeholders. Mocking your data to create a testing environment could be a good thing. Before official release you can start a beta program to gather valuable feedback from external parties.

## Pagination
Two ways to do it:
1. Offset-based\
Pros:
    * Very simple to implement;
    * You can go to desired page.
Cons:
    * Inefficient for lagre datasets;
    * Can be unreliable when a list of items changes frequently;
    * Can be tricky in distributes systems (you might need to scan multiple shards to get the desired set of items).
2. Cursor-based
Pros:
    * Good performance;
    * Addition or removal of items does not affect result set.
Cons:
    * You cannot jump to desired page;
    * The results must be sorted on a unique and sequential database column.

## Versioning
Strategies for handling versioning:
1. Additive-change;
2. Explicit-version.

## A good API...
* Solves an actual developer need or pain point;
* Is consistent;
* Is stable;
* Is thoroughly documented;
* Does not have breaking changes;
* Has reasonable rate limits;
* Follows standards;
* Is reliable and secure;
* Has a great community and support;
* Has sample code;
*  Is easy to understand and use;
*  Has a good SDK, in multiple languages;
*  Is easy to test.