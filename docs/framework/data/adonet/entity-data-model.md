---
title: Entity Data Model
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: ed834c57104e9f03ac337f6c1d30a0498bd42a06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738411"
---
# <a name="entity-data-model"></a>Entity Data Model
Das Entity Data Model (EDM) ist eine Reihe von Konzepten, die die Datenstruktur unabhängig von der gespeicherten Form beschreiben. Das EDM ist aus dem 1976 von Peter Chen beschriebenen Entitätsbeziehungsmodell ausgeliehen, baut aber auch auf dem Entitätsbeziehungsmodell auf und erweitert seine herkömmliche Verwendung.  
  
 Das EDM löst die Herausforderungen, die sich aus dem Speichern von Daten in vielen Formen ergeben. Denken Sie z. B. an ein Unternehmen, das Daten in relationalen Datenbanken, Textdateien, XML-Dateien, Arbeitsblättern und Berichten speichert. Dies stellt bedeutende Herausforderungen an Datenmodellierung, Anwendungsentwurf und Datenzugriff dar. Beim Entwerfen einer datenorientierten Anwendung besteht die Herausforderung darin, effizienten und verwaltbaren Code zu schreiben, ohne auf effizienten Datenzugriff, Speicherung und Skalierbarkeit zu verzichten. Wenn Daten eine relationale Struktur haben, sind Datenzugriff, Speicherung und Skalierbarkeit sehr effizient, allerdings wird das Schreiben von effizientem und verwaltbarem Code schwieriger. Wenn Daten über eine Objektstruktur verfügen, kehren sich Vor- und Nachteile um: Das Schreiben von effizientem und verwaltbarem Code erfolgt zu Lasten von effizientem Datenzugriff, Speicherung und Skalierbarkeit. Selbst wenn die richtige Balance zwischen diesen Kompromissen gefunden wird, entstehen neue Herausforderungen, wenn Daten zwischen Formen verschoben werden. Das Entity Data Model löst diese Herausforderungen, indem die Datenstruktur in Bezug auf Entitäten und Beziehungen beschrieben wird, die unabhängig von einem Speicherschema sind. Dadurch wird die gespeicherte Datenform unabhängig von Anwendungsentwurf und Entwicklung. Und da Entitäten und Beziehungen die Datenstruktur beschreiben, wie sie in einer Anwendung (nicht der gespeicherten Form) verwendet wird, können sie mit der Anwendung weiterentwickelt werden.  
  
 Ein `conceptual model` ist eine bestimmte Darstellung der Datenstruktur als Entitäten und Beziehungen und wird im Allgemeinen in einer domänenspezifischen Sprache (DSL) definiert, die die Konzepte des EDM implementiert. Die [konzeptionelle Schema Definitions Sprache (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) ist ein Beispiel für eine solche domänenspezifische Sprache. In einem konzeptionellen Modell beschriebene Entitäten und Beziehungen können als Abstraktionen von Objekten und Zuordnungen in einer Anwendung betrachtet werden. Dadurch können sich Entwickler ohne Beachtung des Speicherschemas auf das konzeptionelle Modell konzentrieren und Code mit dem Schwerpunkt auf Effizienz und Verwaltbarkeit schreiben. In der Zwischenzeit können sich Speicherschema-Designer auf die Effizienz von Datenzugriff, Speicherung und Skalierbarkeit konzentrieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 In den Themen dieses Abschnitts werden die Konzepte des Entity Data Model erläutert. Jede DSL, die das EDM implementiert, sollte die hier beschriebenen Konzepte enthalten. Beachten Sie, dass das [ADO.NET-Entity Framework](./ef/index.md) CSDL verwendet, um konzeptionelle Modelle zu definieren. Weitere Informationen finden Sie unter [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).  
  
 [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)  
  
 [Entity Data Model: Namespaces](entity-data-model-namespaces.md)  
  
 [Entity Data Model: Primitive Datentypen](entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: Vererbung](entity-data-model-inheritance.md)  
  
 [Zuordnungsende](association-end.md)  
  
 [Multiplizität des Zuordnungsendes](association-end-multiplicity.md)  
  
 [Zuordnungssatz](association-set.md)  
  
 [Ende des Zuordnungssatzes](association-set-end.md)  
  
 [Zuordnungstyp](association-type.md)  
  
 [Komplexer Typ](complex-type.md)  
  
 [Entitätscontainer](entity-container.md)  
  
 [Entitätsschlüssel](entity-key.md)  
  
 [Entitätenmenge](entity-set.md)  
  
 [Entitätstyp](entity-type.md)  
  
 [facet](facet.md)  
  
 [Fremdschlüsseleigenschaft](foreign-key-property.md)  
  
 [Im Modell deklarierte Funktion](model-declared-function.md)  
  
 [Im Modell definierte Funktion](model-defined-function.md)  
  
 [Navigationseigenschaft](navigation-property.md)  
  
 [Eigenschaft](property.md)  
  
 [Einschränkung der referenziellen Integrität](referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [CSDL-Spezifikation](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
