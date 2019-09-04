---
title: SqlClient für Entity Framework-Typen
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: af3a4eea08dd3f4e1a134fcb66d92bc4a3b077c7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248382"
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
|`decimal`|n/v|`Edm.Decimal`|Präziser<br /><br /> Garantien 1<br /><br /> Maximale 38<br /><br /> Vorgegebene 18<br /><br /> Bend False<br /><br /> Migen<br /><br /> Garantien 0<br /><br /> Maximale 38<br /><br /> Vorgegebene 0<br /><br /> Bend False|  
|`numeric`|n/v|`Edm.Decimal`|Präziser<br /><br /> Garantien 1<br /><br /> Maximale 38<br /><br /> Vorgegebene 18<br /><br /> Bend False<br /><br /> Migen<br /><br /> Garantien 0<br /><br /> Maximale 38<br /><br /> Vorgegebene 0<br /><br /> Bend False|  
|`smallmoney`|n/v|`Edm.Decimal`|Präziser<br /><br /> Vorgegebene 10<br /><br /> Bend True<br /><br /> Migen<br /><br /> Vorgegebene 4<br /><br /> Bend True|  
|`money`|n/v|`Edm.Decimal`|Präziser<br /><br /> Vorgegebene 19<br /><br /> Bend True<br /><br /> Migen<br /><br /> Vorgegebene 4<br /><br /> Bend True|  
|`binary`|n/v|`Edm.Binary`|MaxLength<br /><br /> Garantien 1<br /><br /> Maximale 8000<br /><br /> Vorgegebene 8000<br /><br /> Bend False<br /><br /> FixedLength:<br /><br /> Vorgegebene True<br /><br /> Bend True|  
|`varbinary`|n/v|`Edm.Binary`|MaxLength<br /><br /> Garantien 1<br /><br /> Maximale 8000<br /><br /> Vorgegebene 8000<br /><br /> Bend False<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`varbinary(max)`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.Binary`|MaxLength<br /><br /> Vorgegebene 214748364780<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`image`|n/v|`Edm.Binary`|MaxLength<br /><br /> Vorgegebene 2147483647<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`timestamp`|n/v|`Edm.Binary`|MaxLength<br /><br /> Vorgegebene 8<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene True<br /><br /> Bend True|  
|`rowversion`|n/v|`Edm.Binary`|MaxLength<br /><br /> Vorgegebene 8<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene True<br /><br /> Bend True|  
|`smalldatetime`|n/v|`Edm.DateTime`|Präziser<br /><br /> Vorgegebene 0<br /><br /> Bend True|  
|`datetime`|n/v|`Edm.DateTime`|Präziser<br /><br /> Vorgegebene 3<br /><br /> Bend True|  
|`date`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Präziser<br /><br /> Vorgegebene 0<br /><br /> Bend False|  
|`time`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.Time`|Präziser<br /><br /> Vorgegebene 7<br /><br /> Bend False|  
|`datetime2`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Präziser<br /><br /> Vorgegebene 7<br /><br /> Bend False|  
|`datetimeoffset`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTimeOffset`|Präziser<br /><br /> Vorgegebene 7<br /><br /> Bend False|  
|`nvarchar`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.String`|MaxLength<br /><br /> Garantien 1<br /><br /> Maximale 4000<br /><br /> Vorgegebene 4000<br /><br /> Bend False<br /><br /> Unicode:<br /><br /> Vorgegebene True<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`varchar`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.String`|MaxLength<br /><br /> Garantien 1<br /><br /> Maximale 8000<br /><br /> Vorgegebene 8000<br /><br /> Bend False<br /><br /> Unicode:<br /><br /> Vorgegebene False<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`char`|n/v|`Edm.String`|MaxLength<br /><br /> Garantien 1<br /><br /> Maximale 8000<br /><br /> Vorgegebene 8000<br /><br /> Bend False<br /><br /> Unicode:<br /><br /> Vorgegebene False<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene True<br /><br /> Bend True|  
|`nchar`|n/v|`Edm.String`|MaxLength<br /><br /> Garantien 1<br /><br /> Maximale 4000<br /><br /> Vorgegebene 4000<br /><br /> Bend False<br /><br /> Unicode:<br /><br /> Vorgegebene True<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene True<br /><br /> Bend True|  
|`varchar`(`max`)|n/v|`Edm.String`|MaxLength<br /><br /> Vorgegebene 2147483647<br /><br /> Bend True<br /><br /> Unicode:<br /><br /> Vorgegebene False<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`nvarchar`(`max`)|n/v|`Edm.String`|MaxLength<br /><br /> Vorgegebene 1073741823<br /><br /> Bend True<br /><br /> Unicode:<br /><br /> Vorgegebene True<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`ntext`|Gleichwertig: False<br /><br /> Vergleichbare Reihenfolge: False|`Edm.String`|MaxLength<br /><br /> Vorgegebene 1073741823<br /><br /> Bend True<br /><br /> Unicode:<br /><br /> Vorgegebene False<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`text`|Gleichwertig: False<br /><br /> Vergleichbare Reihenfolge: False|`Edm.String`|MaxLength<br /><br /> Vorgegebene 2147483647<br /><br /> Bend True<br /><br /> Unicode:<br /><br /> Vorgegebene False<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
|`Unique`<br /><br /> `identifier`|Gleichwertig: True<br /><br /> Vergleichbare Reihenfolge: True|`Edm.Guid`|n/v|  
|`xml`|Gleichwertig: False<br /><br /> Vergleichbare Reihenfolge: False|`Edm.String`|MaxLength<br /><br /> Vorgegebene 1073741823<br /><br /> Bend True<br /><br /> Unicode:<br /><br /> Vorgegebene True<br /><br /> Bend True<br /><br /> FixedLength:<br /><br /> Vorgegebene False<br /><br /> Bend True|  
  
## <a name="see-also"></a>Siehe auch

- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](./language-reference/csdl-ssdl-and-msl-specifications.md)
