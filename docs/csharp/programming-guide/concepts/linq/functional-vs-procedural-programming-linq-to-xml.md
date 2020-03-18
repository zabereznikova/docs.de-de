---
title: Vergleich von funktionaler und Prozedurale Programmierung (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e87114d2edcda4b2df14eb2d84f62ebe9638b5eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69594251"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a>Vergleich von funktionaler und Prozedurale Programmierung (LINQ to XML) (C#)
Es gibt viele verschiedene Arten von XML-Anwendungen:  
  
- Einige Anwendungen produzieren auf der Basis von XML-Quelldokumenten neue XML-Dokumente, die eine andere Form als die Quelldokumente besitzen.  
  
- Andere Anwendungen produzieren auf der Basis von XML-Quelldokumenten Ergebnisdokumente mit einem völlig anderen Format, z. B. HTML- oder CSV-Textdateien.  
  
- Wieder andere Anwendungen nehmen XML-Quelldokumente und fügen Datensätze in eine Datenbank ein.  
  
- Es gibt aber auch Anwendungen, die Daten aus einer anderen Quelle, z. B. einer Datenbank, verwenden und aus ihnen XML-Dokumente erstellen.  
  
 Dies sind immer noch nicht alle Arten von XML-Anwendungen, die es gibt, sie stehen aber stellvertretend für die verschiedenartige Funktionalität, die XML-Programmierer implementieren müssen.  
  
 Bei allen diesen Arten von Anwendungen kann ein Entwickler sich grundsätzlich zwischen den folgenden beiden gegensätzlichen Ansätzen entscheiden:  
  
- funktionale Konstruktion unter Verwendung eines deklarativen Ansatzes  
  
- XML-Strukturänderung im Arbeitsspeicher unter Verwendung prozeduralen Codes  
  
 LINQ to XML unterstützt beide Ansätze.  
  
 Beim funktionalen Ansatz schreiben Sie Transformationen, die aus Quelldokumenten vollständig neue Ergebnisdokumente in der gewünschten Form generieren.  
  
 Beim Ändern einer XML-Struktur an Ort und Stelle schreiben Sie Code, der die Knoten in einer XML-Struktur im Arbeitsspeicher durchläuft und durch sie navigiert und dabei Knoten nach Bedarf einfügt, löscht und bearbeitet.  
  
 Sie können LINQ to XML für beide Ansätze verwenden. Bei beiden Ansätzen werden die gleichen Klassen und mitunter auch die gleichen Methoden verwendet. Der Aufbau und die Ziele der beiden Ansätze unterscheiden sich jedoch deutlich. Welcher Ansatz im konkreten Fall leistungsfähiger und weniger speicherintensiv ist, hängt von der jeweiligen Situation ab. Außerdem ist es auch von Fall zu Fall unterschiedlich, ob der Code gerade einfacher zu schreiben und besser zu unterhalten ist.  
  
 Eine Gegenüberstellung der beiden Ansätze finden Sie unter [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#) (Änderung der XML-Struktur im Arbeitsspeicher und funktionale Konstruktion im Vergleich (LINQ to XML) (C#))](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
 Ein Tutorial zum Schreiben funktionaler Transformationen finden Sie unter [Pure Functional Transformations of XML (C#) (Reine funktionale XML-Transformationen (C#))](./introduction-to-pure-functional-transformations.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))](./linq-to-xml-overview.md)
