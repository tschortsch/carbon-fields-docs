# Hooks

There are several hooks that allow you to include your custom classes and functionality at the right time, in the right place:

### General

*(action)* `carbon_register_fields`

Called prior to registering the Fields.

*(action)* `carbon_after_register_fields`

Called after all Fields have been registered.

### Templates

*(filter)* `carbon_template` `($html, $name)`

Applied to the template html before putting it into the admin footer.

*(filter)* `carbon_template_{template-name}` `($html)`

Same as `carbon_template`, but you can specify a template name.

### Relationship & Association Fields

*(filter)* `carbon_relationship_title` `($title, $name, $id, $type, $subtype)`

Allows you to modify the title of the relationship / association items. Helpful when implementing custom relationship / association items. Passes the following parameters:

* *string* `$title` The unfiltered item title.
* *string* `$name` Name of the relationship / association field.
* *int* `$id` The database ID of the item.
* *string* `$type` Item type (post, term, user, comment, or a custom one).
* *string* `$subtype` Subtype – `page`, `post`, `category`, etc.

*(filter)* `carbon_relationship_item_label` `($label, $name, $id, $type, $subtype)`

Allows you to modify the label of the relationship / association items. Helpful when implementing custom relationship / association items, or when you want to change the default label. Passes the following parameters:

* *string* `$label` The unfiltered item label.
* *string* `$name` Name of the relationship / association field.
* *int* `$id` The database ID of the item.
* *string* `$type` Item type (post, term, user, comment, or a custom one).
* *string* `$subtype` Subtype – `page`, `post`, `category`, etc.

*(filter)* `carbon_relationship_comment_length` `($number, $name)`

Allows you to change the number of characters, visible from the comment text in an item. Passes the following parameters:

* *int* `$number` Number of characters. Default: `30`
* *string* `$name` Name of the relationship / association field.

*(filter)* `carbon_relationship_options_{name}_post_{post_type}` `($options)`

Allows you to modify the available options of the relationship / association field with name `{name}` from the `{post_type}` post type.

For example, if you want to filter the page post type options of the `crb_relationship` field, you would use the following filter: `carbon_relationship_options_crb_relationship_post_page`

*(filter)* `carbon_relationship_options_{name}_taxonomy_{taxonomy}` `($options)`

Allows you to modify the available options of the relationship / association field with name `{name}` from the `{taxonomy}` taxonomy.

For example, if you want to filter the category taxonomy options of the `crb_relationship` field, you would use the following filter: `carbon_relationship_options_crb_relationship_taxonomy_category`

*(filter)* `carbon_relationship_options_{name}_user` `($options)`

Allows you to modify the available options of the relationship / association field with name `{name}` that are users.

For example, if you want to filter the users options of the `crb_relationship` field, you would use the following filter: `carbon_relationship_options_crb_relationship_user`

*(filter)* `carbon_relationship_options_{name}_comment` `($options)`

Allows you to modify the available options of the relationship / association field with name `{name}` that are comments.

For example, if you want to filter the comments options of the `crb_relationship` field, you would use the following filter: `carbon_relationship_options_crb_relationship_comment`

*(filter)* `carbon_relationship_options` `($options, $name)`

Allows you to filter the available options of a relationship / association field. Passes the following parameters:

* *array* `$options` Unfiltered options.
* *string* `$name` Name of the relationship / association field.

### Gravity Form Field

*(filter)* `crb_gravity_form_options` `($options)`

Applied to the gravity form options.