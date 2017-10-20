## Main category - Update 

Update certain properties of main category.
If some property is not passed it will be SKIPPED (NOT CHANGED).

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/menus/101/main-categories/5
```

```json
{
    "name": "Pizza"
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/menus/{menuNo}/main-categories/{mainCategoryNo}`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
name | string | false | | main category name
type | string | false | | main category type (see above)
description | string | false | | main category description
categories | array | false | array of integer | list of related categories (categoryNo). You can use this parameter if you want to set/update relations between main category and its categories. The order of passed categories is important and will be used for sorting.

> Response: no content

### HTTP Response (success)

`HTTP/1.1 200`
