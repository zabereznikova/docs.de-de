---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620342"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="fea26-101">MEF-Kataloge implementieren IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul zu erstellen</span><span class="sxs-lookup"><span data-stu-id="fea26-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="fea26-102">Details</span><span class="sxs-lookup"><span data-stu-id="fea26-102">Details</span></span>

<span data-ttu-id="fea26-103">Ab .NET Framework 4.5 implementieren MEF-Kataloge IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>-Objekt) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fea26-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="fea26-104">Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fea26-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fea26-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fea26-105">Suggestion</span></span>

<span data-ttu-id="fea26-106">MEF kann nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fea26-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="fea26-107">name</span><span class="sxs-lookup"><span data-stu-id="fea26-107">Name</span></span>    | <span data-ttu-id="fea26-108">Wert</span><span class="sxs-lookup"><span data-stu-id="fea26-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fea26-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="fea26-109">Scope</span></span>   |<span data-ttu-id="fea26-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="fea26-110">Major</span></span>|
|<span data-ttu-id="fea26-111">Version</span><span class="sxs-lookup"><span data-stu-id="fea26-111">Version</span></span>|<span data-ttu-id="fea26-112">4.5</span><span class="sxs-lookup"><span data-stu-id="fea26-112">4.5</span></span>|
|<span data-ttu-id="fea26-113">Typ</span><span class="sxs-lookup"><span data-stu-id="fea26-113">Type</span></span>|<span data-ttu-id="fea26-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fea26-114">Runtime</span></span>|
