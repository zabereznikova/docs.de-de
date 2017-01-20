---
title: "volatile (C#-Referenz) | Microsoft Docs"
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
  - "volatile_CSharpKeyword"
  - "volatile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "volatile-Schlüsselwort [C#]"
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# volatile (C#-Referenz)
Das `volatile`\-Schlüsselwort gibt an, dass ein Feld von mehreren gleichzeitig ausgeführten Threads geändert werden kann.  Mit `volatile` deklarierte Felder unterliegen nicht den Compileroptimierungen, für die der Zugriff durch einen Thread Voraussetzung ist.  Auf diese Weise wird sichergestellt, dass im Feld stets der aktuelle Wert vorhanden ist.  
  
 Der `volatile`\-Modifizierer wird normalerweise für ein Feld verwendet, auf das mehrere Threads zugreifen, ohne dass die [lock](../../../csharp/language-reference/keywords/lock-statement.md)\-Anweisung zur Zugriffsserialisierung verwendet wird.  
  
 Das `volatile`\-Schlüsselwort kann auf Felder der folgenden Typen angewendet werden:  
  
-   Referenztypen.  
  
-   Zeigertypen \(in einem unsicheren Kontext\)  Beachten Sie, dass der Zeiger flüchtig sein kann, das Objekt, auf den er zeigt, jedoch nicht.  Mit anderen Worten können Sie keinen "Zeiger auf volatile" deklarieren.  
  
-   Typen wie sbyte, byte, short, ushort, int, uint, char, float und bool.  
  
-   Ein Enumerationstyp mit einem der folgenden Basistypen: byte, sbyte, short, ushort, int oder uint.  
  
-   Generische Typparameter, von denen bekannt ist, dass sie Referenztypen sind.  
  
-   <xref:System.IntPtr> und <xref:System.UIntPtr>.  
  
 Das volatile\-Schlüsselwort kann nur auf Felder einer Klasse oder Struktur angewendet werden.  Lokale Variablen können nicht als `volatile` deklariert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine public\-Feldvariable als `volatile` deklariert wird.  
  
 [!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#24)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs\- bzw. Arbeitsthread erstellt und für die Verarbeitung parallel zum primären Thread verwendet werden kann.  Hintergrundinformationen zum Multithreading finden Sie unter [Threading](../Topic/Managed%20Threading.md) und [Threading](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)  
  
 [!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)