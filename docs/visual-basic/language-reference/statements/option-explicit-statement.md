---
title: Option Explicit-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 020f12f1fbb9a06647215f1fac6324e3b74e8a77
ms.lasthandoff: 03/13/2017

---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit-Anweisung (Visual Basic)
Erzwingt die explizite Deklaration aller Variablen in einer Datei oder die implizite Deklarationen von Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Teile  
 `On`  
 Optional. Ermöglicht `Option Explicit` überprüfen. Wenn `On` oder `Off` nicht angegeben ist, wird der Standardwert ist `On`.  
  
 `Off`  
 Optional. Deaktiviert die `Option Explicit` überprüfen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `Option Explicit On` oder `Option Explicit` wird in einer Datei müssen Sie alle Variablen explizit deklarieren, mit der `Dim` oder `ReDim` Anweisungen. Wenn Sie versuchen, einen nicht deklarierten Variablennamen verwenden, tritt ein Fehler zur Kompilierzeit. Die `Option Explicit Off` Anweisung ermöglicht die implizite Deklaration von Variablen.  
  
 Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
> [!NOTE]
>  Festlegen von `Option Explicit` zu `Off` ist im Allgemeinen nicht empfohlen. Sie könnten einen Variablennamen in einem oder mehreren Standorten, falsch schreiben, die was die unerwarteten Ergebnissen führen würde, wenn das Programm ausgeführt wird.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Wenn eine Option Explicit-Anweisung nicht vorhanden ist  
 Enthält der Quellcode kein `Option Explicit` -Anweisung, die **Option Explicit** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird. Wenn der Befehlszeile-Compiler verwendet wird, die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption verwendet wird.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Option Explicit in der IDE festlegen  
  
1.  In **Projektmappen-Explorer**, wählen Sie ein Projekt. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die **Kompilieren** Registerkarte.  
  
3.  Legen Sie den Wert der **Option Explicit** Feld.  
  
 Wenn Sie ein neues Projekt erstellen die **Option Explicit** auf der **Kompilieren** Registerkarte auf festgelegt ist die **Option Explicit** festlegen in der **VB-Standard** (Dialogfeld). Für den Zugriff auf die **VB-Standard** Dialogfelds die **Tools** Menü klicken Sie auf **Optionen**. In der **Optionen** Dialogfeld erweitern Sie **Projekte und Projektmappen**, und klicken Sie dann auf **VB-Standard**. Die ursprüngliche Standardeinstellung in **VB-Standard** ist `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Option Explicit in der Befehlszeile festlegen  
  
-   Enthalten die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Option Explicit` Anweisung, um die explizite Deklaration aller Variablen zu erzwingen. Versucht, eine nicht deklarierte Variable verwenden, verursacht einen Fehler zur Kompilierzeit.  
  
 [!code-vb[VbVbalrStatements&#47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements&#48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [VB-Standard, Projekte, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
