---
title: "MustInherit (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "MustInherit"
  - "vb.MustInherit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "classes [Visual Basic], abstract"
  - "MustInherit classes, MustInherit keyword"
  - "abstract classes, MustInherit class"
  - "MustInherit keyword"
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# MustInherit (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Legt fest, dass eine Klasse lediglich als Basisklasse verwendet werden kann und Objekte dieser Klasse nicht direkt erstellt werden können.  
  
## Hinweise  
 Eine *Basisklasse* \(auch *abstrakte Klasse* genannt\) dient dem Zweck, eine Funktionalität zu definieren, die allen Klassen gemeinsam ist, die von dieser Klasse abgeleitet werden.  In den abgeleiteten Klassen müssen dadurch die gemeinsamen Elemente nicht neu definiert werden.  Manchmal ist diese gemeinsame Funktionalität nicht umfassend genug, um ein brauchbares Objekt zu bilden. Jede abgeleitete Klasse definiert dann die fehlende Funktionalität.  In einem solchen Fall soll der verwendete Code Objekte nur aus den abgeleiteten Klassen erstellen.  Wenden Sie `MustInherit` auf die Basisklasse an, um dies zu durchzusetzen.  
  
 Eine andere Verwendungsmöglichkeit für eine `MustInherit`\-Klasse besteht darin, eine Variable auf einen Satz verwandter Klassen zu beschränken.  Sie können eine Basisklasse definieren und diese verwandten Klassen davon ableiten.  Die Basisklasse muss keine Funktionalität bereitstellen, die allen abgeleiteten Klassen gemeinsam ist, aber sie kann als Filter für die Zuweisung von Werten zu Variablen dienen.  Wenn im verwendeten Code eine Variable vom Typ der Basisklasse deklariert wird, lässt Visual Basic nur zu, dass dieser Variablen ein Objekt vom Typ einer der abgeleiteten Klassen zugewiesen wird.  
  
 .NET Framework definiert eine Reihe von `MustInherit`\-Klassen, u. a. <xref:System.Array>, <xref:System.Enum> und <xref:System.ValueType>.  <xref:System.ValueType> ist ein Beispiel für eine Basisklasse, die eine Variable einschränkt.  Alle Werttypen sind von <xref:System.ValueType> abgeleitet.  Wenn Sie eine Variable als <xref:System.ValueType> deklarieren, können Sie dieser Variablen nur Werttypen zuweisen.  
  
## Regeln  
  
-   **Deklarationskontext.** `MustInherit` kann nur in einer `Class`\-Anweisung verwendet werden.  
  
-   **Kombinierte Modifizierer.** Sie können `MustInherit` nicht zusammen mit `NotInheritable` in derselben Deklaration angeben.  
  
## Beispiel  
 Im folgenden Beispiel werden sowohl die erzwungene Vererbung als auch das erzwungene Überschreiben veranschaulicht.  In der `shape`\-Basisklasse ist die `acrossLine`\-Variable definiert.  Die `circle`\-Klasse und die `square`\-Klasse sind von `shape` abgeleitet.  Sie erben die Definition von `acrossLine`, müssen jedoch die Funktion `area` definieren, weil diese Berechnung von der Art der Form abhängig ist.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/visualbasic/mustinherit_1.vb)]  
  
 Sie können `shape1` und `shape2` als Klassen vom Typ `shape` deklarieren.  Allerdings können Sie kein Objekt vom Typ `shape` erstellen, weil diese Klasse nicht über die Funktionalität der `area`\-Funktion verfügt und als `MustInherit` deklariert ist.  
  
 Weil die `shape1`\-Variable und die `shape2`\-Variable als `shape` deklariert sind, sind sie auf Objekte der abgeleiteten `circle`\-Klasse und `square`\-Klasse beschränkt.  Visual Basic lässt nicht zu, dass diesen Variablen andere Objekte zugewiesen werden, wodurch ein hohes Maß an Typsicherheit geboten wird.  
  
## Verwendung  
 Der `MustInherit`\-Modifizierer kann im folgenden Kontext verwendet werden:  
  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## Siehe auch  
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)