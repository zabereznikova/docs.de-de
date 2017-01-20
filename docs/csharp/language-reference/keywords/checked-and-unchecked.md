---
title: "Checked und Unchecked (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked-Anweisung [C#]"
  - "Ausnahmen [C#], Überlaufüberprüfung"
  - "Operatoren [C#], checked und unchecked"
  - "Überlaufüberprüfung [C#]"
  - "Anweisungen [C#], checked und unchecked"
  - "unchecked-Anweisung [C#]"
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Checked und Unchecked (C#-Referenz)
C\#\-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext \(checked oder unchecked\) ausgeführt werden.  In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus.  In einem nicht geprüften Kontext wird der arithmetische Überlauf ignoriert, und das Ergebnis wird abgeschnitten.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) Gibt einen geprüften Kontext an.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) Gibt einen ungeprüften Kontext an.  
  
 Wenn weder `checked` noch `unchecked` angegeben wird, ist der Standardkontext von externen Faktoren wie Compileroptionen abhängig.  
  
 Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:  
  
-   Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:  
  
     `++`  `--` \- \(unary\)   `+` \-   `*` `/`  
  
-   Explizite numerische Konvertierungen zwischen ganzzahligen Typen.  
  
 Mit der [\/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)\-Compileroption können Sie einen geprüften oder nicht geprüften Kontext für alle ganzzahligen arithmetischen Anweisungen angeben, die nicht explizit im Umfang eines `checked`\- oder `unchecked`\-Schlüsselworts enthalten sind.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Anweisungsschlüsselwörter](../../../csharp/language-reference/keywords/statement-keywords.md)