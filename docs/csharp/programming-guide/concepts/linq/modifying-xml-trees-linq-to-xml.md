---
title: "Ändern von XML-Strukturen (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 8ec47e6d-2363-4694-be46-8d5ca4d15fc9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8cf3ffabeb7c3caa5f0e3e38fb6f69551ce791b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-xml-trees-linq-to-xml-c"></a>Ändern von XML-Strukturen (LINQ to XML) (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist ein Speicher im Arbeitsspeicher, der XML-Strukturen speichert. Nachdem Sie eine XML-Struktur aus einer Quelle geladen oder analysiert haben, können Sie diese Struktur in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ändern, sie anschließend serialisieren und möglicherweise in einer Datei speichern oder an einen Remoteserver senden.  
  
 Für das Ändern einer vorhandenen Struktur verwenden Sie bestimmte Methoden, wie <xref:System.Xml.Linq.XContainer.Add%2A>.  
  
 Es gibt aber auch einen anderen Ansatz, nämlich die Verwendung der funktionalen Konstruktion, um eine neue Struktur mit einer anderen Form zu erzeugen. Je nach Art der Änderungen, die Sie an Ihrer XML-Struktur vornehmen müssen, und je nach Größe der Struktur kann sich dieser Ansatz als robuster und einfacher in der Handhabung erweisen. Das erste Thema in diesem Abschnitt enthält eine Gegenüberstellung dieser beiden Ansätze.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Änderung des XML-Baums im Arbeitsspeicher und Funktionale Konstruktion (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)|Stellt das Ändern einer XML-Struktur im Arbeitsspeicher dem Ändern durch funktionale Konstruktion gegenüber.|  
|[Hinzufügen von Elementen, Attributen und Knoten zu einer XML-Struktur (C#)](../../../../csharp/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Enthält Informationen zum Hinzufügen von Elementen, Attributen oder Knoten zu einer XML-Struktur.|  
|[Ändern von Elementen, Attributen und Knoten in einem XML-Baum](../../../../csharp/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Enthält Informationen zum Ändern vorhandener Elemente, Attribute oder Knoten.|  
|[Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (C#)](../../../../csharp/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Enthält Informationen zum Entfernen von Elementen, Attributen oder Knoten aus einer XML-Struktur.|  
|[Warten von Name-Wert-Paaren (C#)](../../../../csharp/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|Beschreibt das Verwalten von Anwendungsinformationen, die am besten als Name/Wert-Paare aufbewahrt werden, wie Konfigurationsinformationen oder globale Einstellungen.|  
|[Vorgehensweise: Ändern des Namespace für eine gesamte XML-Struktur (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|Zeigt, wie eine XML-Struktur aus einem Namespace in einen anderen Namespace verschoben werden kann.|  
  
## <a name="see-also"></a>Siehe auch  
 [Programming Guide (LINQ to XML) (C#) (Programmierhandbuch (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
