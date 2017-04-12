---
title: / optioninfer | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0c0b6d8361e2bd59837161d1135b100e66d40887
ms.lasthandoff: 03/13/2017

---
# <a name="optioninfer"></a>/optioninfer
Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Geben Sie `/optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `/optioninfer-` zu blockieren. Die `/optioninfer` -Option ohne angegebenen Wert entspricht dem `/optioninfer+`. Der Standardwert, wenn die `/optioninfer` Switch nicht vorhanden ist, ist auch `/optioninfer+`. Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.|  
  
> [!NOTE]
>  Sie können die `/noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten. Der Compilerstandardwert für diese Option ist `/optioninfer-`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Quellcodedatei enthält eine [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md), überschreibt die Anweisung die `/optioninfer` Befehlszeilencompiler-Einstellung.  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a>Festlegen von / Optioninfer in der Visual Studio-IDE  
  
1.  Wählen Sie ein Projekt in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [NIB: Verwalten von Projekteigenschaften mit dem Projekt-Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Auf der **Kompilieren** Registerkarte, ändern Sie den Wert in der **Option infer** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Visual Basic Standard, Projekte, Optionen (Dialogfeld)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Erstellen von der Befehlszeile aus](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
