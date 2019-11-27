---
title: Funktionale Programmierung kontra imperativer Programmierung
ms.date: 07/20/2015
ms.assetid: 6a1f3b57-00e6-447d-9906-74c7c4d5d85c
ms.openlocfilehash: 704beadc29af0de606b8f246360dc6fffca8cfcc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353442"
---
# <a name="functional-programming-vs-imperative-programming-visual-basic"></a>Funktionale Programmierung im Vergleich zu imperativer Programmierung (Visual Basic)
In diesem Thema werden die Gemeinsamkeiten und die Unterschiede der funktionalen Programmierung und der herkömmlichen imperativen (prozeduralen) Programmierung erläutert.  
  
## <a name="functional-programming-vs-imperative-programming"></a>Funktionale Programmierung kontra imperativer Programmierung  
 Explizite Aufgabe der *funktionalen Programmierung* ist die Unterstützung eines reinen funktionalen Ansatzes bei der Problemlösung. Die funktionale Programmierung ist eine Form der *deklarativen Programmierung*. Im Unterschied dazu unterstützen die meisten normalen Programmiersprachen, darunter auch OOP-Sprachen wie C#, Visual Basic, C++ und Java, in erster Linie die *imperative* (prozedurale) Programmierung.  
  
 Beim imperativen Ansatz schreibt ein Entwickler Code, der detailliert die Schritte beschreibt, die der Computer zur Erfüllung der Aufgabe ausführen muss. Diese Form der Programmierung wird mitunter auch als *algorithmische* Programmierung bezeichnet. Beim funktionalen Ansatz hingegen wird das Problem als Satz von auszuführenden Funktionen formuliert. Sie definieren sorgfältig, was für jede Funktion eingegeben wird und was die jeweilige Funktion zurückgibt. In der folgenden Tabelle werden einige der allgemeinen Unterschiede zwischen diesen beiden Ansätzen beschrieben:  
  
|Merkmal|Imperativer Ansatz|Funktionaler Ansatz|  
|--------------------|-------------------------|-------------------------|  
|Schwerpunkt bei der Programmierung|Art und Weise der Ausführung von Aufgaben (Algorithmen) und der Überwachung von Statusänderungen|Art der gewünschten Informationen und der erforderlichen Transformationen|  
|Zustandsänderungen|Wichtig.|nicht existent|  
|Reihenfolge der Ausführung|Wichtig.|weniger wichtig|  
|Primäre Datenflusskontrolle|Schleifen, Bedingungen und Funktions- (Methoden-)Aufrufe|Funktionsaufrufe, einschließlich Rekursion|  
|Primäre Manipulationseinheit|Instanzen von Strukturen oder Klassen|Funktionen als erstklassige Objekte und Datensammlungen|  
  
 Die meisten Sprachen unterstützen zwar ein bestimmtes Programmierparadigma, viele allgemeine Sprachen sind aber ausreichend flexibel, um mehrere Paradigmen zu unterstützen. So können z. B. die meisten Sprachen, die Funktionszeiger enthalten, zur glaubwürdigen Unterstützung der funktionalen Programmierung verwendet werden. Darüber hinaus enthält Visual Basic explizite Spracherweiterungen zur Unterstützung der funktionalen Programmierung, einschließlich Lambda-Ausdrücken und Typrückschluss. Eine Form der deklarativen, funktionalen Programmierung ist die LINQ-Technologie.  
  
## <a name="functional-programming-using-xslt"></a>Funktionale Programmierung mit XSLT  
 Viele XSLT-Entwickler sind mit dem reinen funktionalen Ansatz vertraut. Der effektivste Weg bei der Entwicklung eines XSLT-Stylesheets besteht darin, jede Vorlage als isolierte, zusammensetzbare Transformation zu behandeln. Die Reihenfolge der Ausführung ist dabei ohne jede Bedeutung. XSLT lässt keine Nebenwirkungen zu (lediglich die Escapemechanismen für die Ausführung von prozeduralem Code können Nebenwirkungen mit sich bringen, die zu funktionaler Unreinheit führen). XSLT ist zwar ein wirksames Tool, dennoch sind einige seiner Eigenschaften nicht optimal. So führt z. B. das Ausdrücken von Programmierkonstrukten in XML dazu, dass Code relativ weitschweifig und damit schwierig zu unterhalten ist. Auch die schwere Abhängigkeit von der Rekursion zur Flusssteuerung kann dazu führen, dass Code schwer lesbar ist. Weitere Informationen zu XSLT finden Sie unter [XSLT-Transformationen](../../../../standard/data/xml/xslt-transformations.md).  
  
 Dennoch hat XSLT bewiesen, dass die Verwendung eines reinen funktionalen Ansatzes bei der Transformierung von XML von einer Form in eine andere sinnvoll ist. Die reine funktionale Programmierung mit LINQ to XML ähnelt in vielerlei Hinsicht XSLT. Mit den Programmierkonstrukten, die mit LINQ to XML und Visual Basic eingeführt wurden, können Sie jedoch reine funktionale Transformationen schreiben, die besser lesbar und verwalterbar sind als XSLT.  
  
## <a name="advantages-of-pure-functions"></a>Vorteile von reinen Funktionen  
 Der Hauptgrund für die Implementierung von funktionalen Transformationen als reinen Funktionen (Pure-Funktionen) besteht darin, dass reine Funktionen zusammenstellbar sind, d. h., sie sind in sich abgeschlossen und zustandslos. Diese Eigenschaften bieten u. a. die folgenden Vorteile:  
  
- Bessere Lesbarkeit und Verwaltbarkeit: Jede Funktion ist für die Erledigung einer bestimmten Aufgabe anhand ihrer Argumente vorgesehen, ohne sich dabei auf einen externen Zustand zu verlassen.  
  
- Einfachere reiterative Entwicklung: Da der Code einfacher umgestaltet werden kann, können Änderungen am Entwurf oft leichter implementiert werden. Nehmen wir z. B. an, Sie schreiben eine komplizierte Transformation und stellen dann fest, dass sich ein Teil des Codes in der Transformation mehrmals wiederholt. Bei der Umgestaltung mit einer reinen Methode können Sie Ihre reine Methode ganz nach Belieben aufrufen, ohne auf irgendwelche Nebenwirkungen Rücksicht nehmen zu müssen.  
  
- Einfacheres Testen und Debuggen: Da reine Funktionen einfacher in Isolation getestet werden können, können Sie Testcode schreiben, der die reine Funktion mit typischen Werten, gültigen Randfällen und ungültigen Randfällen aufruft.  
  
## <a name="transitioning-for-oop-developers"></a>Was müssen OOP-Entwickler beachten?  
 Bei der traditionellen objektorientierten Programmierung (OOP) verwenden die meisten Entwickler beim Programmieren den imperativen/prozeduralen Stil. Für den Umstieg auf die Entwicklung in einem reinen funktionalen Stil müssen die Entwickler umdenken und ihre Herangehensweise an die Entwicklung ändern.  
  
 Zur Lösung von Problemen entwerfen OOP-Entwickler Klassenhierarchien, konzentrieren sich auf die richtige Kapselung und denken in Klassenvertragskategorien. Im Vordergrund stehen das Verhalten und der Status von Objekttypen, und zu diesem Zweck werden Sprachfunktionen wie Klassen, Schnittstellen, Vererbung und Polymorphie bereitgestellt.  
  
 Dagegen werden die Berechnungsprobleme bei der funktionalen Programmierung als Übung für die Auswertung reiner funktionaler Transformationen von Datensammlungen angesehen. Bei der funktionalen Programmierung werden Zustands- und änderbare Daten vermieden, stattdessen steht die Anwendung von Funktionen im Mittelpunkt.  
  
 Glücklicherweise erfordert Visual Basic nicht den vollständigen Sprung zur funktionalen Programmierung, da Sie sowohl imperative als auch funktionale Programmier Ansätze unterstützt. Der Entwickler kann daher selbst entscheiden, welcher Ansatz für ein bestimmtes Szenario am geeignetsten ist. Bei vielen Programme werden beide Ansätze häufig miteinander kombiniert.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in reine funktionale Transformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [XSLT Transformations (XSLT-Transformationen)](../../../../standard/data/xml/xslt-transformations.md)
- [Refactoring in reine Funktionen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
