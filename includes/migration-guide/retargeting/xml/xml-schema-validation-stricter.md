---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617239"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="624b0-101">Die XML-Schemaüberprüfung ist genauer</span><span class="sxs-lookup"><span data-stu-id="624b0-101">XML schema validation is stricter</span></span>

#### <a name="details"></a><span data-ttu-id="624b0-102">Details</span><span class="sxs-lookup"><span data-stu-id="624b0-102">Details</span></span>

<span data-ttu-id="624b0-103">In .NET Framework 4.5 ist die XML-Schemaüberprüfung genauer.</span><span class="sxs-lookup"><span data-stu-id="624b0-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="624b0-104">Wenn Sie xsd:anyURI verwenden, um einen URI wie ein mailto-Protokoll zu überprüfen, tritt bei der Validierung ein Fehler auf, wenn der URI Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="624b0-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="624b0-105">In früheren Versionen von .NET Framework war die Validierung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="624b0-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="624b0-106">Die Änderung betrifft nur Anwendungen, die auf .NET Framework 4.5 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="624b0-106">The change affects only applications that target the .NET Framework 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="624b0-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="624b0-107">Suggestion</span></span>

<span data-ttu-id="624b0-108">Wenn eine weniger genaue Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.0 von .NET Framework ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="624b0-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="624b0-109">Bei einer Neuausrichtung auf .NET Framework 4.5 sollte jedoch ein Code Review erfolgen, um sicherzustellen, dass ungültige URIs (mit Leerzeichen) nicht als Attributwerte mit dem Datentyp „anyURI“ erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="624b0-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>

| <span data-ttu-id="624b0-110">name</span><span class="sxs-lookup"><span data-stu-id="624b0-110">Name</span></span>    | <span data-ttu-id="624b0-111">Wert</span><span class="sxs-lookup"><span data-stu-id="624b0-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="624b0-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="624b0-112">Scope</span></span>   | <span data-ttu-id="624b0-113">Gering</span><span class="sxs-lookup"><span data-stu-id="624b0-113">Minor</span></span>       |
| <span data-ttu-id="624b0-114">Version</span><span class="sxs-lookup"><span data-stu-id="624b0-114">Version</span></span> | <span data-ttu-id="624b0-115">4.5</span><span class="sxs-lookup"><span data-stu-id="624b0-115">4.5</span></span>         |
| <span data-ttu-id="624b0-116">Typ</span><span class="sxs-lookup"><span data-stu-id="624b0-116">Type</span></span>    | <span data-ttu-id="624b0-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="624b0-117">Retargeting</span></span> |
