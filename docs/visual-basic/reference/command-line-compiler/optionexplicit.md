---
title: "/optionexplicit | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optionexplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optionexplicit compiler option [Visual Basic]"
  - "optionexplicit compiler option [Visual Basic]"
  - "-optionexplicit compiler option [Visual Basic]"
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /optionexplicit
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bewirkt, dass der Compiler Fehler meldet, wenn Variablen vor der Verwendung nicht deklariert wurden.  
  
## Syntax  
  
```  
/optionexplicit[+ | -]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Optional.  Gibt an, dass für `/optionexplicit+` Variablen explizit deklariert werden müssen.  Die `/optionexplicit+`\-Option ist die Standardoption. Sie ist identisch mit `/optionexplicit`.  Die `/optionexplicit-`\-Option ermöglicht die implizite Deklaration von Variablen.  
  
## Hinweise  
 Wenn die Quellcodedatei ein [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) enthält, überschreibt die Anweisung die `/optionexplicit`\-Befehlszeilencompiler\-Einstellung.  
  
### So legen Sie \/optionexplicit in der Visual Studio\-IDE fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Ändern Sie den Wert im Feld **Option Explicit**.  
  
## Beispiel  
 Der folgende Code wird kompiliert, wenn `/optionexplicit-` angegeben wird.  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [VB\-Standard, Projekte, Dialogfeld "Optionen"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)