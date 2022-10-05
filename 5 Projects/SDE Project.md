# Documentation
## 2.5.2. Query operators

-   `ne` – not equal to
    
-   `lt` – less than
    
-   `lte` – less than or equal to
    
-   `gt` – greater than
    
-   `gte` – greater than or equal to
    
-   `not` – negate a standard check, may be used before other operators (e.g. `Q(age__not__mod=(5, 0))`)
    
-   `in` – value is in list (a list of values should be provided)
    
-   `nin` – value is not in list (a list of values should be provided)
    
-   `mod` – `value % x == y`, where `x` and `y` are two provided values
    
-   `all` – every item in list of values provided is in array
    
-   `size` – the size of the array is
    
-   `exists` – value for field exists

### 2.5.2.1. String queries[link](https://mongoengine-odm.readthedocs.io/guide/querying.html#string-queries "Permalink to this headline")

The following operators are available as shortcuts to querying with regular expressions:

-   `exact` – string field exactly matches value
    
-   `iexact` – string field exactly matches value (case insensitive)
    
-   `contains` – string field contains value
    
-   `icontains` – string field contains value (case insensitive)
    
-   `startswith` – string field starts with value
    
-   `istartswith` – string field starts with value (case insensitive)
    
-   `endswith` – string field ends with value
    
-   `iendswith` – string field ends with value (case insensitive)
    
-   `wholeword` – string field contains whole word
    
-   `iwholeword` – string field contains whole word (case insensitive)
    
-   `regex` – string field match by regex
    
-   `iregex` – string field match by regex (case insensitive)
    
-   `match` – performs an $elemMatch so you can match an entire document within an array



```python
# This will return a QuerySet that will only iterate over pages that have
# been written by a user whose 'country' field is set to 'uk'
uk_pages = Page.objects(author__country='uk')
```


### Querying lists

```python
class Page(Document):
    tags = ListField(StringField())

# This will match all pages that have the word 'coding' as an item in the
# 'tags' list
Page.objects(tags='coding')

Page.objects(tags__0='db')

# comments - skip 5, limit 10
Page.objects.fields(slice__comments=[5, 10])
```

## Sorting/Ordering results

```python
# Order by ascending date
blogs = BlogPost.objects().order_by('date')    # equivalent to .order_by('+date')

# Order by ascending date first, then descending title
blogs = BlogPost.objects().order_by('+date', '-title')
```

## Limiting and skipping results
```python

# Only the first 5 people
users = User.objects[:5]

# All except for the first 5 people
users = User.objects[5:]

# 5 users, starting from the 11th user found
users = User.objects[10:15]
```

### Further aggregation
```python
yearly_expense = Employee.objects.sum('salary')
mean_age = User.objects.average('age')


class Article(Document):
    tag = ListField(StringField())

# After adding some tagged articles...
tag_freqs = Article.objects.item_frequencies('tag', normalize=True)

from operator import itemgetter
top_tags = sorted(tag_freqs.items(), key=itemgetter(1), reverse=True)[:10]

```