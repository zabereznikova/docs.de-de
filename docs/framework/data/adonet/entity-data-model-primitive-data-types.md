---
title: 'Entity Data Model: primitive Datentypen'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: 044a0ed981bb9cda3550fb3a3a9f1cb9bff96f25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142648"
---
# <a name="entity-data-model-primitive-data-types"></a>Entity Data Model: primitive Datentypen
Das Entity Data Model (EDM) unterstützt einen Satz von abstrakten primitiven Datentypen (z. B. eine Zeichenfolge, boolescher Wert, Int32 und So weiter), die verwendet werden, um zu definieren [Eigenschaften](../../../../docs/framework/data/adonet/property.md) in einem konzeptionellen Modell. Diese primitiven Datentypen sind Proxys für tatsächliche primitive Datentypen, die in der Speicher- oder Hostingumgebung unterstützt werden, z. B. eine SQL Server-Datenbank oder die Common Language Runtime (CLR). Das EDM definiert keine Semantik von Vorgängen oder Konvertierungen für primitive Datentypen. Diese Semantik wird von der Speicher- oder Hostingumgebung definiert. In der Regel werden primitive Datentypen im EDM entsprechenden primitiven Datentypen in der Speicher- oder Hostingumgebung zugeordnet. Informationen dazu, wie das Entity Framework primitive Typen im EDM in SQL Server-Datentypen zuordnet, finden Sie unter [SqlClient für Entity Framework-Typen](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
>  Das EDM unterstützt keine Auflistungen primitiver Datentypen.  
  
 Weitere Informationen zu strukturierten Datentypen im EDM finden Sie unter [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und [komplexen Typ](../../../../docs/framework/data/adonet/complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Im Entity Data Model unterstützte primitive Datentypen  
 In der nachfolgenden Tabelle werden die vom EDM unterstützten primitiven Datentypen aufgeführt. Die Tabelle enthält außerdem die [Facets](../../../../docs/framework/data/adonet/facet.md) , die auf jeden primitiven Datentyp angewendet werden kann.  
  
|Primitiver Datentyp|Beschreibung|Anwendbare Facets|  
|-------------------------|-----------------|-----------------------|  
|Binär|Enthält Binärdaten.|MaxLength, FixedLength, Nullable, Default|  
|Boolesch|Enthält den Wert `true` oder `false`.|Nullable, Default|  
|Byte|Enthält einen 8-Bit-Ganzzahlwert ohne Vorzeichen.|Precision, Nullable, Default|  
|DateTime|Stellt ein Datum und eine Uhrzeit dar.|Precision, Nullable, Default|  
|DateTimeOffset|Enthält ein Datum und eine Uhrzeit als Offset in Minuten von GMT.|Precision, Nullable, Default|  
|Decimal|Enthält einen numerischen Wert mit fester Genauigkeit und festen Dezimalstellen.|Precision, Nullable, Default|  
|Double|Enthält eine Gleitkommazahl mit einer Genauigkeit von 15 Stellen.|Precision, Nullable, Default|  
|Float|Enthält eine Gleitkommazahl mit siebenstelliger Genauigkeit.|Precision, Nullable, Default|  
|GUID|Enthält einen eindeutigen 16-Byte-Bezeichner.|Precision, Nullable, Default|  
|Int16|Enthält einen 16-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int32|Enthält einen 32-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int64|Enthält einen 64-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|SByte|Enthält einen 8-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Zeichenfolge|Enthält Zeichendaten.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|zeit|Enthält eine Uhrzeit.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
