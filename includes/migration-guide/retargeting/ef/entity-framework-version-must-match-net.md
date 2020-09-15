---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617191"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="b7297-101">Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="b7297-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="b7297-102">Details</span><span class="sxs-lookup"><span data-stu-id="b7297-102">Details</span></span>

<span data-ttu-id="b7297-103">Die Version von Entity Framework muss mit der .NET Framework-Version übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b7297-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="b7297-104">Für .NET Framework 4.5 wird Entity Framework 5 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b7297-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="b7297-105">Bei EF 4.x in einem .NET Framework 4.5-Projekt sind im Zusammenhang mit <xref:System.ComponentModel.DataAnnotations> mehrere Probleme bekannt.</span><span class="sxs-lookup"><span data-stu-id="b7297-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="b7297-106">In .NET Framework 4.5 wurden diese in eine andere Assembly verschoben. Daher gibt es Probleme mit der Bestimmung der zu verwendenden Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="b7297-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b7297-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b7297-107">Suggestion</span></span>

<span data-ttu-id="b7297-108">Führen Sie bei Verwendung von .NET Framework 4.5 ein Upgrade auf Entity Framework 5 durch.</span><span class="sxs-lookup"><span data-stu-id="b7297-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="b7297-109">name</span><span class="sxs-lookup"><span data-stu-id="b7297-109">Name</span></span>    | <span data-ttu-id="b7297-110">Wert</span><span class="sxs-lookup"><span data-stu-id="b7297-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b7297-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="b7297-111">Scope</span></span>   | <span data-ttu-id="b7297-112">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="b7297-112">Major</span></span>       |
| <span data-ttu-id="b7297-113">Version</span><span class="sxs-lookup"><span data-stu-id="b7297-113">Version</span></span> | <span data-ttu-id="b7297-114">4.5</span><span class="sxs-lookup"><span data-stu-id="b7297-114">4.5</span></span>         |
| <span data-ttu-id="b7297-115">Typ</span><span class="sxs-lookup"><span data-stu-id="b7297-115">Type</span></span>    | <span data-ttu-id="b7297-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b7297-116">Retargeting</span></span> |
