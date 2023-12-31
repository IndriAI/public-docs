# IndriU Documentation

The IndriU (Indri Universal) library is available to all supported languages. It provides a set of `say` functions for
sending plain or formatted output (CSS attributes, HTML or Markdown) to the Output view, and a set of `ask` functions
for getting input from the user via a dialog box.

## Table of Contents

### TypeScript

#### Say

- [Functions](#say-functions)
  - [say](#say)
  - [sayHTML](#sayhtml)
- [Format](#sayformat)

#### Ask

- [Functions](#ask-functions)
  - [ask](#ask)
  - [askAsync](#askasync)
  - [askBoolean](#askboolean)
  - [askBooleanAsync](#askbooleanasync)
  - [askConfirm](#askconfirm)
  - [askConfirmAsync](#askconfirmasync)
- [Interfaces](#ask-interfaces)
  - [AskProps](#askprops)
- [Types](#ask-types)
  - [AskCallback](#type-askcallback)
  - [AskConfirm](#type-askconfirm)
  - [AskCancel](#type-askcancel)

### Python

#### Say

- [say](#python-say)
- [sayHTML](#python-sayhtml)

#### Ask

- [ask](#python-ask)
- [askAsync](#python-askasync)
- [askBoolean](#python-askboolean)
- [askBooleanAsync](#python-askbooleanasync)
- [askConfirm](#python-askconfirm)
- [askConfirmAsync](#python-askconfirmasync)
- [askCancel](#python-askcancel)
- [askCancelAsync](#python-askcancelasync)

### TypeScript

#### Say Functions <a name="say-functions"></a>

##### say  <a name="say"></a>

Sends a text-based message to the client.

`say(value: string, format?: SayFormat | string): void`

- `value`: The text to be sent to the client.
- `format`: Optional. The format of the text. See [SayFormat](#sayformat).

Example Usage:

```typescript
say('hello')
say('hello', { color: 'red' })
say('hello', { fontWeight: 'bold' })
say('hello', { fontStyle: 'italic' })
say('hello', { color: 'red', fontWeight: 'bold', fontStyle: 'italic' })
```

##### sayHTML  <a name="sayhtml"></a>

Sends an HTML-based message to the client.

- `htmlString`: The HTML string to be sent to the client.

Example Usage:

```typescript
sayHTML('<span style="color: red">hello</span>')
```

#### Say Format  <a name="sayformat"></a>

Properties for formatting text messages.

- `color`: Optional. The color of the text.
- `fontWeight`: Optional. The font weight of the text.
- `fontStyle`: Optional. The font style of the text.

This can also be used as a stringify version of the format object.

#### Ask Functions  <a name="ask-functions"></a>

##### ask  <a name="ask"></a>

Opens an input-based dialog and returns the input value.

`ask(text: string, props?: AskProps): Promise<string>`

- `text`: The text to display in the dialog.
- `props`: Configuration properties for the dialog (optional). See [AskProps](#askprops).

Example Usage:

```typescript
ask(text, { title: "Personal Info", description: "Change your first name", showCancel: true });
```

##### askAsync  <a name="askasync"></a>

Opens an input-based dialog and asynchronously handles the input value.

`askAsync(text: string, action: AskCallback, props?: AskProps): void`

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the input value. See [AskCallback](#askcallback).
- `props`: Configuration properties for the dialog (optional). See [AskProps](#askprops).

Example Usage:

```typescript
askAsync("First Name", (value) => setFirstName(value), { title: "Personal Info", description: "Change your first name", showCancel: true })
```

##### askBoolean  <a name="askboolean"></a>

Opens a boolean-based dialog and returns the boolean value.

`askBoolean(text: string, props?: AskProps): Promise<boolean>`

- `text`: The text to display in the dialog.
- `props`: Configuration properties for the dialog (optional). See [AskProps](#askprops).

Example Usage:

```typescript
const close = await askBoolean("Close window?", { title: "Confirm", description: "This window has unsaved changes", showCancel: false })
```

##### askBooleanAsync  <a name="askbooleanasync"></a>

Opens a boolean-based dialog and asynchronously handles the boolean value.

`askBooleanAsync(text: string, action: AskCallback, props?: AskProps): void`

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the boolean value. See [AskCallback](#askcallback).
- `props`: Configuration properties for the dialog (optional). See [AskProps](#askprops).

Example Usage:

```typescript
askBooleanAsync("Close window?", (value) => closeWindow(value), { title: "Confirm", description: "This window has unsaved changes", showCancel: false });
```

##### askConfirm  <a name="askconfirm"></a>

Opens a confirmation dialog and returns the boolean value.

`askConfirm(text: string, props?: AskProps): Promise<boolean>`

- `text`: The text to display in the dialog.
- `props`: Configuration properties for the dialog (optional). See [AskConfirm](#interfaces).

Example Usage:

```typescript
const close = await askConfirm("Close window?", { description: "This window has unsaved changes", showCancel: false });
```

##### askConfirmAsync  <a name="askconfirmasync"></a>

Opens a confirmation dialog and asynchronously handles the boolean value.

`askConfirmAsync(text: string, action: AskCallback, props?: AskProps): void`

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the confirmation result. See [AskCallback](#askcallback).
- `props`: Configuration properties for the dialog (optional). See [AskConfirm](#interfaces).

Example Usage:

```typescript
askConfirmAsync("Close window?", (value) => closeWindow(value), { description: "This window has unsaved changes", showCancel: true});
```

#### Ask Interfaces  <a name="ask-interfaces"></a>

##### AskProps  <a name="askprops"></a>

Properties for configuring dialog behavior.

- `title`: Optional. The title of the dialog. Default is `"Input"`.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `false`.

#### Ask Types <a name="ask-types"></a>

##### AskCallback  <a name="type-askcallback"></a>

Callback function for handling dialog responses.

- `value`: The value obtained from the dialog.

##### AskConfirm  <a name="type-askconfirm"></a>

Type representing properties for a confirmation dialog.

##### AskCancel  <a name="type-askcancel"></a>

Type representing properties for a cancellation dialog.

### Python

#### Say Functions

##### say <a name="python-say"></a>

Sends a text-based message to the client.

`say(s: str, options: str | dict = None) -> str`

- `s`: The text to be sent to the client.
- `options`: Optional. A JSON string or dictionary with formatting options.
- Returns: The sent text as a string.

Example Usage:

```python
say('hello')
say('hello', { 'color': 'red' })
say('hello', dict(color='red'))
```

##### sayHTML <a name="python-sayhtml"></a>

Sends an HTML-based message to the client.

`sayHTML(s: str) -> str`

- `s`: The HTML string to be sent to the client.
- Returns: The sent HTML string as a string.

Example Usage:

```python
sayHTML('<span style="color: red">hello</span>')
```

#### Ask Functions

##### ask <a name="python-ask"></a>

Opens a dialog and returns the user's input asynchronously.

```python
ask(text: str, title: str = None, description: str = None, showCancel: bool = False) -> str
```

- `text`: The text to display in the dialog.
- `title`: Optional. The title of the dialog.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.
- Returns: The user's input as a string.

Example Usage:

```python
ask("First Name", title="Personal Info", description="Change your first name", showCancel=True).then(lambda resp: say(resp))
```

##### askAsync <a name="python-askasync"></a>

Opens a dialog and asynchronously handles the user's input.

```python
askAsync(text: str, action: AskCallback, title: str = None, description: str = None, showCancel: bool = False) -> None
```

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the user's input.
- `title`: Optional. The title of the dialog.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.

Example Usage:

```python
def callback(value):
    say(value)
    
askAsync("First Name", callback, title="Personal Info", description="Change your first name", showCancel=True)
```

##### askBoolean <a name="python-askboolean"></a>

Opens a boolean dialog and returns the user's response.

```python
askBoolean(text: str, title: str = None, description: str = None, showCancel: bool = False) -> bool
```

- `text`: The text to display in the dialog.
- `title`: Optional. The title of the dialog.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.
- Returns: The user's response as a boolean.

Example Usage:

```python
askBoolean("Close window?", title="Confirm", description="This window has unsaved changes", showCancel=False).then(lambda resp: say(resp))
```

##### askBooleanAsync <a name="python-askbooleanasync"></a>

Opens a boolean dialog and asynchronously handles the user's response.

```python
askBooleanAsync(text: str, action: AskCallback, title: str = None, description: str = None, showCancel: bool = False) -> None
```

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the user's response.
- `title`: Optional. The title of the dialog.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.

Example Usage:

```python
def callback(value):
    say(value)

askBooleanAsync("Close window?", callback, title="Confirm", description="This window has unsaved changes", showCancel=False)
```

##### askConfirm <a name="python-askconfirm"></a>

Opens a confirmation dialog and returns the user's response.

```python
askConfirm(text: str, title: str = None, description: str = None, showCancel: bool = False) -> bool
```

- `text`: The text to display in the dialog.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.
- Returns: The user's response as a boolean.

Example Usage:

```python
askConfirm("Close window?", description="This window has unsaved changes", showCancel=False).then(lambda resp: say(resp))
```

##### askConfirmAsync <a name="python-askconfirmasync"></a>

Opens a confirmation dialog and asynchronously handles the user's response.

```python
askConfirmAsync(text: str, action: AskCallback, title: str = None, description: str = None, showCancel: bool = False) -> None
```

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the user's response.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.

Example Usage:

```python
def callback(value):
    say(value)

askConfirmAsync("Close window?", callback, description="This window has unsaved changes", showCancel=False)
```

##### askCancel <a name="python-askcancel"></a>

Opens a cancellation dialog and returns the user's response.

```python
askCancel(text: str, title: str = None, description: str = None, showCancel: bool = False) -> bool
```

- `text`: The text to display in the dialog.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.
- Returns: The user's response as a boolean.

Example Usage:

```python
askCancel("Close window?", description="This window has unsaved changes", showCancel=False).then(lambda resp: say(resp))
```

##### askCancelAsync <a name="python-askcancelasync"></a>

Opens a cancellation dialog and asynchronously handles the user's response.

```python
askCancelAsync(text: str, action: AskCallback, title: str = None, description: str = None, showCancel: bool = False) -> None
```

- `text`: The text to display in the dialog.
- `action`: Callback function to handle the user's response.
- `description`: Optional. The description of the dialog.
- `showCancel`: Optional. Whether to show a cancel option. Default is `False`.

Example Usage:

```python
def callback(value):
    say(value)

askCancelAsync("Close window?", callback, description="This window has unsaved changes", showCancel=False)
```
