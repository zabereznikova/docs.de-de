---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616113"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="9fd49-101">DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="9fd49-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

#### <a name="details"></a><span data-ttu-id="9fd49-102">Details</span><span class="sxs-lookup"><span data-stu-id="9fd49-102">Details</span></span>

<span data-ttu-id="9fd49-103"><xref:System.Data.Common.DbParameter.Precision> und <xref:System.Data.Common.DbParameter.Scale> werden als öffentliche virtuelle Eigenschaften implementiert.</span><span class="sxs-lookup"><span data-stu-id="9fd49-103"><xref:System.Data.Common.DbParameter.Precision> and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="9fd49-104">Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="9fd49-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9fd49-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9fd49-105">Suggestion</span></span>

<span data-ttu-id="9fd49-106">Wenn Sie einen ADO.NET-Datenbankanbieter neu erstellen, erfordern diese Unterschiede die Anwendung des Schlüsselworts „override“ auf die Eigenschaften „Precision“ und „Scale“.</span><span class="sxs-lookup"><span data-stu-id="9fd49-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="9fd49-107">Dies ist nur beim erneuten Erstellen von Komponenten erforderlich. Vorhandene Binärdateien funktionieren weiterhin.</span><span class="sxs-lookup"><span data-stu-id="9fd49-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>

| <span data-ttu-id="9fd49-108">name</span><span class="sxs-lookup"><span data-stu-id="9fd49-108">Name</span></span>    | <span data-ttu-id="9fd49-109">Wert</span><span class="sxs-lookup"><span data-stu-id="9fd49-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9fd49-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="9fd49-110">Scope</span></span>   | <span data-ttu-id="9fd49-111">Gering</span><span class="sxs-lookup"><span data-stu-id="9fd49-111">Minor</span></span>       |
| <span data-ttu-id="9fd49-112">Version</span><span class="sxs-lookup"><span data-stu-id="9fd49-112">Version</span></span> | <span data-ttu-id="9fd49-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="9fd49-113">4.5.1</span></span>       |
| <span data-ttu-id="9fd49-114">Typ</span><span class="sxs-lookup"><span data-stu-id="9fd49-114">Type</span></span>    | <span data-ttu-id="9fd49-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="9fd49-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9fd49-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9fd49-116">Affected APIs</span></span>

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
