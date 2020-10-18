# API Design  
API design is the collection of planning and architectural decisions you make when building an API. Your basic API design influences how well developers are able to consume it and even how they use it. Just like website design or product design, API design informs the user experience. Good API design principles meet initial expectations and continue to behave consistently and predictably.  

There is not a single approach on how to design a API or even how to design good APIs “the right way.” Instead, we need to lean on good industry basic API design guidelines, best practices and patterns where relevant, then take cues from those who will use our APIs.  

## Prerequisites  
* HTTP  
* JSON  
* YAML  
* ACL  

## Key Terms  
### Pagination  
When a network request potentially warrants a really large response, the relevant API might be designed to return only a single **page** of that response (i.e., a limited portion of the response), accompanied by an identifier or token for the client to request the next page if desired.  

Pagination is often used when designing **List** endpoints. For instance, an endpoint to list videos on the YouTube Trending page could return a huge list of videos. This wouldn't perform very well on mobile devices due to the lower network speeds and simply wouldn't be optimal, since most users will only ever scroll through the first ten or twenty videos. So, the API could be designed to respond with only the first few videos of that list; in this case, we would say that the API response is **paginated**.  

### CRUD Operations  
Stands for **Create, Read, Update, Delete** Operations. These four operations often serve as the bedrock of a functioning system and therefore find themselves at the core of many APIs. The term **CRUD** is common in API design.
