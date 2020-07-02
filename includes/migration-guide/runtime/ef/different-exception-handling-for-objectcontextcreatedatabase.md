---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620303"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
