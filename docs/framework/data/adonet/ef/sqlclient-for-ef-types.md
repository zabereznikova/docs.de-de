---
title: SqlClient für Entity Framework-Typen
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: 7e3abe86128670656bfb2607b8531c9ceb0e4134
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662118"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient für Entity Framework-Typen
Die Anbietermanifestdatei des .NET Framework-Datenanbieters für SQL Server (SqlClient) enthält eine Liste der primitiven Typen des Anbieters, die Facets für jeden Typ, die Zuordnungen zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell sowie die Höherstufungs- und Konvertierungsregeln zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell.  
  
 Die folgende Tabelle beschreibt die Typen für SQL Server 2008, SQL Server 2005 und SQL Server 2000-Datenbanken und deren Zuordnung zu Typen des konzeptionellen Modells. Einige neue Typen wurden in neueren Versionen von SQL Server eingeführt und werden in älteren Versionen von SQL Server nicht unterstützt. Auf diese Typen wird in der folgenden Tabelle hingewiesen.  
  
|Anbietertyp<br /><br /> Name|Anbietertyp<br /><br /> Attribute|`EDMSimpleType`<br /><br /> Name|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|n/v|`Edm.Boolean`|n/v|  
|`tinyint`|n/v|`Edm.Byte`|n/v|  
|`smallint`|n/v|`Edm.Int16`|n/v|  
|`int`|n/v|`Edm.Int32`|n/v|  
|`bigint`|n/v|`Edm.Int64`|n/v|  
|`float`|n/v|`Edm.Double`|n/v|  
|`real`|n/v|`Edm.Double`|n/v|  
|`decimal`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 38<br /><br /> – Default: 18<br /><br /> -Konstanten: False<br /><br /> Skalierung:<br /><br /> -Mindestens: 0<br /><br /> -Maximum: 38<br /><br /> – Default: 0<br /><br /> -Konstanten: False|  
|`numeric`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 38<br /><br /> – Default: 18<br /><br /> -Konstanten: False<br /><br /> Skalierung:<br /><br /> -Mindestens: 0<br /><br /> -Maximum: 38<br /><br /> – Default: 0<br /><br /> -Konstanten: False|  
|`smallmoney`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> – Default: 10<br /><br /> -Konstanten: True<br /><br /> Skalierung:<br /><br /> – Default: 4<br /><br /> -Konstanten: True|  
|`money`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> – Default: 19<br /><br /> -Konstanten: True<br /><br /> Skalierung:<br /><br /> – Default: 4<br /><br /> -Konstanten: True|  
|`binary`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 8000<br /><br /> – Default: 8000<br /><br /> -Konstanten: False<br /><br /> FixedLength:<br /><br /> – Default: True<br /><br /> -Konstanten: True|  
|`varbinary`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 8000<br /><br /> – Default: 8000<br /><br /> -Konstanten: False<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`varbinary(max)`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.Binary`|MaxLength:<br /><br /> – Default: 214748364780<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`image`|n/v|`Edm.Binary`|MaxLength:<br /><br /> – Default: 2147483647<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`timestamp`|n/v|`Edm.Binary`|MaxLength:<br /><br /> – Default: 8<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: True<br /><br /> -Konstanten: True|  
|`rowversion`|n/v|`Edm.Binary`|MaxLength:<br /><br /> – Default: 8<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: True<br /><br /> -Konstanten: True|  
|`smalldatetime`|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> – Default: 0<br /><br /> -Konstanten: True|  
|`datetime`|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> – Default: 3<br /><br /> -Konstanten: True|  
|`date`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> – Default: 0<br /><br /> -Konstanten: False|  
|`time`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.Time`|Genauigkeit:<br /><br /> – Default: 7<br /><br /> -Konstanten: False|  
|`datetime2`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> – Default: 7<br /><br /> -Konstanten: False|  
|`datetimeoffset`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTimeOffset`|Genauigkeit:<br /><br /> – Default: 7<br /><br /> -Konstanten: False|  
|`nvarchar`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.String`|MaxLength:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 4000<br /><br /> – Default: 4000<br /><br /> -Konstanten: False<br /><br /> Unicode:<br /><br /> – Default: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`varchar`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2000 nicht unterstützt.|n/v|`Edm.String`|MaxLength:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 8000<br /><br /> – Default: 8000<br /><br /> -Konstanten: False<br /><br /> Unicode:<br /><br /> – Default: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`char`|n/v|`Edm.String`|MaxLength:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 8000<br /><br /> – Default: 8000<br /><br /> -Konstanten: False<br /><br /> Unicode:<br /><br /> – Default: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: True<br /><br /> -Konstanten: True|  
|`nchar`|n/v|`Edm.String`|MaxLength:<br /><br /> -Mindestens: 1<br /><br /> -Maximum: 4000<br /><br /> – Default: 4000<br /><br /> -Konstanten: False<br /><br /> Unicode:<br /><br /> – Default: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: True<br /><br /> -Konstanten: True|  
|`varchar`(`max`)|n/v|`Edm.String`|MaxLength:<br /><br /> – Default: 2147483647<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> – Default: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`nvarchar`(`max`)|n/v|`Edm.String`|MaxLength:<br /><br /> – Default: 1073741823<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> – Default: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`ntext`|Gleich vergleichbar: False<br /><br /> Die Reihenfolge vergleichbar: False|`Edm.String`|MaxLength:<br /><br /> – Default: 1073741823<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> – Default: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`text`|Gleich vergleichbar: False<br /><br /> Die Reihenfolge vergleichbar: False|`Edm.String`|MaxLength:<br /><br /> – Default: 2147483647<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> – Default: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
|`Unique`<br /><br /> `identifier`|Gleich vergleichbar: True<br /><br /> Die Reihenfolge vergleichbar: True|`Edm.Guid`|n/v|  
|`xml`|Gleich vergleichbar: False<br /><br /> Die Reihenfolge vergleichbar: False|`Edm.String`|MaxLength:<br /><br /> – Default: 1073741823<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> – Default: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> – Default: False<br /><br /> -Konstanten: True|  
  
## <a name="see-also"></a>Siehe auch

- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
