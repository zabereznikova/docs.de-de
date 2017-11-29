---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d384986e42ee69a0f425c1590599aa2c82bc856
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Gibt an, dass eine Klasse nur als Basisklasse verwendet werden kann und Sie ein Objekt direkt daraus erstellen können.  
  
## <a name="remarks"></a>Hinweise  
 Der Zweck einer *Basisklasse* (auch bekannt als ein *abstrakte Klasse*) Funktionalität zu definieren, die für alle Klassen, die davon abgeleitet wird. Dies erspart die abgeleiteten Klassen von die gemeinsamen Elemente neu definieren. In einigen Fällen diesen häufig verwendeten Funktionen ist nicht umfassend genug, um ein Objekt nutzbar zu machen, und jede abgeleitete Klasse definiert die fehlende Funktionalität. Sie möchten in einem solchen Fall ist den verwendeten Code zum Erstellen von Objekten nur von den abgeleiteten Klassen. Verwenden Sie `MustInherit` in der Basisklasse, um dies zu erzwingen.  
  
 Eine weitere Verwendungsmöglichkeit von einer `MustInherit` Klasse ist, um eine Variable auf einen Satz von verwandten Klassen zu beschränken. Sie können eine Basisklasse definieren und diese verwandten Klassen ableiten. Die Basisklasse muss keine Funktionen, die den abgeleiteten Klassen gemeinsam bereitstellen, aber als Filter für das Zuweisen von Werten zu Variablen dienen. Wenn der verwendete Code eine Variable als Basisklasse deklariert wird, können mit Visual Basic nur ein Objekt aus einer der abgeleiteten Klassen auf diese Variable zuzuweisen.  
  
 .NET Framework definiert mehrere `MustInherit` Klassen untereinander <xref:System.Array>, <xref:System.Enum>, und <xref:System.ValueType>. <xref:System.ValueType>ist ein Beispiel für eine Basisklasse, die eine Variable einschränkt. Alle Werttypen abgeleitet <xref:System.ValueType>. Wenn Sie eine Variable deklarieren <xref:System.ValueType>, können Sie diese Variable nur Werttypen zuweisen.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `MustInherit` nur in einem `Class` Anweisung.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `MustInherit` zusammen mit `NotInheritable` in der gleichen Deklaration.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die erzwungene Vererbung und erzwungene überschreiben. Die Basisklasse `shape` definiert eine Variable `acrossLine`. Die Klassen `circle` und `square` abgeleitet `shape`. Sie erben die Definition der `acrossLine`, aber sie müssen die Funktion definieren `area` , da die Berechnung für jede Art von Form unterscheidet.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 Sie können deklarieren, `shape1` und `shape2` Typ `shape`. Allerdings kann nicht Erstellung ein Objekts aus `shape` , da sie nicht die Funktionalität der Funktion enthält `area` und RuntimeCompatibility `MustInherit`.  
  
 Da sie als deklariert werden `shape`, die Variablen `shape1` und `shape2` auf Objekte eingeschränkt werden, von den abgeleiteten Klassen `circle` und `square`. Visual Basic erlaubt nicht, ein anderes Objekt um diese Variablen zuzuweisen, was Ihnen ein hohes Maß an Sicherheit gibt.  
  
## <a name="usage"></a>Verwendung  
 Die `MustInherit` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
