---
title: "class (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "class_CSharpKeyword"
  - "class"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "class-Schlüsselwort [C#]"
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# class (C#-Referenz)
Klassen werden wie im folgenden Beispiel mit dem `class`\-Schlüsselwort deklariert:  
  
```  
  
      class TestClass  
{  
    // Methods, properties, fields, events, delegates   
    // and nested classes go here.  
}  
```  
  
## Hinweise  
 Nur einzelne Vererbung wird in C\# zulässig.  Dies bedeutet, dass eine Implementierung nur von einer Basisklasse an eine Klasse vererbt werden kann.  Eine Klasse kann jedoch mehr als eine Schnittstelle implementieren.  In der folgenden Tabelle sind Beispiele für Klassenvererbung und Schnittstellenimplementierung aufgeführt:  
  
|Vererbung|Beispiel|  
|---------------|--------------|  
|Keine|`class ClassA { }`|  
|Single|`class DerivedClass: BaseClass { }`|  
|Keine, Implementierung von zwei Schnittstellen|`class ImplClass: IFace1, IFace2 { }`|  
|Einfache, Implementierung einer Schnittstelle|`class ImplDerivedClass: BaseClass, IFace1 { }`|  
  
 Die Klassen, die Sie direkt innerhalb eines Namespace deklarieren, geschachtelt nicht innerhalb anderer Klassen, können entweder [Öffentlich](../../../csharp/language-reference/keywords/public.md) oder [intern](../../../csharp/language-reference/keywords/internal.md) sein.  Klassen sind `internal` standardmäßig.  
  
 Klassenmember, einschließlich geschachtelte Klassen, können [Öffentlich](../../../csharp/language-reference/keywords/public.md), `protected internal`, [geschützt](../../../csharp/language-reference/keywords/protected.md), [intern](../../../csharp/language-reference/keywords/internal.md) oder [privat](../../../csharp/language-reference/keywords/private.md) sein.  Member sind [privat](../../../csharp/language-reference/keywords/private.md) standardmäßig.  
  
 Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Sie können generische Klassen deklarieren, die Typparameter verfügen.  Weitere Informationen finden Sie unter [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md).  
  
 Eine Klasse kann Deklarationen der folgenden Member umfassen:  
  
-   [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [Indexer](../../../csharp/programming-guide/indexers/index.md)  
  
-   [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [Ereignisse](../../../csharp/programming-guide/events/index.md)  
  
-   [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
  
-   [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
## Beispiel  
 Im folgenden Beispiel wird erläutert, wie Klassenfelder, Konstruktoren und Methoden deklariert werden.  Zusätzlich wird die Objektinstanziierung sowie die Ausgabe von Instanzdaten veranschaulicht.  In diesem Beispiel werden zwei Klassen deklariert: die Klasse `Child`, die zwei private Felder \(`name` und `age`\) sowie zwei öffentliche Methoden enthält,  Die zweite Klasse, `StringTest`, wird verwendet, da sie `Main` enthält.  
  
 [!code-cs[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]  
  
## Kommentare  
 Beachten Sie, dass auf die privaten Felder \(`name` und `age`\) im vorherigen Beispiel nur über die öffentlichen Methoden der `Child`\-Klasse zugegriffen werden kann.  Mit der folgenden Anweisung ist es z. B. nicht möglich, den Namen des Kindes über die `Main`\-Methode auszugeben:  
  
```  
Console.Write(child1.name);   // Error  
```  
  
 `Main` könnte nur dann auf private Member von `Child` zugreifen, wenn `Main` ein Member der Klasse wäre.  
  
 Die Typen, die in einer Klasse ohne einen Zugriffsmodifizierer deklariert werden, führen zu `private`, daher werden die Datenmember in diesem Beispiel noch `private` sein, wenn das \- Schlüsselwort entfernt wurden.  
  
 Beachten Sie schließlich, dass das Altersfeld für das mit dem Standardkonstruktor \(`child3`\) erstellte Objekt mit dem Wert 0 \(null\) initialisiert wurde.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)