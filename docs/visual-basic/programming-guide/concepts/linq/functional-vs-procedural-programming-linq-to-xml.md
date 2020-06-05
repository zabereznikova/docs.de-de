---
title: Vergleich von funktionaler und prozeduraler Programmierung (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
ms.openlocfilehash: 0b525f13298e7402369b890516434cec47e01542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398434"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a>Funktionale und prozedurale Programmierung (LINQ to XML) (Visual Basic)
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
  
 Weitere Informationen zu den beiden Ansätzen finden Sie unter [in-Memory-XML-Strukturänderung im Vergleich zur funktionalen Konstruktion (LINQ to XML) (Visual Basic)](in-memory-xml-tree-modification-vs-functional-construction.md).  
  
 Ein Tutorial zum Schreiben funktionaler Transformationen finden Sie unter [reine funktionale XML-Transformationen (Visual Basic)](pure-functional-transformations-of-xml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die LINQ to XML Programmierung (Visual Basic)](linq-to-xml-programming-overview.md)
