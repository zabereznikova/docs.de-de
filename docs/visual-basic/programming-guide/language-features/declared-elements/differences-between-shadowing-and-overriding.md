---
title: "Differences Between Shadowing and Overriding (Visual Basic) | Microsoft Docs"
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
  - "shadowing, vs. overriding"
  - "overriding, vs. shadowing"
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Differences Between Shadowing and Overriding (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine Klasse definieren, die von einer Basisklasse erbt, möchten Sie u. U. eines oder mehrere der Basisklassenelemente in der abgeleiteten Klasse neu definieren.  Zu diesem Zweck sind die Techniken Shadowing und Überschreiben verfügbar.  
  
## Vergleich  
 Shadowing und Überschreiben werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt und beide ein deklariertes Element durch ein anderes neu definieren.  Es gibt jedoch klare Unterschiede zwischen den beiden Verfahren.  
  
 In der folgenden Tabelle werden das Shadowing und das Überschreiben miteinander verglichen.  
  
||||  
|-|-|-|  
|Vergleichsaspekte|Shadowing|Überschreiben|  
|Zweck|Schützt vor späteren Änderungen der Basisklasse, durch die ein Member eingeführt wird, der bereits in der abgeleiteten Klasse definiert wurde|Gewährleistet Polymorphismus durch die Definition einer anderen Implementierung einer Prozedur oder Eigenschaft mit derselben Aufrufabfolge<sup>1</sup>|  
|Neu definiertes Element|Jeder deklarierte Elementtyp|Nur Prozeduren \(`Function`, `Sub` oder `Operator`\) oder Eigenschaften|  
|Neu definierendes Element|Jeder deklarierte Elementtyp|Nur Prozeduren oder Eigenschaften mit einer identischen Aufrufabfolge<sup>1</sup>|  
|Zugriffsebene für die Neudefinition von Elementen|Beliebige Zugriffsebene|Kann die Zugriffsebene von überschriebenen Elementen nicht ändern|  
|Lese\- und Schreibzugriff des neu definierenden Elements|Beliebige Kombination|Kann die Lesbarkeit oder Schreibbarkeit der überschriebenen Eigenschaft nicht ändern|  
|Kontrolle über die Neudefinition|Basisklassenelement kann das Shadowing nicht durchsetzen oder verbieten|Basisklassenelement kann `MustOverride`, `NotOverridable` oder `Overridable` angeben|  
|Verwendung von Schlüsselwörtern|Die Verwendung von `Shadows` wird in der abgeleiteten Klasse empfohlen. Wenn weder `Shadows` noch `Overrides` angegeben wurde, wird `Shadows` angenommen<sup>2</sup>.|`Overridable` oder `MustOverride` ist in der Basisklasse erforderlich; `Overrides` ist in der abgeleiteten Klasse erforderlich.|  
|Vererbung des neu definierenden Elements durch Klassen, die von der abgeleiteten Klasse abgeleitet werden|Das Element, welches das Shadowing durchführt, wird von nachfolgenden abgeleiteten Klassen geerbt; das Element, für welches das Shadowing durchgeführt wurde, bleibt verdeckt<sup>3</sup>.|Das überschreibende Element wird von weiter abgeleiteten Klassen geerbt; das überschriebene Element bleibt überschrieben|  
  
 <sup>1</sup> Die *Aufrufabfolge* besteht aus dem Elementtyp \(`Function`, `Sub`, `Operator` oder `Property`\), dem Namen, der Argumentliste und dem Rückgabetyp.  Es ist nicht möglich, eine Prozedur mit einer Eigenschaft zu überschreiben oder umgekehrt.  Sie können keinerlei Prozedur \(`Function`, `Sub` oder `Operator`\) mit einer anderen Art von Prozedur überschreiben.  
  
 <sup>2</sup> Wenn Sie weder `Shadows` noch `Overrides` angeben, gibt der Compiler eine Warnung aus, damit Sie nochmals überprüfen und bestätigen können, welche Art von Neudefinition verwendet werden soll.  Wenn Sie die Warnung ignorieren, wird der Shadowing\-Mechanismus verwendet.  
  
 <sup>3</sup> Wenn in einer nachfolgend abgeleiteten Klasse nicht auf das Element, welches das Shadowing durchführt, zugegriffen werden kann, wird der Shadowing\-Effekt nicht vererbt.  Wenn Sie beispielsweise das Element, welches das Shadowing durchführt, als `Private` deklarieren, erbt eine von der abgeleiteten Klasse abgeleitete Klasse das Originalelement anstelle des Elements, welches das Shadowing durchführt.  
  
## Richtlinien  
 Das Überschreiben wird normalerweise in den folgenden Fällen angewendet:  
  
-   Sie definieren polymorphe abgeleitete Klassen.  
  
-   Sie möchten sicherstellen, dass der Compiler den gleichen Elementtyp und die gleiche Aufrufabfolge erzwingt.  
  
 Sie führen ein Shadowing normalerweise in den folgenden Fällen durch:  
  
-   Sie erwarten, dass Ihre Basisklasse modifiziert wird, und definieren ein Element mit dem Namen eines Basisklassenelements.  
  
-   Sie möchten in der Lage sein, den Elementtyp oder die Aufruffolge zu ändern.  
  
## Siehe auch  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)