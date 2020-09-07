---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496643"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="934f3-101">MEF-Kataloge implementieren IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul zu erstellen</span><span class="sxs-lookup"><span data-stu-id="934f3-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="934f3-102">Details</span><span class="sxs-lookup"><span data-stu-id="934f3-102">Details</span></span>

<span data-ttu-id="934f3-103">Ab .NET Framework 4.5 implementieren MEF-Kataloge IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>-Objekt) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="934f3-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="934f3-104">Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="934f3-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="934f3-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="934f3-105">Suggestion</span></span>

<span data-ttu-id="934f3-106">MEF kann nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="934f3-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="934f3-107">name</span><span class="sxs-lookup"><span data-stu-id="934f3-107">Name</span></span>    | <span data-ttu-id="934f3-108">Wert</span><span class="sxs-lookup"><span data-stu-id="934f3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="934f3-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="934f3-109">Scope</span></span>   |<span data-ttu-id="934f3-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="934f3-110">Major</span></span>|
|<span data-ttu-id="934f3-111">Version</span><span class="sxs-lookup"><span data-stu-id="934f3-111">Version</span></span>|<span data-ttu-id="934f3-112">4.5</span><span class="sxs-lookup"><span data-stu-id="934f3-112">4.5</span></span>|
|<span data-ttu-id="934f3-113">Typ</span><span class="sxs-lookup"><span data-stu-id="934f3-113">Type</span></span>|<span data-ttu-id="934f3-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="934f3-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="934f3-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="934f3-115">Affected APIs</span></span>

<span data-ttu-id="934f3-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="934f3-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
