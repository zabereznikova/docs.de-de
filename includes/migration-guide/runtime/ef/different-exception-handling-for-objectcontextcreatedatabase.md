---
ms.openlocfilehash: 33ad1c044001e0a8d09708cc7a1f06e05cb307de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804048"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Unterschiedliche Ausnahmebehandlung für die Methoden „ObjectContext.CreateDatabase“ und „DbProviderServices.CreateDatabase“

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 versuchen <code>CreateDatabase</code>-Methoden, eine leere Datenbank zu löschen, wenn die Datenbankerstellung fehlgeschlagen ist. Wenn dieser Vorgang erfolgreich ist, wird die ursprüngliche <xref:System.Data.SqlClient.SqlException?displayProperty=name> weitergegeben (anstelle der <xref:System.InvalidOperationException?displayProperty=name>, die in .NET Framework 4.0 immer ausgelöst wurde).|
|Vorschlag|Beim Abfangen einer <xref:System.InvalidOperationException?displayProperty=name>-Ausnahme während der Ausführung von <xref:System.Data.Objects.ObjectContext.CreateDatabase> oder <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> sollten SQLExceptions-Ausnahmen nun ebenfalls abgefangen werden.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
