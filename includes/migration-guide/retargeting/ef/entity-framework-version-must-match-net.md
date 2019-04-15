---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234724"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="90e6b-101">Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="90e6b-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="90e6b-102">Details</span><span class="sxs-lookup"><span data-stu-id="90e6b-102">Details</span></span>|<span data-ttu-id="90e6b-103">Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="90e6b-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="90e6b-104">Für .NET Framework 4.5 wird Entity Framework 5 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="90e6b-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="90e6b-105">Bei EF 4.x in einem .NET Framework 4.5-Projekt sind im Zusammenhang mit <xref:System.ComponentModel.DataAnnotations> mehrere Probleme bekannt.</span><span class="sxs-lookup"><span data-stu-id="90e6b-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="90e6b-106">In .NET 4.5 wurden diese in eine andere Assembly verschoben, daher gibt es Probleme mit der Bestimmung der zu verwendenden Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="90e6b-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="90e6b-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="90e6b-107">Suggestion</span></span>|<span data-ttu-id="90e6b-108">Führen Sie bei Verwendung von .NET Framework 4.5 ein Upgrade auf Entity Framework 5 durch.</span><span class="sxs-lookup"><span data-stu-id="90e6b-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="90e6b-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="90e6b-109">Scope</span></span>|<span data-ttu-id="90e6b-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="90e6b-110">Major</span></span>|
|<span data-ttu-id="90e6b-111">Version</span><span class="sxs-lookup"><span data-stu-id="90e6b-111">Version</span></span>|<span data-ttu-id="90e6b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="90e6b-112">4.5</span></span>|
|<span data-ttu-id="90e6b-113">Typ</span><span class="sxs-lookup"><span data-stu-id="90e6b-113">Type</span></span>|<span data-ttu-id="90e6b-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="90e6b-114">Retargeting</span></span>|
