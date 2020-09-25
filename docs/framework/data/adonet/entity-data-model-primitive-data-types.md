---
title: 'Entity Data Model: primitive Datentypen'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: 4d52f50dec44c7d667dfedc10a2c9c25fcde8917
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194816"
---
# <a name="entity-data-model-primitive-data-types"></a>Entity Data Model: primitive Datentypen

Der Entity Data Model (EDM) unterstützt einen Satz abstrakter primitiver Datentypen (z. b. String, Boolean, Int32 usw.), die verwendet werden, um [Eigenschaften](property.md) in einem konzeptionellen Modell zu definieren. Diese primitiven Datentypen sind Proxys für tatsächliche primitive Datentypen, die in der Speicher- oder Hostingumgebung unterstützt werden, z. B. eine SQL Server-Datenbank oder die Common Language Runtime (CLR). Das EDM definiert keine Semantik von Vorgängen oder Konvertierungen für primitive Datentypen. Diese Semantik wird von der Speicher- oder Hostingumgebung definiert. In der Regel werden primitive Datentypen im EDM entsprechenden primitiven Datentypen in der Speicher- oder Hostingumgebung zugeordnet. Informationen dazu, wie die Entity Framework primitive Typen im EDM SQL Server Datentypen zuordnet, finden Sie unter [SqlClient für Entity frameworktypes](./ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
> Das EDM unterstützt keine Auflistungen primitiver Datentypen.  
  
 Informationen zu strukturierten Datentypen im EDM finden Sie unter [Entitätstyp](entity-type.md) und [komplexer Typ](complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Im Entity Data Model unterstützte primitive Datentypen  

 In der nachfolgenden Tabelle werden die vom EDM unterstützten primitiven Datentypen aufgeführt. In der Tabelle werden auch die [Facetten](facet.md) aufgelistet, die auf jeden primitiven Datentyp angewendet werden können.  
  
|Primitiver Datentyp|Beschreibung|Anwendbare Facets|  
|-------------------------|-----------------|-----------------------|  
|Binary|Enthält Binärdaten.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|Enthält den Wert `true` oder `false`.|Nullable, Default|  
|Byte|Enthält einen 8-Bit-Ganzzahlwert ohne Vorzeichen.|Precision, Nullable, Default|  
|Datetime|Stellt ein Datum und eine Uhrzeit dar.|Precision, Nullable, Default|  
|DateTimeOffset|Enthält ein Datum und eine Uhrzeit als Offset in Minuten von GMT.|Precision, Nullable, Default|  
|Decimal|Enthält einen numerischen Wert mit fester Genauigkeit und festen Dezimalstellen.|Precision, Nullable, Default|  
|Doppelt|Enthält eine Gleitkommazahl mit einer Genauigkeit von 15 Stellen.|Precision, Nullable, Default|  
|Float|Enthält eine Gleitkommazahl mit siebenstelliger Genauigkeit.|Precision, Nullable, Default|  
|Guid|Enthält einen eindeutigen 16-Byte-Bezeichner.|Precision, Nullable, Default|  
|Int16|Enthält einen 16-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int32|Enthält einen 32-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int64|Enthält einen 64-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|SByte|Enthält einen 8-Bit-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|String|Enthält Zeichendaten.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|Time|Enthält eine Uhrzeit.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
