---
ms.openlocfilehash: ac929a8b3e9a7d56122f5699c51819ad483d1f5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804052"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>„BinaryFormatter“ findet den Typ im LoadFrom-Kontext möglicherweise nicht

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 führen diverse <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>-Änderungen zu Unterschieden in der Deserialisierung, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> verwendet wird, um Typen zu deserialisieren, die im LoadFrom-Kontext geladen wurden. Diese Änderungen werden durch die neuen Arten hervorgerufen, auf die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> nun Typen lädt. Dies führt zu einem abweichenden Verhalten, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> versucht, diese Typen später zu deserialisieren. Der Standardbinder für die Serialisierung durchsucht den LoadFrom-Kontext nicht automatisch, obwohl dies in einigen Fällen funktioniert haben kann, die auf dem früheren Verhalten von „XmlSerializer“ basieren. Wegen der Änderung kann eine <xref:System.IO.FileNotFoundException?displayProperty=name>-Ausnahme ausgelöst werden, wenn ein Typ aus einer Assembly geladen wird, die in einem anderen Kontext geladen wurde.|
|Vorschlag|Wenn diese Ausnahme angezeigt wird, kann die <code>Binder</code>-Eigenschaft von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> auf einen benutzerdefinierten Binder festgelegt werden, der den richtigen Typ<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>und anschließend den benutzerdefinierten Binder sucht:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
