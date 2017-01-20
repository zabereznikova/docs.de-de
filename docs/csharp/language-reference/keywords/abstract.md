---
title: "abstract (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "abstract"
  - "abstract_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "abstract-Schlüsselwort [C#]"
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# abstract (C#-Referenz)
Der `abstract`\-Modifizierer gibt an, dass die Implementierung des Elements, das geändert wird, fehlt oder unvollständig ist.  Der abstract\-Modifizierer kann für Klassen, Methoden, Eigenschaften, Indexer und Ereignisse verwendet werden.  In einer Klassendeklaration kann mit dem `abstract`\-Modifizierer angegeben werden, dass die Klasse nur als Basisklasse anderer Klassen verwendet werden soll.  Member, die als abstrakt gekennzeichnet oder in einer abstrakten Klasse enthalten sind, müssen von Klassen implementiert werden, die von der abstrakten Klasse abgeleitet sind.  
  
## Beispiel  
 In diesem Beispiel muss die Klasse `Square` eine Implementierung von `Area` bereitstellen, weil sie von `ShapesClass` abgeleitet ist:  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#1)]  
  
 Abstrakte Klassen weisen die nachstehenden Funktionen auf:  
  
-   Eine abstrakte Klasse darf nicht instanziiert werden.  
  
-   Eine abstrakte Klasse darf abstrakte Methoden und Accessoren enthalten.  
  
-   Es ist nicht möglich, eine abstrakte Klasse unter Verwendung des [sealed](../../../csharp/language-reference/keywords/sealed.md)\-Modifizierers zu ändern, da die beiden Modifizierer entgegengesetzte Bedeutungen haben.  Der `sealed`\-Modifizierer verhindert, dass eine Klasse geerbt wird, und der `abstract`\-Modifizierer erfordert, dass eine Klasse geerbt wird.  
  
-   Eine nicht abstrakte Klasse, die von einer abstrakten Klasse abgeleitet wurde, muss Implementierungen aller geerbten abstrakten Methoden und Accessoren enthalten.  
  
 In einer Methoden\- oder Eigenschaftendeklaration kann mit dem `abstract`\-Modifizierer angegeben werden, dass die Methode bzw. Eigenschaft keine Implementierung enthält.  
  
 Abstrakte Methoden weisen die nachstehenden Features auf:  
  
-   Eine abstrakte Methode stellt implizit eine virtuelle Methode dar.  
  
-   Abstrakte Methodendeklarationen sind nur in abstrakten Klassen zulässig.  
  
-   Da eine abstrakte Methodendeklaration keine Implementierung bereitstellt, ist kein Methodentext vorhanden. Die Methodendeklaration wird einfach mit einem Semikolon beendet, ohne dass der Signatur geschweifte Klammern \({ }\) folgen.  Beispiele:  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     Die Implementierung wird durch eine überschreibende Methode [override](../../../csharp/language-reference/keywords/override.md) bereitgestellt, bei der es sich um einen Member einer nicht abstrakten Klasse handelt.  
  
-   Die Modifizierer [static](../../../csharp/language-reference/keywords/static.md) oder [virtual](../../../csharp/language-reference/keywords/virtual.md) dürfen nicht in einer abstrakten Methodendeklaration verwendet werden.  
  
 Abstrakte Eigenschaften verhalten sich wie abstrakte Methoden, mit Ausnahme der Unterschiede bei der Deklaration und der Syntax für den Aufruf.  
  
-   Der `abstract`\-Modifizierer darf nicht für eine statische Eigenschaft verwendet werden.  
  
-   Eine abstrakte geerbte Eigenschaft kann in einer abgeleiteten Klasse überschrieben werden, indem eine Eigenschaftendeklaration, die den [override](../../../csharp/language-reference/keywords/override.md)\-Modifizierer verwendet, eingefügt wird.  
  
 Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Eine abstrakte Klasse muss eine Implementierung aller Schnittstellenmember bereitstellen.  
  
 Eine abstrakte Klasse, die eine Schnittstelle implementiert, ordnet die Schnittstellenmethoden möglicherweise abstrakten Methoden zu.  Beispiele:  
  
 [!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#2)]  
  
## Beispiel  
 In diesem Beispiel wird die `DerivedClass`\-Klasse von der abstrakten `BaseClass`\-Klasse abgeleitet.  Die abstrakte Klasse enthält eine abstrakte Methode \(`AbstractMethod`\) sowie zwei abstrakte Eigenschaften \(`X` und `Y`\).  
  
 [!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#3)]  
  
 Wenn Sie die abstrakte Klasse im voranstehenden Beispiel unter Verwendung einer Anweisung wie dieser instanziieren:  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 erhalten Sie eine Fehlermeldung, die besagt, dass der Compiler keine Instanz der abstrakten Klasse "BaseClass" erstellen kann.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Virtuell](../../../csharp/language-reference/keywords/virtual.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)