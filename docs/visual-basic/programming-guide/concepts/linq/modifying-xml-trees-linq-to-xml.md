---
title: Ändern von XML-Bäumen (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
ms.openlocfilehash: 3402188c4e34ef81bad41ed49f9236b4fb7c47ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406884"
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist ein Speicher im Arbeitsspeicher, der XML-Strukturen speichert. Nachdem Sie eine XML-Struktur aus einer Quelle geladen oder analysiert haben, können Sie diese Struktur in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ändern, sie anschließend serialisieren und möglicherweise in einer Datei speichern oder an einen Remoteserver senden.  
  
 Für das Ändern einer vorhandenen Struktur verwenden Sie bestimmte Methoden, wie <xref:System.Xml.Linq.XContainer.Add%2A>.  
  
 Es gibt aber auch einen anderen Ansatz, nämlich die Verwendung der funktionalen Konstruktion, um eine neue Struktur mit einer anderen Form zu erzeugen. Je nach Art der Änderungen, die Sie an Ihrer XML-Struktur vornehmen müssen, und je nach Größe der Struktur kann sich dieser Ansatz als robuster und einfacher in der Handhabung erweisen. Das erste Thema in diesem Abschnitt enthält eine Gegenüberstellung dieser beiden Ansätze.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|BESCHREIBUNG|  
|-----------|-----------------|  
|[XML-Strukturänderung im Arbeitsspeicher im Vergleich zur funktionalen Konstruktion (LINQ to XML) (Visual Basic)](in-memory-xml-tree-modification-vs-functional-construction.md)|Stellt das Ändern einer XML-Struktur im Arbeitsspeicher dem Ändern durch funktionale Konstruktion gegenüber.|  
|[Hinzufügen von Elementen, Attributen und Knoten zu einer XML-Struktur (Visual Basic)](adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Enthält Informationen zum Hinzufügen von Elementen, Attributen oder Knoten zu einer XML-Struktur.|  
|[Ändern von Elementen, Attributen und Knoten in einer XML-Struktur](modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Enthält Informationen zum Ändern vorhandener Elemente, Attribute oder Knoten.|  
|[Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (Visual Basic)](removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Enthält Informationen zum Entfernen von Elementen, Attributen oder Knoten aus einer XML-Struktur.|  
|[Warten von Name-Wert-Paaren (Visual Basic)](maintaining-name-value-pairs.md)|Beschreibt das Verwalten von Anwendungsinformationen, die am besten als Name/Wert-Paare aufbewahrt werden, wie Konfigurationsinformationen oder globale Einstellungen.|  
|[Vorgehensweise: Ändern des Namespaces für eine gesamte XML-Struktur (Visual Basic)](how-to-change-the-namespace-for-an-entire-xml-tree.md)|Zeigt, wie eine XML-Struktur aus einem Namespace in einen anderen Namespace verschoben werden kann.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Programmier Handbuch (LINQ to XML) (Visual Basic)](programming-guide-linq-to-xml.md)
