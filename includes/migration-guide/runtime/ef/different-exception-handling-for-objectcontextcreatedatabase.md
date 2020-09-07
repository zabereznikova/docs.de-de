---
ms.openlocfilehash: 8c593fa6490451c6236f0d4390f09d4e9e4f0cbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496523"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Unterschiedliche Ausnahmebehandlung für die Methoden „ObjectContext.CreateDatabase“ und „DbProviderServices.CreateDatabase“

#### <a name="details"></a>Details

Ab .NET Framework 4.5 versuchen <code>CreateDatabase</code>-Methoden, eine leere Datenbank zu löschen, wenn die Datenbankerstellung fehlgeschlagen ist. Wenn dieser Vorgang erfolgreich ist, wird die ursprüngliche <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> weitergegeben (anstelle der <xref:System.InvalidOperationException?displayProperty=fullName>, die in .NET Framework 4.0 immer ausgelöst wurde).

#### <a name="suggestion"></a>Vorschlag

Beim Abfangen einer <xref:System.InvalidOperationException?displayProperty=fullName>-Ausnahme während der Ausführung von <xref:System.Data.Objects.ObjectContext.CreateDatabase> oder <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> sollten SQLExceptions-Ausnahmen nun ebenfalls abgefangen werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>
- <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`
- `M:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)`

-->
