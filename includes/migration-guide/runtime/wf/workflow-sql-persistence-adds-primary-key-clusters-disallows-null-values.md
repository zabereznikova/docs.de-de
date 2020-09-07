---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497790"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>Über die SQL-Workflowpersistenz werden Primärschlüsselcluster hinzugefügt und NULL-Werte in einigen Spalten nicht zugelassen

#### <a name="details"></a>Details

Ab .NET Framework 4.7 verwenden die vom SqlWorkflowInstanceStoreSchema.sql-Skript erstellten Tabellen für SQL Workflow Instance Store (SWIS) Primärschlüsselcluster. Aus diesem Grund unterstützen Identitäten keine <code>null</code>-Werte. Diese Änderung hat keine Auswirkungen auf SWIS. Die Updates wurden erstellt, um die Transaktionsreplikation mit SQL Server zu unterstützen.

#### <a name="suggestion"></a>Vorschlag

Die SQL-Datei „SqlWorkflowInstanceStoreSchemaUpgrade.sql“ muss auf bereits vorgenommene Installationen angewendet werden, damit diese Änderung vorgenommen wird. Bei neuen Datenbankinstallationen werden die Änderungen automatisch vorgenommen.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
