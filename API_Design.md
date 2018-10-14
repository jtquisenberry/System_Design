# API Design

## API Domain Modeling Examples
1. Refer to the object being acted on: `users`, `statuses`, `friendships`.
2. If GET, the state what is being retrieved `list`, `ids`, `id:1`
3. If POST, state the operation. `create`, `destroy`, `update`.
4. Use a common interface - singular or plural nouns. Consistent verbs.
5. Maybe include a version number.
<br> Examples from Twitter: https://developer.twitter.com/en/docs/api-reference-index.html
6. url.com/api/v1/users/create

## Naming
* Spend some time thinking about naming upfront.
* https://www.interviewcake.com/question/csharp/url-shortener?section=system-design&course=fc1
  * ShortLink
    * slug
    * destination

## Naming Conventions
* Refer to RFCs


## C#
* https://stackoverflow.com/questions/2005367/getting-full-url-of-action-in-asp-net-mvc
* Controller, action, data
* Url.Action("Action", null, null, Request.Url.Scheme);
