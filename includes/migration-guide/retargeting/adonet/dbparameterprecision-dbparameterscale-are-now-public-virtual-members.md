---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616113"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member

#### <a name="details"></a>Details

<xref:System.Data.Common.DbParameter.Precision> und <xref:System.Data.Common.DbParameter.Scale> werden als öffentliche virtuelle Eigenschaften implementiert. Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie einen ADO.NET-Datenbankanbieter neu erstellen, erfordern diese Unterschiede die Anwendung des Schlüsselworts „override“ auf die Eigenschaften „Precision“ und „Scale“. Dies ist nur beim erneuten Erstellen von Komponenten erforderlich. Vorhandene Binärdateien funktionieren weiterhin.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
