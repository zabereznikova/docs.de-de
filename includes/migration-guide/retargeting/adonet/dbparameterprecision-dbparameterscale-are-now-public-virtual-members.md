---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616113"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="7edf6-101">DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="7edf6-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

#### <a name="details"></a><span data-ttu-id="7edf6-102">Details</span><span class="sxs-lookup"><span data-stu-id="7edf6-102">Details</span></span>

<span data-ttu-id="7edf6-103"><xref:System.Data.Common.DbParameter.Precision> und <xref:System.Data.Common.DbParameter.Scale> werden als öffentliche virtuelle Eigenschaften implementiert.</span><span class="sxs-lookup"><span data-stu-id="7edf6-103"><xref:System.Data.Common.DbParameter.Precision> and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="7edf6-104">Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="7edf6-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7edf6-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7edf6-105">Suggestion</span></span>

<span data-ttu-id="7edf6-106">Wenn Sie einen ADO.NET-Datenbankanbieter neu erstellen, erfordern diese Unterschiede die Anwendung des Schlüsselworts „override“ auf die Eigenschaften „Precision“ und „Scale“.</span><span class="sxs-lookup"><span data-stu-id="7edf6-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="7edf6-107">Dies ist nur beim erneuten Erstellen von Komponenten erforderlich. Vorhandene Binärdateien funktionieren weiterhin.</span><span class="sxs-lookup"><span data-stu-id="7edf6-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>

| <span data-ttu-id="7edf6-108">name</span><span class="sxs-lookup"><span data-stu-id="7edf6-108">Name</span></span>    | <span data-ttu-id="7edf6-109">Wert</span><span class="sxs-lookup"><span data-stu-id="7edf6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7edf6-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="7edf6-110">Scope</span></span>   | <span data-ttu-id="7edf6-111">Gering</span><span class="sxs-lookup"><span data-stu-id="7edf6-111">Minor</span></span>       |
| <span data-ttu-id="7edf6-112">Version</span><span class="sxs-lookup"><span data-stu-id="7edf6-112">Version</span></span> | <span data-ttu-id="7edf6-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="7edf6-113">4.5.1</span></span>       |
| <span data-ttu-id="7edf6-114">Typ</span><span class="sxs-lookup"><span data-stu-id="7edf6-114">Type</span></span>    | <span data-ttu-id="7edf6-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="7edf6-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7edf6-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7edf6-116">Affected APIs</span></span>

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
