---
ms.openlocfilehash: 1721d32f8cdc9b6ea4b4732e38afa56a8a532600
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234731"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="60749-101">DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="60749-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

|   |   |
|---|---|
|<span data-ttu-id="60749-102">Details</span><span class="sxs-lookup"><span data-stu-id="60749-102">Details</span></span>|<xref:System.Data.Common.DbParameter.Precision> <span data-ttu-id="60749-103">und <xref:System.Data.Common.DbParameter.Scale> werden als öffentliche virtuelle Eigenschaften implementiert.</span><span class="sxs-lookup"><span data-stu-id="60749-103">and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="60749-104">Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="60749-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>|
|<span data-ttu-id="60749-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="60749-105">Suggestion</span></span>|<span data-ttu-id="60749-106">Wenn Sie einen ADO.NET-Datenbankanbieter neu erstellen, erfordern diese Unterschiede die Anwendung des Schlüsselworts „override“ auf die Eigenschaften „Precision“ und „Scale“.</span><span class="sxs-lookup"><span data-stu-id="60749-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="60749-107">Dies ist nur beim erneuten Erstellen von Komponenten erforderlich. Vorhandene Binärdateien funktionieren weiterhin.</span><span class="sxs-lookup"><span data-stu-id="60749-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>|
|<span data-ttu-id="60749-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="60749-108">Scope</span></span>|<span data-ttu-id="60749-109">Gering</span><span class="sxs-lookup"><span data-stu-id="60749-109">Minor</span></span>|
|<span data-ttu-id="60749-110">Version</span><span class="sxs-lookup"><span data-stu-id="60749-110">Version</span></span>|<span data-ttu-id="60749-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="60749-111">4.5.1</span></span>|
|<span data-ttu-id="60749-112">Typ</span><span class="sxs-lookup"><span data-stu-id="60749-112">Type</span></span>|<span data-ttu-id="60749-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="60749-113">Retargeting</span></span>|
|<span data-ttu-id="60749-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="60749-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType></li></ul>|
