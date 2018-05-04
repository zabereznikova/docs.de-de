---
title: 'Entity Data Model: Primitive Datentypen'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: 3e99f65c57cf0e0ee4cbccc79d5819d39b9ee60b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="entity-data-model-primitive-data-types"></a>Entity Data Model: Primitive Datentypen
Das Entity Data Model (EDM) unterstützt eine Reihe abstrakter primitiver Datentypen (z. B. eine Zeichenfolge, boolescher Wert, Int32, usw.), mit denen definieren [Eigenschaften](../../../../docs/framework/data/adonet/property.md) in einem konzeptionellen Modell. Diese primitiven Datentypen sind Proxys für tatsächliche primitive Datentypen, die in der Speicher- oder Hostingumgebung unterstützt werden, z. B. eine SQL Server-Datenbank oder die Common Language Runtime (CLR). Das EDM definiert keine Semantik von Vorgängen oder Konvertierungen für primitive Datentypen. Diese Semantik wird von der Speicher- oder Hostingumgebung definiert. In der Regel werden primitive Datentypen im EDM entsprechenden primitiven Datentypen in der Speicher- oder Hostingumgebung zugeordnet. Informationen wie das Entity Framework primitive Datentypen im EDM in SQL Server-Datentypen zugeordnet werden, finden Sie unter [SqlClient für Entity Framework-Typen](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
>  Das EDM unterstützt keine Auflistungen primitiver Datentypen.  
  
 Informationen zu strukturierten Datentypen im EDM finden Sie unter [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und [komplexen Typ](../../../../docs/framework/data/adonet/complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Im Entity Data Model unterstützte primitive Datentypen  
 In der nachfolgenden Tabelle werden die vom EDM unterstützten primitiven Datentypen aufgeführt. Die Tabelle enthält außerdem die [Facets](../../../../docs/framework/data/adonet/facet.md) , kann auf jeden primitiven Datentyp angewendet werden.  
  
|Primitiver Datentyp|Beschreibung|Anwendbare Facets|  
|-------------------------|-----------------|-----------------------|  
|Binär|Enthält Binärdaten.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|Enthält den Wert `true` oder `false`.|Nullable, Default|  
|Byte|Enthält einen 8-Bit-Ganzzahlwert ohne Vorzeichen.|Precision, Nullable, Default|  
|DateTime|Stellt ein Datum und eine Uhrzeit dar.|Precision, Nullable, Default|  
|DateTimeOffset|Enthält ein Datum und eine Uhrzeit als Offset in Minuten von GMT.|Precision, Nullable, Default|  
|Decimal|Enthält einen numerischen Wert mit fester Genauigkeit und festen Dezimalstellen.|Precision, Nullable, Default|  
|Double|Enthält eine Gleitkommazahl mit einer Genauigkeit von 15 Stellen.|Precision, Nullable, Default|  
|Float|Enthält eine Gleitkommazahl mit siebenstelliger Genauigkeit.|Precision, Nullable, Default|  
|Guid|Enthält einen eindeutigen 16-Byte-Bezeichner.|Precision, Nullable, Default|  
|Int16|Enthält einen 16-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int32|Enthält einen 32-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int64|Enthält einen 64-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|SByte|Enthält einen 8-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Zeichenfolge|Enthält Zeichendaten.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|zeit|Enthält eine Uhrzeit.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
