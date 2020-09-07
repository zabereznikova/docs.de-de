---
ms.openlocfilehash: 71cc7119710a2b381626dd9cf4ab66265eb3deba
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496746"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="62e74-101">Hashtable und ähnlich sortierte Auflistungsobjekte können von SoapFormatter nicht deserialisiert werden</span><span class="sxs-lookup"><span data-stu-id="62e74-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="62e74-102">Details</span><span class="sxs-lookup"><span data-stu-id="62e74-102">Details</span></span>

<span data-ttu-id="62e74-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> garantiert nicht dafür, dass unter einer .NET Framework-Version serialisierte Objekte erfolgreich unter einer anderen Version deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="62e74-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="62e74-104">Insbesondere einige sortierte Auflistungen (z.B. <xref:System.Collections.Hashtable?displayProperty=fullName>) haben Member zwischen 4.0 und 4.5 hinzugefügt, sodass Objekte dieser Typen nicht mit .NET Framework 4.0 deserialisiert werden können, wenn sie mit .NET Framework 4.5 serialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="62e74-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="62e74-105">Beachten Sie, dass kein Problem auftritt, wenn die serialisierten Daten mit derselben Version von .NET Framework sowohl serialisiert als auch deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="62e74-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="62e74-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="62e74-106">Suggestion</span></span>

<span data-ttu-id="62e74-107">Die <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName>-Serialisierung sollte durch die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName>-Serialisierung oder durch <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> ersetzt werden, um .NET Framework-Änderungen verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="62e74-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="62e74-108">name</span><span class="sxs-lookup"><span data-stu-id="62e74-108">Name</span></span>    | <span data-ttu-id="62e74-109">Wert</span><span class="sxs-lookup"><span data-stu-id="62e74-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="62e74-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="62e74-110">Scope</span></span>   |<span data-ttu-id="62e74-111">Gering</span><span class="sxs-lookup"><span data-stu-id="62e74-111">Minor</span></span>|
|<span data-ttu-id="62e74-112">Version</span><span class="sxs-lookup"><span data-stu-id="62e74-112">Version</span></span>|<span data-ttu-id="62e74-113">4.5</span><span class="sxs-lookup"><span data-stu-id="62e74-113">4.5</span></span>|
|<span data-ttu-id="62e74-114">Typ</span><span class="sxs-lookup"><span data-stu-id="62e74-114">Type</span></span>|<span data-ttu-id="62e74-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="62e74-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="62e74-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="62e74-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
