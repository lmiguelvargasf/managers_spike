# Managers Spike

The purpose of this "project" is to play around with Django's [Managers][managers].

## Managers

### What is a Manager?

In a Django model, a manager is the interface that interacts with the database.
I have provided [an answer][answer] on StackOverflow with further explanations.

### Custom managers

You can use a custom Manager in a particular model by extending the base Manager class and instantiating your custom Manager in your model.

#### Custom manager overrides default manager

I have implemented a custom manager to override the default `Manager`
which can be accessed throught `Model.objects`. ([see logic][custom-manager])

#### Custom manager and default manager

It is possible to have multiple managers for the same model.
I have implemented two custom managers besides the default manager. ([see logic][multiple-managers])

The problem with the previous two approaches is that it is not possible to chain
the methods defined in the managers.

#### Custom manager and queryset

If you want to chain methods defined in managers, you should define a custom `QuerySet`.
([see logic][custom-queryset-manager])

#### Custom queryset used as manager

When defining just custom querysets in the manager, it is possible to simply extend the queryset
and set it as the manager. ([see logic][query-set-as-manager])

[answer]: https://stackoverflow.com/questions/14689237/what-is-a-manager-in-django/63095697#63095697
[custom-manager]: ./foo/models/document.py
[custom-queryset-manager]: ./foo/models/author.py
[managers]: https://docs.djangoproject.com/en/dev/topics/db/managers/
[multiple-managers]: ./foo/models/book.py
[query-set-as-manager]: ./foo/models/publisher.py
