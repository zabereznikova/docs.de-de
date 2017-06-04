---
title: "Entity Data Model | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Entity Data Model
Das Entity Data Model \(EDM\) ist eine Reihe von Konzepten, die die Datenstruktur unabhängig von der gespeicherten Form beschreiben.  Das EDM ist aus dem 1976 von Peter Chen beschriebenen Entitätsbeziehungsmodell ausgeliehen, baut aber auch auf dem Entitätsbeziehungsmodell auf und erweitert seine herkömmliche Verwendung.  
  
 Das EDM löst die Herausforderungen, die sich aus dem Speichern von Daten in vielen Formen ergeben.  Denken Sie z. B. an ein Unternehmen, das Daten in relationalen Datenbanken, Textdateien, XML\-Dateien, Arbeitsblättern und Berichten speichert.  Dies stellt bedeutende Herausforderungen an Datenmodellierung, Anwendungsentwurf und Datenzugriff dar.  Beim Entwerfen einer datenorientierten Anwendung besteht die Herausforderung darin, effizienten und verwaltbaren Code zu schreiben, ohne auf effizienten Datenzugriff, Speicherung und Skalierbarkeit zu verzichten.  Wenn Daten eine relationale Struktur haben, sind Datenzugriff, Speicherung und Skalierbarkeit sehr effizient, allerdings wird das Schreiben von effizientem und verwaltbarem Code schwieriger.  Wenn Daten über eine Objektstruktur verfügen, kehren sich Vor\- und Nachteile um: Das Schreiben von effizientem und verwaltbarem Code erfolgt zu Lasten von effizientem Datenzugriff, Speicherung und Skalierbarkeit.  Selbst wenn die richtige Balance zwischen diesen Kompromissen gefunden wird, entstehen neue Herausforderungen, wenn Daten zwischen Formen verschoben werden.  Das Entity Data Model löst diese Herausforderungen, indem die Datenstruktur in Bezug auf Entitäten und Beziehungen beschrieben wird, die unabhängig von einem Speicherschema sind.  Dadurch wird die gespeicherte Datenform unabhängig von Anwendungsentwurf und Entwicklung.  Und da Entitäten und Beziehungen die Datenstruktur beschreiben, wie sie in einer Anwendung \(nicht der gespeicherten Form\) verwendet wird, können sie mit der Anwendung weiterentwickelt werden.  
  
 Ein `conceptual model` ist eine bestimmte Darstellung der Datenstruktur als Entitäten und Beziehungen und wird im Allgemeinen in einer domänenspezifischen Sprache \(DSL\) definiert, die die Konzepte des EDM implementiert.  [Konzeptionelle Schemadefinitionssprache \(CSDL\)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) ist ein Beispiel einer solchen domänenspezifischen Sprache.  In einem konzeptionellen Modell beschriebene Entitäten und Beziehungen können als Abstraktionen von Objekten und Zuordnungen in einer Anwendung betrachtet werden.  Dadurch können sich Entwickler ohne Beachtung des Speicherschemas auf das konzeptionelle Modell konzentrieren und Code mit dem Schwerpunkt auf Effizienz und Verwaltbarkeit schreiben.  In der Zwischenzeit können sich Speicherschema\-Designer auf die Effizienz von Datenzugriff, Speicherung und Skalierbarkeit konzentrieren.  
  
## In diesem Abschnitt  
 In den Themen dieses Abschnitts werden die Konzepte des Entity Data Model erläutert.  Jede DSL, die das EDM implementiert, sollte die hier beschriebenen Konzepte enthalten.  Beachten Sie, dass das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) konzeptionelle Modelle mithilfe von CSDL definiert.  Weitere Informationen finden Sie unter [CSDL\-Spezifikation](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).  
  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [Zuordnungsende](../../../../docs/framework/data/adonet/association-end.md)  
  
 [Multiplizität des Zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md)  
  
 [Zuordnungssatzende](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [Zuordnungstyp](../../../../docs/framework/data/adonet/association-type.md)  
  
 [Komplexer Typ](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [Facet](../../../../docs/framework/data/adonet/facet.md)  
  
 [Fremdschlüsseleigenschaft](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [Im Modell deklarierte Funktion](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [Modelldefinierte Funktion](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [Navigationseigenschaft](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [property](../../../../docs/framework/data/adonet/property.md)  
  
 [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## Siehe auch  
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)   
 [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [CSDL\-Spezifikation](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)