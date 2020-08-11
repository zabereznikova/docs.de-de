---
ms.openlocfilehash: 2e9267b35c9389da017927aca2346190348265c9
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87919305"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="19de5-101">BinaryFormatter.Deserialize umschließt einige Ausnahmen in SerializationException erneut</span><span class="sxs-lookup"><span data-stu-id="19de5-101">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="19de5-102">Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode umschließt jetzt einige Ausnahmeobjekte innerhalb einer <xref:System.Runtime.Serialization.SerializationException> erneut, bevor die Ausnahme an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="19de5-102">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

#### <a name="change-description"></a><span data-ttu-id="19de5-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="19de5-103">Change description</span></span>

<span data-ttu-id="19de5-104">Bisher erlaubte die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode die Weitergabe einiger zufälliger Ausnahmen, wie z. B. <xref:System.ArgumentNullException> den Stapel entlang zu den Aufrufern.</span><span class="sxs-lookup"><span data-stu-id="19de5-104">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="19de5-105">In .NET 5.0 und höher fängt die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>-Methode Ausnahmen aufgrund von ungültigen Deserialisierungsvorgängen aggressiver ab und umschließt sie in einer <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="19de5-105">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="19de5-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="19de5-106">Version introduced</span></span>

<span data-ttu-id="19de5-107">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="19de5-107">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="19de5-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="19de5-108">Recommended action</span></span>

<span data-ttu-id="19de5-109">In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="19de5-109">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="19de5-110">Wenn es für Ihre Aufrufsite jedoch erforderlich ist, dass eine bestimmte Ausnahme ausgelöst wird, können Sie die Umschließung der Ausnahme in der äußeren <xref:System.Runtime.Serialization.SerializationException> aufheben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="19de5-110">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

#### <a name="category"></a><span data-ttu-id="19de5-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="19de5-111">Category</span></span>

<span data-ttu-id="19de5-112">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="19de5-112">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="19de5-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="19de5-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
