---
title: "switch (C#-Referenz) | Microsoft Docs"
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
  - "switch_CSharpKeyword"
  - "switch"
  - "case"
  - "case_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "switch-Anweisung [C#]"
  - "switch-Schlüsselwort [C#]"
  - "case-Anweisung [C#]"
  - "default-Schlüsselwort [C#]"
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
caps.handback.revision: 47
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# switch (C#-Referenz)
Die `switch`\-Anweisung ist eine Steuerungsanweisung, die einen auszuführenden *switch\-Abschnitt* aus einer Liste von Kandidaten auswählt.  
  
 Eine `switch`\-Anweisung enthält eine oder mehrere switch\-Abschnitte.  Jeder switch\-Abschnitt enthält eine oder mehrere *case\-Bezeichnungen* und eine Liste mit mindestens einer Anweisung.  Das folgende Beispiel zeigt eine einfache `switch`\-Anweisung, die über drei switch\-Abschnitte verfügt.  Jeder switch\-Abschnitt enthält eine case\-Bezeichnung, z. B. `case 1`, und zwei Anweisungen.  
  
 [!code-cs[csrefKeywordsSelection#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/switch_1.cs)]  
  
## Hinweise  
 Jede case\-Bezeichnung gibt einen konstanten Wert an.  Mit der switch\-Anweisung wird die Steuerung an den switch\-Abschnitt übergeben, dessen case\-Bezeichnung dem Wert im *switch\-Ausdruck* \(in diesem Beispiel `caseSwitch`\) entspricht.  Wenn keine case\-Bezeichnung einen übereinstimmenden Wert enthält, wird die Steuerung an den `default`\-Abschnitt übertragen, falls vorhanden.  Wenn kein `default`\-Abschnitt vorhanden ist, wird keine Aktion ausgeführt, und der `switch`\-Anweisung wird die Steuerung entzogen.  Im vorherigen Beispiel werden die Anweisungen im ersten switch\-Abschnitt ausgeführt, da `case 1` dem Wert von `caseSwitch` entspricht.  
  
 Eine `switch`\-Anweisung kann eine beliebige Anzahl von switch\-Abschnitten enthalten, und jeder Abschnitt kann eine oder mehrere case\-Bezeichnungen haben \(wie im Beispiel mit den case\-Bezeichnungen für Zeichenfolgen weiter unten dargestellt\).  Allerdings können zwei case\-Bezeichnungen nicht denselben konstanten Wert enthalten.  
  
 Die Ausführung der Anweisungsliste im ausgewählten switch\-Abschnitt beginnt mit der ersten Anweisung und durchläuft in der Regel die Anweisungsliste, bis eine jump\-Anweisung erreicht wird, z. B. `break`, `goto case`, `return` oder `throw`.  An diesem Punkt wird die Steuerung der `switch`\-Anweisung entzogen oder an eine andere case\-Bezeichnung übertragen.  
  
 Im Gegensatz zu C\+\+ lässt C\# nicht zu, dass die Ausführung von einem switch\-Abschnitt zum nächsten fortgesetzt wird.  Im folgenden Code wird ein Fehler verursacht.  
  
```c#  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
  
 In C\# muss das Ende von switch\-Abschnitten, einschließlich dem letzten Abschnitt, nicht erreichbar sein.  Das heißt, anders als in einigen anderen Sprachen, kann der Code nicht mit dem nächsten switch\-Abschnitt fortfahren.  Obwohl diese Bedingung normalerweise mithilfe einer `break`\-Anweisung erfüllt wird, ist der folgende Fall auch zulässig, da hier das Ende der Anweisungsliste auf keinen Fall erreicht werden kann.  
  
```c#  
case 4:  
    while (true)  
        Console.WriteLine("Endless looping. . . .");  
```  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Anforderungen und Funktionen einer `switch`\-Anweisung.  
  
 [!code-cs[csrefKeywordsSelection#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/switch_2.cs)]  
  
## Beispiel  
 Im abschließenden Beispiel steuern die Zeichenfolgenvariable, `str` und die case\-Bezeichnungen für Zeichenfolgen den Ausführungsablauf.  
  
 [!code-cs[csrefKeywordsSelection#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/switch_3.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [switch\-Anweisung \(C\+\+\)](/visual-cpp/cpp/switch-statement-cpp)   
 [if\-else](../../../csharp/language-reference/keywords/if-else.md)