---
title: "Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Befehlszeilenargumente [C#]"
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach (C#-Programmierhandbuch)
Ein weiteres Verfahren zum Durchlaufen von Arrays wird im nachfolgenden Beispiel veranschaulicht: die Verwendung der [foreach](../../../csharp/language-reference/keywords/foreach-in.md)\-Anweisung.  Die `foreach`\-Anweisung kann verwendet werden, um ein Array, eine .NET Framework\-Auflistungsklasse oder eine beliebige Klasse bzw. Struktur zu durchlaufen, die die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert.  
  
> [!NOTE]
>  Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente im [Seite "Debuggen", Projekt\-Designer](/visual-studio/ide/reference/debug-page-project-designer) angeben.  
  
## Beispiel  
 In diesem Beispiel wird die Ausgabe der Befehlszeilenargumente mithilfe von `foreach` verdeutlicht.  
  
 [!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## Siehe auch  
 <xref:System.Array>   
 <xref:System.Collections>   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Main\(\) und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Gewusst wie: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Main\(\)\-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)