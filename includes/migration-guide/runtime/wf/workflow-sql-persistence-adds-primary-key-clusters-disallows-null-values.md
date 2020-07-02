---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621246"
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
