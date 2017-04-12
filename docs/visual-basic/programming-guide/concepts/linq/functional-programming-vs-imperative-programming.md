---
title: Funktionale Programmierung und Imperative Programmierung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6a1f3b57-00e6-447d-9906-74c7c4d5d85c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7fd7a2defabe2d03b658977cc0106e3bbf985202
ms.lasthandoff: 03/13/2017


---
# <a name="functional-programming-vs-imperative-programming-visual-basic"></a>Funktionale Programmierung und Imperative Programmierung (Visual Basic)
In diesem Thema werden die Gemeinsamkeiten und die Unterschiede der funktionalen Programmierung und der herkömmlichen imperativen (prozeduralen) Programmierung erläutert.  
  
## <a name="functional-programming-vs-imperative-programming"></a>Funktionale Programmierung und Imperative Programmierung  
 Die *funktionale Programmierung* Paradigma explizit erstellt wurde, um eine reine funktionale Lösung von Problemen zu unterstützen. Funktionaler Programmierung ist eine Form der *deklarativen Programmierung*. Im Gegensatz dazu die meisten normalen Programmiersprachen, einschließlich der objektorientierten Programmierung (OOP) Sprachen wie c#, Visual Basic, C++ und Java, in erster Linie Unterstützung konzipiert wurden *imperative* (prozedurale) Programmierung.  
  
 Beim imperativen Ansatz schreibt ein Entwickler Code, der detailliert die Schritte beschreibt, die der Computer zur Erfüllung der Aufgabe ausführen muss. Dies wird manchmal als *algorithmische* programmieren. Beim funktionalen Ansatz hingegen wird das Problem als Satz von auszuführenden Funktionen formuliert. Sie definieren sorgfältig, was für jede Funktion eingegeben wird und was die jeweilige Funktion zurückgibt. In der folgenden Tabelle werden einige der allgemeinen Unterschiede zwischen diesen beiden Ansätzen beschrieben:  
  
|Merkmal|Imperativer Ansatz|Funktionaler Ansatz|  
|--------------------|-------------------------|-------------------------|  
|Schwerpunkt bei der Programmierung|Art und Weise der Ausführung von Aufgaben (Algorithmen) und der Überwachung von Statusänderungen|Art der gewünschten Informationen und der erforderlichen Transformationen|  
|Statusänderungen|wichtig|nicht existent|  
|Reihenfolge der Ausführung|wichtig|weniger wichtig|  
|Primäre Datenflusskontrolle|Schleifen, Bedingungen und Funktions- (Methoden-)Aufrufe|Funktionsaufrufe, einschließlich Rekursion|  
|Primäre Manipulationseinheit|Instanzen von Strukturen oder Klassen|Funktionen als erstklassige Objekte und Datensammlungen|  
  
 Die meisten Sprachen unterstützen zwar ein bestimmtes Programmierparadigma, viele allgemeine Sprachen sind aber ausreichend flexibel, um mehrere Paradigmen zu unterstützen. So können z. B. die meisten Sprachen, die Funktionszeiger enthalten, zur glaubwürdigen Unterstützung der funktionalen Programmierung verwendet werden. Darüber hinaus umfasst Visual Basic explizite spracherweiterungen zur Unterstützung der funktionalen Programmierung, einschließlich Lambda-Ausdrücke und typableitung. Eine Form der deklarativen, funktionalen Programmierung ist die LINQ-Technologie.  
  
## <a name="functional-programming-using-xslt"></a>Funktionale Programmierung mit XSLT  
 Viele XSLT-Entwickler sind mit dem reinen funktionalen Ansatz vertraut. Der effektivste Weg bei der Entwicklung eines XSLT-Stylesheets besteht darin, jede Vorlage als isolierte, zusammensetzbare Transformation zu behandeln. Die Reihenfolge der Ausführung ist dabei ohne jede Bedeutung. XSLT lässt keine Nebenwirkungen zu (lediglich die Escapemechanismen für die Ausführung von prozeduralem Code können Nebenwirkungen mit sich bringen, die zu funktionaler Unreinheit führen). XSLT ist zwar ein wirksames Tool, dennoch sind einige seiner Eigenschaften nicht optimal. So führt z. B. das Ausdrücken von Programmierkonstrukten in XML dazu, dass Code relativ weitschweifig und damit schwierig zu unterhalten ist. Auch die schwere Abhängigkeit von der Rekursion zur Flusssteuerung kann dazu führen, dass Code schwer lesbar ist. Weitere Informationen zu XSLT finden Sie unter [XSLT-Transformationen](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03).  
  
 Dennoch hat XSLT bewiesen, dass die Verwendung eines reinen funktionalen Ansatzes bei der Transformierung von XML von einer Form in eine andere sinnvoll ist. Die reine funktionale Programmierung mit LINQ to XML ähnelt in vielerlei Hinsicht XSLT. Allerdings können mit die Programmierkonstrukten von LINQ to XML und Visual Basic Sie reine funktionale Transformationen schreiben, die besser lesbar und unterhaltbar als XSLT sind.  
  
## <a name="advantages-of-pure-functions"></a>Vorteile von reinen Funktionen  
 Der Hauptgrund für die Implementierung von funktionalen Transformationen als reinen Funktionen (Pure-Funktionen) besteht darin, dass reine Funktionen zusammenstellbar sind, d. h., sie sind in sich abgeschlossen und zustandslos. Diese Eigenschaften bieten u. a. die folgenden Vorteile:  
  
-   Bessere Lesbarkeit und Verwaltbarkeit: Jede Funktion ist für die Erledigung einer bestimmten Aufgabe anhand ihrer Argumente vorgesehen, ohne sich dabei auf einen externen Zustand zu verlassen.  
  
-   Einfachere reiterative Entwicklung: Da der Code einfacher umgestaltet werden kann, können Änderungen am Entwurf oft leichter implementiert werden. Nehmen wir z. B. an, Sie schreiben eine komplizierte Transformation und stellen dann fest, dass sich ein Teil des Codes in der Transformation mehrmals wiederholt. Bei der Umgestaltung mit einer reinen Methode können Sie Ihre reine Methode ganz nach Belieben aufrufen, ohne auf irgendwelche Nebenwirkungen Rücksicht nehmen zu müssen.  
  
-   Einfacheres Testen und Debuggen: Da reine Funktionen einfacher in Isolation getestet werden können, können Sie Testcode schreiben, der die reine Funktion mit typischen Werten, gültigen Randfällen und ungültigen Randfällen aufruft.  
  
## <a name="transitioning-for-oop-developers"></a>Was müssen OOP-Entwickler beachten?  
 Bei der traditionellen objektorientierten Programmierung (OOP) verwenden die meisten Entwickler beim Programmieren den imperativen/prozeduralen Stil. Für den Umstieg auf die Entwicklung in einem reinen funktionalen Stil müssen die Entwickler umdenken und ihre Herangehensweise an die Entwicklung ändern.  
  
 Zur Lösung von Problemen entwerfen OOP-Entwickler Klassenhierarchien, konzentrieren sich auf die richtige Kapselung und denken in Klassenvertragskategorien. Im Vordergrund stehen das Verhalten und der Status von Objekttypen, und zu diesem Zweck werden Sprachfunktionen wie Klassen, Schnittstellen, Vererbung und Polymorphie bereitgestellt.  
  
 Dagegen werden die Berechnungsprobleme bei der funktionalen Programmierung als Übung für die Auswertung reiner funktionaler Transformationen von Datensammlungen angesehen. Bei der funktionalen Programmierung werden Zustands- und änderbare Daten vermieden, stattdessen steht die Anwendung von Funktionen im Mittelpunkt.  
  
 Glücklicherweise erfordert Visual Basic den kompletten Umstieg auf die funktionale Programmierung, da er sowohl den imperativen als auch den funktionalen Programmierungsansatz unterstützt. Der Entwickler kann daher selbst entscheiden, welcher Ansatz für ein bestimmtes Szenario am geeignetsten ist. Bei vielen Programme werden beide Ansätze häufig miteinander kombiniert.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in reine funktionale Transformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [XSLT-Transformationen](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03)   
 [Umgestalten in reine Funktionen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
