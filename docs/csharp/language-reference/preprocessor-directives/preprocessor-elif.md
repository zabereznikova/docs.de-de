---
title: "#elif (C#-Referenz) | Microsoft Docs"
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
  - "#elif"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#elif-Direktive [C#]"
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #elif (C#-Referenz)
Mit `#elif` können zusammengesetzte bedingte Direktiven erstellt werden.  Der `#elif`\-Ausdruck wird ausgewertet, wenn weder der Ausdruck der vorangehenden [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)\-Direktive noch der Ausdruck einer vorangehenden \(optionalen\) `#elif`\-Direktive zu `true` ausgewertet wird.  Wenn ein `#elif`\-Ausdruck zu `true` ausgewertet wird, wird der gesamte Code zwischen der `#elif`\-Direktive und der nächsten bedingten Direktive vom Compiler ausgewertet.  Beispiel:  
  
```  
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 Die Operatoren `==` \(Gleichheit\), `!=` \(Ungleichheit\), `&&` \(und\) und `||` \(oder\) können zur Auswertung mehrerer Symbole verwendet werden.  Symbole und Operatoren können auch mit Klammern gruppiert werden.  
  
## Hinweise  
 `#elif` ist identisch mit der Verwendung von:  
  
```  
#else  
#if  
```  
  
 Die Verwendung von `#elif` ist jedoch einfacher, da für jedes `#if` ein [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) erforderlich ist, während ein `#elif` ohne ein entsprechendes `#endif` verwendet werden kann.  
  
 Unter [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#elif`.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)