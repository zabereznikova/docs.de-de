---
title: SqlClient für Entity Framework-Typen
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: bca2cc0e0d9f43c51c66080f3bd38c245ce94381
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156588"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient für Entity Framework-Typen

Die Anbietermanifestdatei des .NET Framework-Datenanbieters für SQL Server (SqlClient) enthält eine Liste der primitiven Typen des Anbieters, die Facets für jeden Typ, die Zuordnungen zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell sowie die Höherstufungs- und Konvertierungsregeln zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell.  
  
 In der folgenden Tabelle werden die Typen für die SQL Server 2008, SQL Server 2005 und SQL Server 2000-Datenbanken beschrieben und erläutert, wie diese Typen konzeptionellen Modelltypen zugeordnet werden. Einige neue Typen wurden in neueren Versionen von SQL Server eingeführt und werden in älteren Versionen von SQL Server nicht unterstützt. Auf diese Typen wird in der folgenden Tabelle hingewiesen.  
  
|Anbietertyp<br /><br /> name|Anbietertyp<br /><br /> attributes|`EDMSimpleType`<br /><br /> name|Facetten|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|–|`Edm.Boolean`|–|  
|`tinyint`|–|`Edm.Byte`|–|  
|`smallint`|–|`Edm.Int16`|–|  
|`int`|–|`Edm.Int32`|–|  
|`bigint`|–|`Edm.Int64`|–|  
|`float`|–|`Edm.Double`|–|  
|`real`|–|`Edm.Double`|–|  
|`decimal`|–|`Edm.Decimal`|Präziser<br /><br /> -Minimal: 1<br /><br /> -Maximum: 38<br /><br /> -Standard: 18<br /><br /> -Konstant: false<br /><br /> Skalierung:<br /><br /> -Minimalwert: 0<br /><br /> -Maximum: 38<br /><br /> -Standardwert: 0<br /><br /> -Konstant: false|  
|`numeric`|–|`Edm.Decimal`|Präziser<br /><br /> -Minimal: 1<br /><br /> -Maximum: 38<br /><br /> -Standard: 18<br /><br /> -Konstant: false<br /><br /> Skalierung:<br /><br /> -Minimalwert: 0<br /><br /> -Maximum: 38<br /><br /> -Standardwert: 0<br /><br /> -Konstant: false|  
|`smallmoney`|–|`Edm.Decimal`|Präziser<br /><br /> -Standard: 10<br /><br /> -Konstant: true<br /><br /> Skalierung:<br /><br /> -Standardwert: 4<br /><br /> -Konstant: true|  
|`money`|–|`Edm.Decimal`|Präziser<br /><br /> -Standardwert: 19<br /><br /> -Konstant: true<br /><br /> Skalierung:<br /><br /> -Standardwert: 4<br /><br /> -Konstant: true|  
|`binary`|–|`Edm.Binary`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`varbinary`|–|`Edm.Binary`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`varbinary(max)`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2000 nicht unterstützt.|–|`Edm.Binary`|MaxLength<br /><br /> -Standard: 214748364780<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`image`|–|`Edm.Binary`|MaxLength<br /><br /> -Standard: 2147483647<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`timestamp`|–|`Edm.Binary`|MaxLength<br /><br /> -Standardwert: 8<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`rowversion`|–|`Edm.Binary`|MaxLength<br /><br /> -Standardwert: 8<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`smalldatetime`|–|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 0<br /><br /> -Konstant: true|  
|`datetime`|–|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 3<br /><br /> -Konstant: true|  
|`date`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|–|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 0<br /><br /> -Konstant: false|  
|`time`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|–|`Edm.Time`|Präziser<br /><br /> -Standardwert: 7<br /><br /> -Konstant: false|  
|`datetime2`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|–|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 7<br /><br /> -Konstant: false|  
|`datetimeoffset`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|–|`Edm.DateTimeOffset`|Präziser<br /><br /> -Standardwert: 7<br /><br /> -Konstant: false|  
|`nvarchar`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2000 nicht unterstützt.|–|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 4000<br /><br /> -Standard: 4000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`varchar`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2000 nicht unterstützt.|–|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`char`|–|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`nchar`|–|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 4000<br /><br /> -Standard: 4000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`varchar`(`max`)|–|`Edm.String`|MaxLength<br /><br /> -Standard: 2147483647<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`nvarchar`(`max`)|–|`Edm.String`|MaxLength<br /><br /> -Standard: 1073741823<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`ntext`|Gleichwertig: false<br /><br /> Vergleichbare Reihenfolge: false|`Edm.String`|MaxLength<br /><br /> -Standard: 1073741823<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`text`|Gleichwertig: false<br /><br /> Vergleichbare Reihenfolge: false|`Edm.String`|MaxLength<br /><br /> -Standard: 2147483647<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`Unique`<br /><br /> `identifier`|Gleichwertig: true<br /><br /> Vergleichbare Reihenfolge: true|`Edm.Guid`|–|  
|`xml`|Gleichwertig: false<br /><br /> Vergleichbare Reihenfolge: false|`Edm.String`|MaxLength<br /><br /> -Standard: 1073741823<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
  
## <a name="see-also"></a>Weitere Informationen

- [CSDL-, SSDL- und MSL-Spezifikationen](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
