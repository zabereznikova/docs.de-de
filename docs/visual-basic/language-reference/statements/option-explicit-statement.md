---
title: "Option Explicit Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Explicit"
  - "vb.OptionExplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring variables, explicit"
  - "forced variable declaration in Option Explicit statement"
  - "Explicit keyword"
  - "explicit variable declaration"
  - "Option Explicit statement"
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Option Explicit Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Erzwingt die explizite Deklaration aller Variablen in einer Datei oder ermöglicht die implizite Deklaration von Variablen.  
  
## Syntax  
  
```  
Option Explicit { On | Off }  
```  
  
## Teile  
 `On`  
 Optional.  Aktiviert die `Option Explicit`\-Überprüfung.  Wenn weder `On` noch `Off` angegeben ist, lautet der Standardwert `On`.  
  
 `Off`  
 Optional.  Deaktiviert die `Option Explicit`\-Überprüfung.  
  
## Hinweise  
 Wenn `Option Explicit On` oder `Option Explicit` in einer Datei angegeben wird, müssen alle Variablen explizit mit der `Dim`\-Anweisung oder der `ReDim`\-Anweisung deklariert werden.  Wenn Sie einen nicht deklarierten Variablennamen verwenden, tritt ein Fehler beim Kompilieren auf.  Die `Option Explicit Off`\-Anweisung ermöglicht implizite Deklaration von Variablen.  
  
 Bei Verwendung der `Option Explicit`\-Anweisung muss diese in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
> [!NOTE]
>  `Option Explicit` sollte normalerweise nicht auf `Off` festgelegt werden.  Sie könnten einen Variablennamen an einer oder mehreren Stellen falsch schreiben, was zu unerwarteten Ergebnissen führen würde, wenn das Programm ausgeführt wird.  
  
## Wenn eine Option Explicit\-Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine `Option Explicit`\-Anweisung enthält, wird die Einstellung **Option Explicit** auf der [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) verwendet.  Wenn der Befehlszeile\-Compiler verwendet wird, wird die [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)\-Compileroption verwendet.  
  
#### So legen Sie Option Explicit in der IDE fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Legen Sie den Wert im Feld **Option Explicit** fest.  
  
 Wenn Sie ein neues Projekt erstellen, wird die **Option Explicit**\-Einstellung auf der Registerkarte **Kompilieren** auf die **Option Explicit**\-Einstellung im Dialogfeld **VB\-Standard** festgelegt.  Um das Dialogfeld **VB\-Standard** zu öffnen, klicken Sie im Menü **Extras** auf **Optionen**.  Erweitern Sie im Dialogfeld **Optionen** die Option **Projekte und Projektmappen**, und klicken Sie dann auf **VB\-Standard**.  Die ursprüngliche Standardeinstellung in **VB\-Standard** ist `On`.  
  
#### So legen Sie Option Explicit in der Befehlszeile fest  
  
-   Fügen Sie die [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)\-Compileroption in den **vbc**\-Befehl ein.  
  
## Beispiel  
 Im folgenden Beispiel wird die `Option Explicit`\-Anweisung verwendet, um die explizite Deklaration aller Variablen zu erzwingen.  Wenn Sie eine nicht deklarierte Variable verwenden, tritt ein Fehler beim Kompilieren auf.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## Siehe auch  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [VB\-Standard, Projekte, Dialogfeld "Optionen"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)