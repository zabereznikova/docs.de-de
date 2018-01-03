---
title: "SqlClient für Entity Framework-Typen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b04a7199fefc5df93d5e3472163d16c66e9279c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient für Entity Framework-Typen
Die Anbietermanifestdatei des .NET Framework-Datenanbieters für SQL Server (SqlClient) enthält eine Liste der primitiven Typen des Anbieters, die Facets für jeden Typ, die Zuordnungen zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell sowie die Höherstufungs- und Konvertierungsregeln zwischen den primitiven Typen von konzeptionellem Modell und Speichermodell.  
  
 Die folgende Tabelle beschreibt die Typen für SQL Server 2008, [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], und [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] Modelltypen für Datenbanken und wie diese Typen konzeptionellen zugeordnet. Einige neue Typen wurden in neueren Versionen von SQL Server eingeführt und werden in älteren Versionen von SQL Server nicht unterstützt. Auf diese Typen wird in der folgenden Tabelle hingewiesen.  
  
|Anbietertyp<br /><br /> Name|Anbietertyp<br /><br /> Attribute|`EDMSimpleType`<br /><br /> Name|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|nicht verfügbar|`Edm.Boolean`|nicht verfügbar|  
|`tinyint`|nicht verfügbar|`Edm.Byte`|nicht verfügbar|  
|`smallint`|nicht verfügbar|`Edm.Int16`|nicht verfügbar|  
|`int`|nicht verfügbar|`Edm.Int32`|nicht verfügbar|  
|`bigint`|nicht verfügbar|`Edm.Int64`|nicht verfügbar|  
|`float`|nicht verfügbar|`Edm.Double`|nicht verfügbar|  
|`real`|nicht verfügbar|`Edm.Double`|nicht verfügbar|  
|`decimal`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 38<br /><br /> -Standard: 18<br /><br /> -Konstante: "false"<br /><br /> Skalierung:<br /><br /> -Mindestens: 0<br /><br /> -Maximale: 38<br /><br /> -Standard: 0<br /><br /> -Konstante: "false"|  
|`numeric`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 38<br /><br /> -Standard: 18<br /><br /> -Konstante: "false"<br /><br /> Skalierung:<br /><br /> -Mindestens: 0<br /><br /> -Maximale: 38<br /><br /> -Standard: 0<br /><br /> -Konstante: "false"|  
|`smallmoney`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> -Standard: 10<br /><br /> -Konstanten: True<br /><br /> Skalierung:<br /><br /> -Standard: 4<br /><br /> -Konstanten: True|  
|`money`|n/v|`Edm.Decimal`|Genauigkeit:<br /><br /> -Standard: 19<br /><br /> -Konstanten: True<br /><br /> Skalierung:<br /><br /> -Standard: 4<br /><br /> -Konstanten: True|  
|`binary`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstante: "false"<br /><br /> FixedLength:<br /><br /> -Standard: True<br /><br /> -Konstanten: True|  
|`varbinary`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstante: "false"<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`varbinary(max)`<br /><br /> Hinweis: Dieser Typ wird nicht unterstützt [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Standard: 214748364780<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`image`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Standard: 2147483647<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`timestamp`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Standard: 8<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: True<br /><br /> -Konstanten: True|  
|`rowversion`|n/v|`Edm.Binary`|MaxLength:<br /><br /> -Standard: 8<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: True<br /><br /> -Konstanten: True|  
|`smalldatetime`|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> -Standard: 0<br /><br /> -Konstanten: True|  
|`datetime`|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> -Standard: 3<br /><br /> -Konstanten: True|  
|`date`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> -Standard: 0<br /><br /> -Konstante: "false"|  
|`time`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.Time`|Genauigkeit:<br /><br /> -Standard: 7<br /><br /> -Konstante: "false"|  
|`datetime2`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTime`|Genauigkeit:<br /><br /> -Standard: 7<br /><br /> -Konstante: "false"|  
|`datetimeoffset`<br /><br /> Hinweis: Dieser Typ wird in SQL Server 2005 und SQL Server 2000 nicht unterstützt.|n/v|`Edm.DateTimeOffset`|Genauigkeit:<br /><br /> -Standard: 7<br /><br /> -Konstante: "false"|  
|`nvarchar`<br /><br /> Hinweis: Dieser Typ wird nicht unterstützt [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|n/v|`Edm.String`|MaxLength:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 4000<br /><br /> -Standard: 4000<br /><br /> -Konstante: "false"<br /><br /> Unicode:<br /><br /> -Standard: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`varchar`<br /><br /> Hinweis: Dieser Typ wird nicht unterstützt [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|n/v|`Edm.String`|MaxLength:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstante: "false"<br /><br /> Unicode:<br /><br /> -Standard: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`char`|n/v|`Edm.String`|MaxLength:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 8000<br /><br /> -Standard: 8000<br /><br /> -Konstante: "false"<br /><br /> Unicode:<br /><br /> -Standard: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: True<br /><br /> -Konstanten: True|  
|`nchar`|n/v|`Edm.String`|MaxLength:<br /><br /> -Minimum: 1<br /><br /> -Maximale: 4000<br /><br /> -Standard: 4000<br /><br /> -Konstante: "false"<br /><br /> Unicode:<br /><br /> -Standard: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: True<br /><br /> -Konstanten: True|  
|`varchar`(`max`)|n/v|`Edm.String`|MaxLength:<br /><br /> -Standard: 2147483647<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> -Standard: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`nvarchar`(`max`)|n/v|`Edm.String`|MaxLength:<br /><br /> -Standard: 1073741823<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> -Standard: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`ntext`|Gleichberechtigt-vergleichbar sein: "false"<br /><br /> Reihenfolge vergleichbar: "false"|`Edm.String`|MaxLength:<br /><br /> -Standard: 1073741823<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> -Standard: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`text`|Gleichberechtigt-vergleichbar sein: "false"<br /><br /> Reihenfolge vergleichbar: "false"|`Edm.String`|MaxLength:<br /><br /> -Standard: 2147483647<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> -Standard: False<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
|`Unique`<br /><br /> `identifier`|Gleichberechtigt-vergleichbar sein: "true"<br /><br /> Reihenfolge vergleichbar: "true"|`Edm.Guid`|n/v|  
|`xml`|Gleichberechtigt-vergleichbar sein: "false"<br /><br /> Reihenfolge vergleichbar: "false"|`Edm.String`|MaxLength:<br /><br /> -Standard: 1073741823<br /><br /> -Konstanten: True<br /><br /> Unicode:<br /><br /> -Standard: True<br /><br /> -Konstanten: True<br /><br /> FixedLength:<br /><br /> -Standard: False<br /><br /> -Konstanten: True|  
  
## <a name="see-also"></a>Siehe auch  
 [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
