---
title: "Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Befehlszeilenargumente [C#], Anzeigen"
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)
`Main` kann auf Argumente, die einer ausführbaren Datei in der Befehlszeile bereitgestellt werden, über einen optionalen Parameter zugreifen.  Die Argumente werden als Zeichenfolgenarray bereitgestellt.  Jedes Element des Arrays enthält ein Argument.  Leerraum zwischen Argumenten wird entfernt.  Betrachten Sie z. B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:  
  
|Eingabe in der Befehlszeile|An Main übergebenes Zeichenfolgenarray|  
|---------------------------------|--------------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente im [Seite "Debuggen", Projekt\-Designer](/visual-studio/ide/reference/debug-page-project-designer) angeben.  
  
## Beispiel  
 In diesem Beispiel werden die an eine Befehlszeilenanwendung übergebenen Befehlszeilenargumente angezeigt.  Die angezeigte Ausgabe betrifft den ersten Eintrag in der Tabelle oben.  
  
 [!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Main\(\) und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main\(\)\-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)