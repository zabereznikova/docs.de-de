---
ms.openlocfilehash: 23ba6064a283b47312a66f3636c2834a7d58106e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620189"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET versucht nun, unterbrochene SQL-Verbindungen automatisch wiederherzustellen

#### <a name="details"></a>Details

Ab .NET Framework 4.5.1 versucht .NET Framework, unterbrochene SQL-Verbindungen automatisch wiederherzustellen. Obwohl dies in der Regel dazu führt, dass Apps zuverlässiger werden, gibt es Grenzfälle, in denen eine App wissen muss, dass die Verbindung getrennt wurde, sodass sie bei der Wiederherstellung der Verbindung bestimmte Aktionen ausführen kann.

#### <a name="suggestion"></a>Vorschlag

Wenn dieses Feature aus Kompatibilitätsgründen nicht erwünscht ist, kann es durch Festlegen der <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName>-Eigenschaft einer Verbindungszeichenfolge (oder <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) auf 0 (null) deaktiviert werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5.1|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)></li></ul>|
