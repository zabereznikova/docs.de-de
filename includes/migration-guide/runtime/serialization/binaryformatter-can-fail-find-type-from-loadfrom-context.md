---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496660"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>„BinaryFormatter“ findet den Typ im LoadFrom-Kontext möglicherweise nicht

#### <a name="details"></a>Details

Ab .NET Framework 4.5 führen diverse <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>-Änderungen zu Unterschieden in der Deserialisierung, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> verwendet wird, um Typen zu deserialisieren, die im LoadFrom-Kontext geladen wurden. Diese Änderungen werden durch die neuen Arten hervorgerufen, auf die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> nun Typen lädt. Dies führt zu einem abweichenden Verhalten, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> versucht, diese Typen später zu deserialisieren. Der Standardbinder für die Serialisierung durchsucht den LoadFrom-Kontext nicht automatisch, obwohl dies in einigen Fällen funktioniert haben kann, die auf dem früheren Verhalten von „XmlSerializer“ basieren. Wegen der Änderung kann eine <xref:System.IO.FileNotFoundException?displayProperty=fullName>-Ausnahme ausgelöst werden, wenn ein Typ aus einer Assembly geladen wird, die in einem anderen Kontext geladen wurde.

#### <a name="suggestion"></a>Vorschlag

Wenn diese Ausnahme angezeigt wird, kann die <code>Binder</code>-Eigenschaft von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> auf einen benutzerdefinierten Binder festgelegt werden, der den richtigen Typ<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>und anschließend den benutzerdefinierten Binder sucht:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
