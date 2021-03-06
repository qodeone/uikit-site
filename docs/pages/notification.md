# Notification

<p class="uk-text-lead">Create toggleable notifications that fade out automatically.</p>

## Usage

The notification will not fade out but remain visible when you hover the message until you stop hovering. You can also close the notification by clicking it. To show notifications, the component provides a simple JavaScript API. The following code snippet gets you started.

### JavaScript

```js
UIkit.notification({
    message: 'my-message!',
    status: 'primary',
    pos: 'top-right',
    timeout: 5000
});

// Shortcuts
UIkit.notification('My message');
UIkit.notification('My message', status);
UIkit.notification('My message', { /* options */ });
```

```example
<button class="demo uk-button uk-button-default" type="button" data-message="Notification message">Click me</button>
```

***

## HTML message

You can use HTML inside your notification message, like an icon from the Icon component.

```js
UIkit.notification("<span uk-icon='icon: check'></span> Message");
```

```example
<button class="uk-button demo uk-button-default" type="button" data-message="<span uk-icon='icon: check'></span> Message with an icon">With icon</button>
```

***

## Position

Add one of the following parameters to adjust the notification's position to different corners.


```js
UIkit.notification("...", {pos: 'top-right'})
```

| Position        | Code |
| --------------- | ---- |
| `top-left`      | `UIkit.notification("...", {pos: 'top-left'})`      |
| `top-center`    | `UIkit.notification("...", {pos: 'top-center'})`    |
| `top-right`     | `UIkit.notification("...", {pos: 'top-right'})`     |
| `bottom-left`   | `UIkit.notification("...", {pos: 'bottom-left'})`   |
| `bottom-center` | `UIkit.notification("...", {pos: 'bottom-center'})` |
| `bottom-right`  | `UIkit.notification("...", {pos: 'bottom-right'})`  |


```example
<p uk-margin>
    <button class="uk-button uk-button-default demo" type="button" data-message="Top Left..." data-pos="top-left">Top Left</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Top Center..." data-pos="top-center">Top Center</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Top Right..." data-pos="top-right">Top Right</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Bottom Left..." data-pos="bottom-left">Bottom Left</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Bottom Center..." data-pos="bottom-center">Bottom Center</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Bottom Right..." data-pos="bottom-right">Bottom Right</button>
</p>
```


***

## Style

A notification can be styled by adding a status to the message to indicate a primary, success, warning or a danger status.

```js
UIkit.notification("...", {status: 'primary'})
```

| Style     | Code |
| --------- | ---- |
| `primary` | `UIkit.notification("...", {status:'primary'})` |
| `success` | `UIkit.notification("...", {status:'success'})` |
| `warning` | `UIkit.notification("...", {status:'warning'})` |
| `danger`  | `UIkit.notification("...", {status:'danger'})`  |

```example
<p uk-margin>
    <button class="uk-button uk-button-default demo" type="button" data-message="Primary message..." data-status="primary">Primary</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Success message..." data-status="success">Success</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Warning message..." data-status="warning">Warning</button>
    <button class="uk-button uk-button-default demo" type="button" data-message="Danger message..." data-status="danger">Danger</button>
</p>
```

***

## Close all

You can close all open notifications by calling `UIkit.notification.closeAll()`.

```example
<button class="uk-button uk-button-default close">Close all</button>
```


<script src="../assets/uikit/dist/js/components/notification.min.js"></script>
<script>
jQuery('button.demo').on('click', function() {
    UIkit.notification($(this).data());
});
jQuery('button.close').on('click', function() {
    UIkit.notification.closeAll();
});
</script>

***

## Component options

Any of these options can be applied to the component attribute. Separate multiple options with a semicolon. [Learn more](javascript.md#component-configuration)

| Option     | Value   | Default    | Description                                                         |
|------------|---------|------------|---------------------------------------------------------------------|
| `message ` | String  | false      | Notification message to show.                                       |
| `status`   | String  | null       | Notification status color.                                          |
| `timeout`  | Integer | 5000       | Visibility duration until a notification disappears.                |
| `group`    | String  | null       | Useful, if you want to close all notifications in a specific group. |
| `pos`      | String  | top-center | Display corner.                                                     |

***

## JavaScript

Learn more about [JavaScript components](javascript.md#programmatic-use).

### Initialization

This is a `Functional Component` and may omit the element argument.

```js
UIkit.notification(options);
UIkit.notification(message, status);
```

### Events

These events will be triggered on elements with this component attached.

| Name | Description |
| --- | --- |
| `close` | Fires after the notification has been closed. |
