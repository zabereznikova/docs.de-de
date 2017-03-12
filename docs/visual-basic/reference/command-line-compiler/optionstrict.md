---
title: "/optionstrict | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optionstrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-optionstrict compiler option [Visual Basic]"
  - "optionstrict compiler option [Visual Basic]"
  - "/optionstrict compiler option [Visual Basic]"
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /optionstrict
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Erzwingt strikte Semantik, um implizite Konvertierungen zu beschränken.  
  
## Syntax  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Optional.  Die `/optionstrict+`\-Option schränkt die implizite Typkonvertierung ein.  Der Standardwert für diese Option ist `/optionstrict-`.  Die `/optionstrict+`\-Option entspricht `/optionstrict`.  Sie können beide für eine freie Typsemantik verwenden.  
  
 `custom`  
 Erforderlich.  Warnhinweis, wenn eine strikte Sprachsemantik nicht eingehalten wird.  
  
## Hinweise  
 Wenn `/optionstrict+` aktiviert ist, können nur Erweiterungskonvertierungen implizit vorgenommen werden.  Implizite einschränkende Typkonvertierungen, z. B. das Zuweisen eines Objekts vom Typ `Decimal` zu einem Objekt von einem Integer\-Typ, werden als Fehler gemeldet.  
  
 Um Warnungen für implizite einschränkende Typkonvertierungen zu generieren, verwenden Sie `/optionstrict:custom`.  Verwenden Sie `/nowarn:numberlist`, um bestimmte Warnungen zu ignorieren, und `/warnaserror:numberlist`, um bestimmte Warnungen als Fehler zu behandeln.  
  
### So legen Sie \/optionstrict in der Visual Studio\-IDE fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Ändern Sie den Wert im Feld **Option Strict**.  
  
### So legen Sie \/optionstrict programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## Beispiel  
 Mit dem folgenden Code wird `Test.vb` unter Verwendung von strikter Semantik kompiliert.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [\/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [VB\-Standard, Projekte, Dialogfeld "Optionen"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)