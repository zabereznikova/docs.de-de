---
title: "readonly (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "readonly_CSharpKeyword"
  - "readonly"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "readonly-Schlüsselwort [C#]"
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# readonly (C#-Referenz)
Bei dem `readonly`\-Schlüsselwort handelt es sich um einen Modifizierer, der für Felder verwendet werden kann.  Wenn eine Felddeklaration einen `readonly`\-Modifizierer enthält, können Zuweisungen an die Felder, die durch die Deklaration eingeführt werden, nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen.  
  
## Beispiel  
 In diesem Beispiel kann der Wert des Felds `year` nicht mit der `ChangeYear`\-Methode geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen wurde:  
  
 [!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#14)]  
  
 Einem `readonly`\-Feld kann nur in den folgenden Fällen ein Wert zugewiesen werden:  
  
-   Beim Initialisieren der Variablen in der Deklaration, z. B.:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Für ein Instanzenfeld in den Instanzkonstruktoren der Klasse, die die Felddeklaration enthält, oder für ein statisches Feld im statischen Konstruktor der Klasse, die die Felddeklaration enthält.  Hierbei handelt sich auch um die einzigen Fälle, in denen ein `readonly`\-Feld als [out](../../../csharp/language-reference/keywords/out.md)\-Parameter oder als [ref](../../../csharp/language-reference/keywords/ref.md)\-Parameter übergeben werden darf.  
  
> [!NOTE]
>  Das `readonly`\-Schlüsselwort unterscheidet sich vom [const](../../../csharp/language-reference/keywords/const.md)\-Schlüsselwort.  Ein `const`\-Feld kann nur bei der Deklaration des Felds initialisiert werden.  Ein `readonly`\-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.  Daher können `readonly`\-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.  Außerdem ist ein `const`\-Feld eine Kompilierzeitkonstante, während ein `readonly`\-Feld für Laufzeitkonstanten verwendet werden kann. Siehe folgendes Beispiel:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## Beispiel  
 [!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#15)]  
  
 Wenn Sie im voranstehenden Beispiel eine Anweisung wie diese verwenden:  
  
 `p2.y = 66;        // Error`  
  
 wird folgende Compilerfehlermeldung angezeigt:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 Hierbei handelt es sich um denselben Fehler, der beim Zuweisen eines Werts zu einer Konstante auftritt.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)