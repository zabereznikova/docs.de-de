---
title: "Entity Data Model: Primitive Datentypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Entity Data Model: Primitive Datentypen
Das Entity Data Model \(EDM\) unterstützt eine Reihe abstrakter primitiver Datentypen \(z. B. String, Boolean oder Int32\), mit denen [Eigenschaften](../../../../docs/framework/data/adonet/property.md) in einem konzeptionellen Modell definiert werden.  Diese primitiven Datentypen sind Proxys für tatsächliche primitive Datentypen, die in der Speicher\- oder Hostingumgebung unterstützt werden, z. B. eine SQL Server\-Datenbank oder die Common Language Runtime \(CLR\).  Das EDM definiert keine Semantik von Vorgängen oder Konvertierungen für primitive Datentypen. Diese Semantik wird von der Speicher\- oder Hostingumgebung definiert.  In der Regel werden primitive Datentypen im EDM entsprechenden primitiven Datentypen in der Speicher\- oder Hostingumgebung zugeordnet.  Informationen darüber, wie das Entity Framework primitive Typen im EDM SQL Server\-Datentypen zuordnet, finden Sie unter [SqlClient für Entity Framework\-Typen](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
>  Das EDM unterstützt keine Auflistungen primitiver Datentypen.  
  
 Informationen zu strukturierten Datentypen im EDM finden Sie unter [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und [komplexer Typ](../../../../docs/framework/data/adonet/complex-type.md).  
  
## Im Entity Data Model unterstützte primitive Datentypen  
 In der nachfolgenden Tabelle werden die vom EDM unterstützten primitiven Datentypen aufgeführt.  In der Tabelle werden auch die [Facets](../../../../docs/framework/data/adonet/facet.md) aufgeführt, die auf jeden primitiven Datentyp angewendet werden können.  
  
|Primitiver Datentyp|Beschreibung|Anwendbare Facets|  
|-------------------------|------------------|-----------------------|  
|Binär|Enthält Binärdaten.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|Enthält den Wert `true` oder `false`.|Nullable, Default|  
|Byte|Enthält einen 8\-Bit\-Ganzzahlwert ohne Vorzeichen.|Precision, Nullable, Default|  
|DateTime|Stellt ein Datum und eine Uhrzeit dar.|Precision, Nullable, Default|  
|DateTimeOffset|Enthält ein Datum und eine Uhrzeit als Offset in Minuten von GMT.|Precision, Nullable, Default|  
|Decimal|Enthält einen numerischen Wert mit fester Genauigkeit und festen Dezimalstellen.|Precision, Nullable, Default|  
|Double|Enthält eine Gleitkommazahl mit einer Genauigkeit von 15 Stellen.|Precision, Nullable, Default|  
|Float|Enthält eine Gleitkommazahl mit siebenstelliger Genauigkeit.|Precision, Nullable, Default|  
|Guid|Enthält einen eindeutigen 16\-Byte\-Bezeichner.|Precision, Nullable, Default|  
|Int16|Enthält einen 16\-Bit\-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int32|Enthält einen 32\-Bit\-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Int64|Enthält einen 64\-Bit\-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|SByte|Enthält einen 8\-Bit\-Ganzzahlwert mit Vorzeichen.|Precision, Nullable, Default|  
|Zeichenfolge|Enthält Zeichendaten.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|zeit|Enthält eine Uhrzeit.|Precision, Nullable, Default|  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)