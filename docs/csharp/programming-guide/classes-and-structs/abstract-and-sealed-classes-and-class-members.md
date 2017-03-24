---
title: "Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Abstrakte Klassen [C#]"
  - "Versiegelte Klassen [C#]"
  - "C#-Sprache, Abstrakte Klasse"
  - "C#-Sprache, versiegelt"
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch)
Das Schlüsselwort [abstract](../../../csharp/language-reference/keywords/abstract.md) ermöglicht die Erstellung von Klassen und [Klassenmembern](../../../csharp/language-reference/keywords/class.md), die unvollständig sind und in einer abgeleiteten Klasse implementiert werden müssen.  
  
 Mit dem Schlüsselwort [sealed](../../../csharp/language-reference/keywords/sealed.md) können Sie die Vererbung von Klassen oder bestimmten Klassenmembern unterbinden, die zuvor als [virtuell](../../../csharp/language-reference/keywords/virtual.md) gekennzeichnet wurden.  
  
## Abstrakte Klassen und Klassenmember  
 Klassen können durch Festlegen des Schlüsselworts `abstract` vor der Klassendefinition als abstrakt deklariert werden.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 Eine abstrakte Klasse darf nicht instanziiert werden.  Der Zweck einer abstrakten Klasse ist die Bereitstellung einer allgemeinen Definition einer Basisklasse, die für mehrere abgeleitete Klassen freigegeben ist.  Eine Klassenbibliothek kann beispielsweise eine abstrakte Klasse definieren, die als Parameter für ihre Funktionen verwendet wird. Programmierer, die diese Bibliothek verwenden, benötigen ihre eigene Implementierung der Klasse, die sie von ihr ableiten können.  
  
 Abstrakte Klassen können auch abstrakte Methoden definieren.  Zu diesem Zweck wird das Schlüsselwort `abstract` vor dem Rückgabetyp der Methode einfügt.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 Abstrakte Methoden verfügen über keine Implementierung, deshalb folgt der Methodendefinition ein Semikolon statt eines normalen Methodenblocks.  Von der abstrakten Klasse abgeleitete Klassen müssen alle abstrakten Methoden implementieren.  Wenn eine abstrakte Klasse eine virtuelle Methode von einer Basisklasse erbt, kann sie die virtuelle Methode mit einer abstrakten Methode überschreiben.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 Wenn eine `virtual`\-Methode als `abstract` deklariert ist, bleibt sie für alle Klassen virtuell, die von der abstrakten Klasse erben.  Eine Klasse, die eine abstrakte Methode erbt, hat keinen Zugriff auf die ursprüngliche Implementierung der Methode: Im obigen Beispiel kann `DoWork` in Klasse F nicht `DoWork` in Klasse D aufrufen.  Auf diese Weise kann eine abstrakte Klasse abgeleitete Klassen zwingen, neue Methoden für virtuelle Methoden zu implementieren.  
  
## Versiegelte Klassen und Klassenmember  
 Klassen können durch Festlegen des Schlüsselworts `sealed` vor der Klassendefinition als [versiegelt](../../../csharp/language-reference/keywords/sealed.md) deklariert werden.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 Eine versiegelte Klasse kann nicht als Basisklasse verwendet werden.  Aus diesem Grund kann sie auch keine abstrakte Klasse sein.  Von versiegelten Klassen kann nicht abgeleitet werden.  Weil sie nicht als Basisklasse verwendet werden können, können Aufrufe an versiegelte Klassenmember durch Laufzeitoptimierungen etwas beschleunigt werden.  
  
 Methoden, Indexer, Eigenschaften oder Ereignisse einer abgeleiteten Klasse, die einen virtuellen Member der Basisklasse überschreiben, können diesen Member als versiegelt deklarieren.  Damit wird der virtuelle Aspekt des Members für jede weitere abgeleitete Klasse aufgehoben.  Dazu wird in die Klassenmemberdeklaration das Schlüsselwort `sealed` vor dem Schlüsselwort [override](../../../csharp/language-reference/keywords/override.md) eingefügt.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [Gewusst wie: Definieren von abstrakten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)