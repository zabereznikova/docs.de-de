---
ms.openlocfilehash: 1721d32f8cdc9b6ea4b4732e38afa56a8a532600
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234731"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member

|   |   |
|---|---|
|Details|<xref:System.Data.Common.DbParameter.Precision> und <xref:System.Data.Common.DbParameter.Scale> werden als öffentliche virtuelle Eigenschaften implementiert. Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.|
|Vorschlag|Wenn Sie einen ADO.NET-Datenbankanbieter neu erstellen, erfordern diese Unterschiede die Anwendung des Schlüsselworts „override“ auf die Eigenschaften „Precision“ und „Scale“. Dies ist nur beim erneuten Erstellen von Komponenten erforderlich. Vorhandene Binärdateien funktionieren weiterhin.|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType></li></ul>|
