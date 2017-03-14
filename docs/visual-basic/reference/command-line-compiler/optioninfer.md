---
title: "/optioninfer | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optioninfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-optioninfer compiler option [Visual Basic]"
  - "/optioninfer compiler option [Visual Basic]"
  - "optioninfer compiler option [Visual Basic]"
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /optioninfer
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.  
  
## Syntax  
  
```  
/optioninfer[+ | -]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`+`  &#124; `-`|Dies ist optional.  Geben Sie `/optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `/optioninfer-` zu blockieren.  Die `/optioninfer` \-Option ohne angegebenen Wert entspricht dem `/optioninfer+`.  Der Standardwert, wenn die `/optioninfer` Switch nicht vorhanden ist, ist auch `/optioninfer+`.  Der Standardwert ist in der Vbc.rsp\-Antwortdatei festgelegt.|  
  
> [!NOTE]
>  Sie können die `/noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten.  Der Compilerstandardwert für diese Option ist `/optioninfer-`.  
  
## Hinweise  
 Wenn die Quellcodedatei einen [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) enthält, überschreibt die Anweisung die `/optioninfer`\-Befehlszeilencompiler\-Einstellung.  
  
### Festlegen von \/ Optioninfer in der Visual Studio\-IDE  
  
1.  Wählen Sie ein Projektverzeichnis im **Lösungs\-Explorer** aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/de-de/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Ändern Sie auf der Registerkarte **Zusammenstellen** den Wert im Textfeld **Option infer** ein.  
  
## Beispiel  
 Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [VB\-Standard, Projekte, Dialogfeld "Optionen"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Erstellen von der Befehlszeile aus](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)