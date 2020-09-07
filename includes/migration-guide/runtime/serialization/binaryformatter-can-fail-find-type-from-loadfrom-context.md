---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496660"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a><span data-ttu-id="647b7-101">„BinaryFormatter“ findet den Typ im LoadFrom-Kontext möglicherweise nicht</span><span class="sxs-lookup"><span data-stu-id="647b7-101">BinaryFormatter can fail to find type from LoadFrom context</span></span>

#### <a name="details"></a><span data-ttu-id="647b7-102">Details</span><span class="sxs-lookup"><span data-stu-id="647b7-102">Details</span></span>

<span data-ttu-id="647b7-103">Ab .NET Framework 4.5 führen diverse <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>-Änderungen zu Unterschieden in der Deserialisierung, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> verwendet wird, um Typen zu deserialisieren, die im LoadFrom-Kontext geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="647b7-103">As of .NET Framework 4.5, a number of <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> changes may cause differences in deserialization when using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> to deserialize types that had been loaded in the LoadFrom context.</span></span> <span data-ttu-id="647b7-104">Diese Änderungen werden durch die neuen Arten hervorgerufen, auf die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> nun Typen lädt. Dies führt zu einem abweichenden Verhalten, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> versucht, diese Typen später zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="647b7-104">These changes are due to the new ways <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> now loads a type which causes different behavior when a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> attempts to deserialize to that type later on.</span></span> <span data-ttu-id="647b7-105">Der Standardbinder für die Serialisierung durchsucht den LoadFrom-Kontext nicht automatisch, obwohl dies in einigen Fällen funktioniert haben kann, die auf dem früheren Verhalten von „XmlSerializer“ basieren.</span><span class="sxs-lookup"><span data-stu-id="647b7-105">The default serialization binder does not automatically search the LoadFrom context, although it may have worked in some circumstances based on the old behavior of XmlSerializer.</span></span> <span data-ttu-id="647b7-106">Wegen der Änderung kann eine <xref:System.IO.FileNotFoundException?displayProperty=fullName>-Ausnahme ausgelöst werden, wenn ein Typ aus einer Assembly geladen wird, die in einem anderen Kontext geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="647b7-106">Due to the changes, when a type is being loaded from an assembly loaded in a different context, a <xref:System.IO.FileNotFoundException?displayProperty=fullName> may be thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="647b7-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="647b7-107">Suggestion</span></span>

<span data-ttu-id="647b7-108">Wenn diese Ausnahme angezeigt wird, kann die <code>Binder</code>-Eigenschaft von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> auf einen benutzerdefinierten Binder festgelegt werden, der den richtigen Typ</span><span class="sxs-lookup"><span data-stu-id="647b7-108">If this exception is seen, the <code>Binder</code> property of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> can be set to a custom binder that will find the correct type.</span></span><pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre><span data-ttu-id="647b7-109">und anschließend den benutzerdefinierten Binder sucht:</span><span class="sxs-lookup"><span data-stu-id="647b7-109">And then the custom binder:</span></span><pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="647b7-110">name</span><span class="sxs-lookup"><span data-stu-id="647b7-110">Name</span></span>    | <span data-ttu-id="647b7-111">Wert</span><span class="sxs-lookup"><span data-stu-id="647b7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="647b7-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="647b7-112">Scope</span></span>   |<span data-ttu-id="647b7-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="647b7-113">Edge</span></span>|
|<span data-ttu-id="647b7-114">Version</span><span class="sxs-lookup"><span data-stu-id="647b7-114">Version</span></span>|<span data-ttu-id="647b7-115">4.5</span><span class="sxs-lookup"><span data-stu-id="647b7-115">4.5</span></span>|
|<span data-ttu-id="647b7-116">Typ</span><span class="sxs-lookup"><span data-stu-id="647b7-116">Type</span></span>|<span data-ttu-id="647b7-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="647b7-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="647b7-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="647b7-118">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
