+++
description = "Synchronize selection of content in different tabbed views"
title = "Tabbed views"
+++

Choose which content to see across the page. Very handy for providing code
snippets for multiple languages or providing configuration in different formats.

## Code example

````go
{{</* tabs */>}}
{{%/* tab name="python" */%}}
```python
print("Hello World!")
```
{{%/* /tab */%}}
{{%/* tab name="R" */%}}
```R
> print("Hello World!")
```
{{%/* /tab */%}}
{{%/* tab name="Bash" */%}}
```Bash
echo "Hello World!"
```
{{%/* /tab */%}}
{{</* /tabs */>}}
````

Renders as:

{{< tabs groupId="tabs-example-language" >}}
{{% tab name="python" %}}
```python
print("Hello World!")
```
{{% /tab %}}
{{% tab name="R" %}}
```R
> print("Hello World!")
```
{{% /tab %}}
{{% tab name="Bash" %}}
```Bash
echo "Hello World!"
```
{{% /tab %}}
{{< /tabs >}}

Tab views with the same tabs that belong to the same group sychronize their selection:

{{< tabs groupId="tabs-example-language" >}}
{{% tab name="python" %}}
```python
print("Hello World!")
```
{{% /tab %}}
{{% tab name="R" %}}
```R
> print("Hello World!")
```
{{% /tab %}}
{{% tab name="Bash" %}}
```Bash
echo "Hello World!"
```
{{% /tab %}}
{{< /tabs >}}

## Config example

````go
{{</* tabs groupId="config" */>}}
{{%/* tab name="json" */%}}
```json
{
  "Hello": "World"
}
```
{{%/* /tab */%}}
{{%/* tab name="XML" */%}}
```xml
<Hello>World</Hello>
```
{{%/* /tab */%}}
{{%/* tab name="properties" */%}}
```properties
Hello = World
```
{{%/* /tab */%}}
{{</* /tabs */>}}
````

Renders as:

{{< tabs groupId="tabs-example-config" >}}
{{% tab name="json" %}}
```json
{
  "Hello": "World"
}
```
{{% /tab %}}
{{% tab name="XML" %}}
```xml
<Hello>World</Hello>
```
{{% /tab %}}
{{% tab name="properties" %}}
```ini
Hello = World
```
{{% /tab %}}
{{< /tabs >}}

{{% notice warning %}}
When using tab views with different content sets, make sure to use a common `groupId` for equal sets but distinct
`groupId` for different sets. The `groupId` defaults to `'default'`.
**Take this into account across the whole site!**
The tab selection is restored automatically based on the `groupId` and if it cannot find a tab item because it came
from the `'default'` group on a different page then all tabs will be empty at first.
{{% /notice %}}
