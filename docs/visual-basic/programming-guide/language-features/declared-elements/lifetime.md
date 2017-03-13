---
title: "Lifetime in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "static variables, lifetime"
  - "static variables, Visual Basic"
  - "declared elements, lifetime"
  - "Shared variable lifetime"
  - "lifetime, declared elements"
  - "lifetime, Visual Basic"
  - "lifetime"
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Lifetime in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Die *Lebensdauer* eines deklarierten Elements ist der Zeitraum, während dessen das Element verfügbar ist.  Variablen sind die einzigen Elemente, die eine Lebensdauer haben.  Aus diesem Grund behandelt der Compiler Prozedurparameter und Funktionsrückgaben als spezielle Variablenarten.  Die Lebensdauer einer Variablen ist der Zeitraum, während dessen sie einen Wert enthalten kann.  Der Wert kann sich innerhalb der Lebensdauer ändern, aber ein Wert ist immer vorhanden.  
  
## Unterschiedliche Lebensdauer  
 Eine *Membervariable* \(eine auf Modulebene außerhalb der Prozeduren deklarierte Variable\) hat in der Regel die gleiche Lebensdauer wie das Element, in dem sie deklariert ist.  Eine nicht freigegebene Variable, die in einer Klasse oder einer Struktur deklariert ist, besteht als separate Kopie für jede Instanz der Klasse bzw. Struktur, in der sie deklariert ist.  Jede dieser Variablen hat die gleiche Lebensdauer wie ihre Instanz.  Eine `Shared`\-Variable hat jedoch nur eine Lebensdauer, die über die gesamte Zeit reicht, in der die Anwendung ausgeführt wird.  
  
 Eine *lokale Variable* \(eine innerhalb einer Prozedur deklarierte Variable\) besteht nur so lange, wie die Prozedur, in der sie deklariert ist, ausgeführt wird.  Dies gilt auch für die Parameter der Prozedur sowie alle Funktionsrückgaben.  Wenn diese Prozedur jedoch andere Prozeduren aufruft, behalten die lokalen Variablen ihre Werte, solange die aufgerufenen Prozeduren ausgeführt werden.  
  
## Anfang der Lebensdauer  
 Die Lebensdauer einer lokalen Variable beginnt, wenn die Prozedur, in der sie deklariert ist, die Steuerung erhält.  Jede lokale Variable wird mit dem Standardwert für ihren Datentyp initialisiert, sobald die Ausführung der Prozedur beginnt.  Wenn die Prozedur auf eine `Dim`\-Anweisung trifft, die Anfangswerte angibt, setzt sie diese Variablen auf diese Werte, auch wenn der Code bereits andere Werte dafür zugewiesen hat.  
  
 Jeder Member einer Strukturvariablen wird wie eine separate Variable initialisiert.  Auf ähnliche Weise wird jedes Element einer Arrayvariablen einzeln initialisiert.  
  
 Variablen, die in einem Block innerhalb einer Prozedur deklariert sind \(z. B. in einer `For`\-Schleife\), werden beim Eintritt in die Prozedur initialisiert.  Diese Initialisierungen finden unabhängig davon statt, ob der Code den Block jemals ausführt.  
  
## Ende der Lebensdauer  
 Wenn eine Prozedur endet, bleiben die Werte ihrer lokalen Variablen nicht erhalten und [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] fordert ihren Arbeitsspeicher an.  Beim nächsten Aufruf der Prozedur werden alle ihre lokalen Variablen von neuem erstellt und initialisiert.  
  
 Wenn eine Instanz einer Klasse oder Struktur beendet wird, verlieren die nicht freigegebenen Variablen ihren Arbeitsspeicher und ihre Werte.  Jede neue Instanz der Klasse oder Struktur erstellt und initialisiert ihre nicht freigegebenen Variablen erneut.  `Shared`\-Variablen bleiben jedoch erhalten, bis die Anwendung nicht mehr ausgeführt wird.  
  
## Erweiterung der Lebensdauer  
 Wenn Sie eine lokale Variable mit dem `Static`\-Schlüsselwort deklarieren, geht ihre Lebensdauer über die Ausführungsdauer ihrer Prozedur hinaus.  Aus der folgenden Tabelle geht hervor, wie die Prozedurdeklaration die Lebensdauer einer `Static`\-Variablen bestimmt.  
  
|Prozedurspeicherort und \-freigabe|Lebensdauer der statischen Variablen beginnt|Lebensdauer der statischen Variablen endet|  
|----------------------------------------|--------------------------------------------------|------------------------------------------------|  
|In einem Modul \(standardmäßig freigegeben\)|Beim ersten Aufruf der Prozedur|Wenn die Ausführung der Anwendung beendet wird|  
|In einer Klasse, `Shared` \(Prozedur ist kein Instanzmember\)|Wenn die Prozedur zum ersten Mal entweder an einer bestimmten Instanz oder am Klassen\- oder Strukturnamen selbst aufgerufen wird|Wenn die Ausführung der Anwendung beendet wird|  
|In einer Instanz einer Klasse, nicht `Shared` \(Prozedur ist ein Instanzmember\)|Wenn die Prozedur zum ersten Mal an der spezifischen Instanz aufgerufen wird|Bei der Freigabe der Instanz für die Garbage Collection \(GC\)|  
  
## Statische Variablen mit demselben Namen  
 Statische Variablen mit demselben Namen können in mehreren Prozeduren deklariert werden.  In einem solchen Fall gilt jede dieser Variablen für den [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler als separates Element.  Die Initialisierung einer dieser Variablen wirkt sich nicht auf die Werte der anderen aus.  Dasselbe gilt, wenn Sie eine Prozedur mit einer Reihe von Überladungen definieren und in jeder Überladung eine statische Variable mit demselben Namen deklarieren.  
  
## Enthaltende Elemente für statische Variablen  
 Es ist möglich, eine statische lokale Variable in einer Klasse, d. h. innerhalb einer Prozedur in dieser Klasse, zu deklarieren.  Sie können eine statische lokale Variable jedoch nicht in einer Struktur deklarieren, sei es als Strukturmember oder als lokale Variable einer Prozedur innerhalb dieser Struktur.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispiel wird eine Variable mit dem [Static](../../../../visual-basic/language-reference/modifiers/static.md)\-Schlüsselwort deklariert.  \(Sie benötigen das `Dim`\-Schlüsselwort nicht, wenn in der [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) ein Modifizierer wie `Static` verwendet wird.\)  
  
### Code  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### Kommentare  
 Im vorhergehenden Beispiel existiert die Variable `applesSold` weiter, nachdem die `runningTotal`\-Prozedur zum aufrufenden Code zurückgekehrt ist.  Beim nächsten Aufruf von `runningTotal` bleibt der zuvor berechnete Wert von `applesSold` bestehen.  
  
 Wäre `applesSold` ohne `Static` deklariert worden, würden die gesammelten Werte nicht für Aufrufe von `runningTotal` erhalten bleiben.  Beim nächsten Aufruf von `runningTotal` wäre `applesSold` neu erstellt und mit 0 initialisiert worden. Darüber hinaus hätte `runningTotal` einfach denselben Wert zurückgegeben, mit dem die Funktion aufgerufen wurde.  
  
### Kompilieren des Codes  
 Der Wert einer statischen lokalen Variablen kann bei ihrer Deklaration initialisiert werden.  Wenn Sie ein Array als `Static` deklarieren, können sein Rang \(die Anzahl der Dimensionen\), die Länge jeder Dimension und die Werte der einzelnen Elemente initialisiert werden.  
  
### Sicherheit  
 Im vorhergehenden Beispiel können Sie dieselbe Lebensdauer erzeugen, indem Sie `applesSold` auf Modulebene deklarieren.  Wenn Sie den Gültigkeitsbereich der Variablen auf diese Weise ändern würden, hätte die Prozedur keinen exklusiven Zugriff mehr auf sie.  Da in diesem Fall andere Prozeduren auf `applesSold` zugreifen und deren Wert ändern könnten, wäre die laufende Summe eventuell nicht zuverlässig, und die Codeverwaltung würde u. U. schwieriger.  
  
## Siehe auch  
 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)