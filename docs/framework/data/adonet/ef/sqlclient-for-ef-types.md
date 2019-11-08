---
title: SqlClient für Entity Framework-Typen
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: d132583bba2520d37693be6c4b085cfa514003e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737847"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient für Entity Framework-Typen
Die Anbietermanifestdatei des .NET Framework-Datenanbieters für SQL Server (SqlClient) enthält eine Liste der primitiven Typen des Anbieters, die Facets für jeden Typ, die Zuordnungen zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell sowie die Höherstufungs- und Konvertierungsregeln zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell.  
  
 In der folgenden Tabelle werden die Typen für die SQL Server 2008, SQL Server 2005 und SQL Server 2000-Datenbanken beschrieben und erläutert, wie diese Typen konzeptionellen Modelltypen zugeordnet werden. Einige neue Typen wurden in neueren Versionen von SQL Server eingeführt und werden in älteren Versionen von SQL Server nicht unterstützt. Auf diese Typen wird in der folgenden Tabelle hingewiesen.  
  
|Anbietertyp<br /><br /> Name|Anbietertyp<br /><br /> Attribute|`EDMSimpleType`<br /><br /> Name|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|n/v|`Edm.Boolean`|n/v|  
|`tinyint`|n/v|`Edm.Byte`|n/v|  
|`smallint`|n/v|`Edm.Int16`|n/v|  
|`int`|n/v|`Edm.Int32`|n/v|  
|`bigint`|n/v|`Edm.Int64`|n/v|  
|`float`|n/v|`Edm.Double`|n/v|  
|`real`|n/v|`Edm.Double`|n/v|  
|`decimal`|n/v|`Edm.Decimal`|Präziser<br /><br /> -Minimal: 1<br /><br /> -Maximum: 38<br /><br /> -Standard: 18<br /><br /> -Konstant: false<br /><br /> Migen<br /><br /> -Minimalwert: 0<br /><br /> -Maximum: 38<br /><br /> -Standardwert: 0<br /><br /> -Konstant: false|  
|`numeric`|n/v|`Edm.Decimal`|Präziser<br /><br /> -Minimal: 1<br /><br /> -Maximum: 38<br /><br /> -Standard: 18<br /><br /> -Konstant: false<br /><br /> Migen<br /><br /> -Minimalwert: 0<br /><br /> -Maximum: 38<br /><br /> -Standardwert: 0<br /><br /> -Konstant: false|  
|`smallmoney`|n/v|`Edm.Decimal`|Präziser<br /><br /> -Standard: 10<br /><br /> -Konstant: true<br /><br /> Migen<br /><br /> -Standardwert: 4<br /><br /> -Konstant: true|  
|`money`|n/v|`Edm.Decimal`|Präziser<br /><br /> -Standardwert: 19<br /><br /> -Konstant: true<br /><br /> Migen<br /><br /> -Standardwert: 4<br /><br /> -Konstant: true|  
|`binary`|n/v|`Edm.Binary`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`varbinary`|n/v|`Edm.Binary`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`varbinary(max)`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.Binary`|MaxLength<br /><br /> -Standard: 214748364780<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`image`|n/v|`Edm.Binary`|MaxLength<br /><br /> -Standard: 2147483647<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`timestamp`|n/v|`Edm.Binary`|MaxLength<br /><br /> -Standardwert: 8<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`rowversion`|n/v|`Edm.Binary`|MaxLength<br /><br /> -Standardwert: 8<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`smalldatetime`|n/v|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 0<br /><br /> -Konstant: true|  
|`datetime`|n/v|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 3<br /><br /> -Konstant: true|  
|`date`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 0<br /><br /> -Konstant: false|  
|`time`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.Time`|Präziser<br /><br /> -Standardwert: 7<br /><br /> -Konstant: false|  
|`datetime2`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Präziser<br /><br /> -Standardwert: 7<br /><br /> -Konstant: false|  
|`datetimeoffset`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTimeOffset`|Präziser<br /><br /> -Standardwert: 7<br /><br /> -Konstant: false|  
|`nvarchar`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 4000<br /><br /> -Standard: 4000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`varchar`<br /><br /> Hinweis: dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`char`|n/v|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`nchar`|n/v|`Edm.String`|MaxLength<br /><br /> -Minimal: 1<br /><br /> -Maximum: 4000<br /><br /> -Standard: 4000<br /><br /> -Konstant: false<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standard: true<br /><br /> -Konstant: true|  
|`varchar`(`max`)|n/v|`Edm.String`|MaxLength<br /><br /> -Standard: 2147483647<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`nvarchar`(`max`)|n/v|`Edm.String`|MaxLength<br /><br /> -Standard: 1073741823<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`ntext`|Gleichwertig: false<br /><br /> Vergleichbare Reihenfolge: false|`Edm.String`|MaxLength<br /><br /> -Standard: 1073741823<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`text`|Gleichwertig: false<br /><br /> Vergleichbare Reihenfolge: false|`Edm.String`|MaxLength<br /><br /> -Standard: 2147483647<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
|`Unique`<br /><br /> `identifier`|Gleichwertig: true<br /><br /> Vergleichbare Reihenfolge: true|`Edm.Guid`|n/v|  
|`xml`|Gleichwertig: false<br /><br /> Vergleichbare Reihenfolge: false|`Edm.String`|MaxLength<br /><br /> -Standard: 1073741823<br /><br /> -Konstant: true<br /><br /> Unicode:<br /><br /> -Standard: true<br /><br /> -Konstant: true<br /><br /> FixedLength:<br /><br /> -Standardwert: false<br /><br /> -Konstant: true|  
  
## <a name="see-also"></a>Siehe auch

- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
