---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497643"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a><span data-ttu-id="a1627-101">Ein in .NET Framework 4.5 mit NetDataContractSerializer serialisiertes ConcurrentDictionary-Element kann nicht von .NET Framework 4.5.1 oder 4.5.2 deserialisiert werden</span><span class="sxs-lookup"><span data-stu-id="a1627-101">A ConcurrentDictionary serialized in .NET Framework 4.5 with NetDataContractSerializer cannot be deserialized by .NET Framework 4.5.1 or 4.5.2</span></span>

#### <a name="details"></a><span data-ttu-id="a1627-102">Details</span><span class="sxs-lookup"><span data-stu-id="a1627-102">Details</span></span>

<span data-ttu-id="a1627-103">Aufgrund von Typänderungen können <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekte, die unter Verwendung von <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> mit .NET Framework 4.5 serialisiert werden, nicht in .NET Framework 4.5.1 oder 4.5.2 deserialisiert werden. Beachten Sie jedoch, dass die Serialisierung mit .NET Framework 4.5.x und die Deserialisierung mit .NET Framework 4.5 funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a1627-103">Due to internal changes to the type, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objects that are serialized with the .NET Framework 4.5 using the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> cannot be deserialized in the .NET Framework 4.5.1 or in the .NET Framework 4.5.2.Note that moving in the other direction (serializing with the .NET Framework 4.5.x and deserializing with the .NET Framework 4.5) works.</span></span> <span data-ttu-id="a1627-104">Genauso funktioniert die versionsübergreifende Serialisierung in .NET Framework 4.x mit .NET Framework 4.6. Dies hat keine Auswirkungen auf die (De-)Serialisierung einer einzelnen Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1627-104">Similarly, all 4.x cross-version serialization works with the .NET Framework 4.6.Serializing and deserializing with a single version of the .NET Framework is not affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1627-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a1627-105">Suggestion</span></span>

<span data-ttu-id="a1627-106">Wenn Sie ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>-Element zwischen .NET Framework 4.5 und .NET Framework 4.5.1/4.5.2 (de-)serialisieren müssen, sollten Sie statt <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> ein Serialisierungsmodul wie <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> verwenden. Das Problem könnte möglicherweise aber auch durch ein Upgrade auf .NET Framework 4.6 gelöst werden, da es in dieser Version behoben wird.</span><span class="sxs-lookup"><span data-stu-id="a1627-106">If it is necessary to serialize and deserialize a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> between the .NET Framework 4.5 and .NET Framework 4.5.1/4.5.2, an alternate serializer like the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serializer should be used instead of the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>.Alternatively, because this issue is addressed in the .NET Framework 4.6, it may be solved by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="a1627-107">Name</span><span class="sxs-lookup"><span data-stu-id="a1627-107">Name</span></span>    | <span data-ttu-id="a1627-108">Wert</span><span class="sxs-lookup"><span data-stu-id="a1627-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1627-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="a1627-109">Scope</span></span>   |<span data-ttu-id="a1627-110">Gering</span><span class="sxs-lookup"><span data-stu-id="a1627-110">Minor</span></span>|
|<span data-ttu-id="a1627-111">Version</span><span class="sxs-lookup"><span data-stu-id="a1627-111">Version</span></span>|<span data-ttu-id="a1627-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a1627-112">4.5.1</span></span>|
|<span data-ttu-id="a1627-113">Typ</span><span class="sxs-lookup"><span data-stu-id="a1627-113">Type</span></span>|<span data-ttu-id="a1627-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a1627-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a1627-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a1627-115">Affected APIs</span></span>

<span data-ttu-id="a1627-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="a1627-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
