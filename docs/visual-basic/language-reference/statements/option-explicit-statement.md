---
title: Option Explicit-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 3a2d81b1441052c132e4739dfe6045f8c3a026d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit-Anweisung (Visual Basic)
Erzwingt die explizite Deklaration aller Variablen in einer Datei oder die Erweiterung impliziter Deklarationen von Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Teile  
 `On`  
 Dies ist optional. Ermöglicht `Option Explicit` überprüfen. Wenn `On` oder `Off` nicht angegeben ist, wird der Standardwert ist `On`.  
  
 `Off`  
 Dies ist optional. Deaktiviert die `Option Explicit` überprüfen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `Option Explicit On` oder `Option Explicit` wird in einer Datei müssen Sie alle Variablen explizit deklarieren, indem die `Dim` oder `ReDim` Anweisungen. Wenn Sie versuchen, einen nicht deklarierten Variablennamen verwenden, tritt ein Fehler zur Kompilierzeit. Die `Option Explicit Off` Anweisung ermöglicht die implizite Deklaration von Variablen.  
  
 Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
> [!NOTE]
>  Festlegen von `Option Explicit` auf `Off` sind im Allgemeinen nicht empfohlen. Sie könnten den Namen einer Variable an einem oder mehreren Orten falsch buchstabieren, wodurch unerwartete Ergebnisse auftreten würden, wenn das Programm ausgeführt wird.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Wenn eine Option Explicit-Anweisung nicht vorhanden ist  
 Wenn der Quellcode nicht enthält ein `Option Explicit` -Anweisung, die **Option Explicit** festlegen für die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird. Wenn Sie der Befehlszeilencompiler verwendet wird, die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption verwendet wird.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Option Explicit festlegen, in der IDE  
  
1.  Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Legen Sie den Wert der **Option Explicit** Feld.  
  
 Bei der Erstellung eines neuen Projekts die **Option Explicit** festlegen, auf die **Kompilieren** auf die Registerkarte "festgelegt ist die **Option Explicit** festlegen in der **VB Defaults**(Dialogfeld). Für den Zugriff auf die **VB Defaults** Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standard** ist `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Option Explicit in der Befehlszeile festlegen  
  
-   Enthalten die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Option Explicit` Anweisung, um die explizite Deklaration aller Variablen durchzusetzen. Versucht, eine nicht deklarierte Variable verwenden, verursacht einen Fehler zur Kompilierzeit.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
