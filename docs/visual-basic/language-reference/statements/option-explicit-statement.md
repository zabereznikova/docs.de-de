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
ms.openlocfilehash: bfedda6dba7f21efa8e808e85869e6f96710e11b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965877"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit-Anweisung (Visual Basic)
Erzwingt die explizite Deklaration aller Variablen in einer Datei oder die implizite Deklarationen von Variablen.  
  
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
 Wenn `Option Explicit On` oder `Option Explicit` wird in einer Datei müssen Sie explizit alle Variablen deklarieren, mit der `Dim` oder `ReDim` Anweisungen. Wenn Sie versuchen, einen nicht deklarierten Variablennamen verwenden, tritt ein Fehler zur Kompilierzeit auf. Die `Option Explicit Off` -Anweisung können implizite Deklaration von Variablen.  
  
 Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
> [!NOTE]
>  Festlegen von `Option Explicit` zu `Off` ist im Allgemeinen nicht empfohlen. Sie könnten den Namen einer Variable an einem oder mehreren Orten falsch buchstabieren, wodurch unerwartete Ergebnisse auftreten würden, wenn das Programm ausgeführt wird.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Wenn eine Option Explicit-Anweisung nicht vorhanden ist  
 Wenn der Quellcode kein `Option Explicit` -Anweisung, die **Option Explicit** festlegen auf die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) wird verwendet. Wenn der Befehlszeilen-Compiler verwendet wird, die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption verwendet wird.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Option Explicit festlegen, in der IDE  
  
1.  Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Legen Sie den Wert der **Option Explicit** Feld.  
  
 Bei der Erstellung eines neuen Projekts die **Option Explicit** festlegen auf die **Kompilieren** Registerkarte nastaven NA hodnotu der **Option Explicit** festlegen in der **VB Defaults**Dialogfeld. Für den Zugriff auf die **VB Defaults** Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB Defaults** ist `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Option Explicit in der Befehlszeile festlegen  
  
-   Enthalten die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Option Explicit` Anweisung, um die explizite Deklaration aller Variablen zu erzwingen. Es wird versucht, eine nicht deklarierte Variable verwenden, tritt ein Fehler zum Zeitpunkt der Kompilierung.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>Siehe auch
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
