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
ms.openlocfilehash: c027964d185d7f69c0a56a4386bedc2d8f9d2eac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912333"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit-Anweisung (Visual Basic)
Erzwingt die explizite Deklaration aller Variablen in einer Datei oder das zulassen impliziter Deklarationen von Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Teile  
 `On`  
 Optional. Aktiviert `Option Explicit` die Überprüfung. Wenn `On` `On`oder `Off` nicht angegeben wird, ist der Standardwert.  
  
 `Off`  
 Optional. Deaktiviert die Überprüfung. `Option Explicit`  
  
## <a name="remarks"></a>Hinweise  
 Wenn `Option Explicit On` `Dim` `ReDim` oder `Option Explicit` in einer Datei angezeigt wird, müssen Sie mithilfe der-oder-Anweisung explizit alle Variablen deklarieren. Wenn Sie versuchen, einen nicht deklarierten Variablennamen zu verwenden, tritt zum Zeitpunkt der Kompilierung ein Fehler auf. Die `Option Explicit Off` -Anweisung ermöglicht die implizite Deklaration von Variablen.  
  
 Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
> [!NOTE]
> Das `Option Explicit` festlegen `Off` von auf ist im Allgemeinen keine bewährte Vorgehensweise. Sie könnten den Namen einer Variable an einem oder mehreren Orten falsch buchstabieren, wodurch unerwartete Ergebnisse auftreten würden, wenn das Programm ausgeführt wird.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Wenn eine Option explizite Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine- `Option Explicit` Anweisung enthält, wird die **Option explizite** Einstellung auf der Seite "kompilieren" [, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet. Wenn der Befehlszeilen Compiler verwendet wird, wird die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption verwendet.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>So legen Sie die Option "explizit" in der IDE fest  
  
1. Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Legen Sie den Wert im Feld **Option explizit** fest.  
  
 Wenn Sie ein neues Projekt erstellen, wird die **Option explizite** Einstellung auf der Registerkarte **Kompilieren** auf die **Option explizite** Einstellung im Dialogfeld **VB-Standardeinstellungen** festgelegt. Um auf das Dialogfeld **VB-Standardeinstellungen** zuzugreifen , klicken Sie im Menü Extras auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standardeinstellungen** ist `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>So legen Sie die Option explizit in der Befehlszeile fest  
  
- Fügen Sie die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption in den **vbc** -Befehl ein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Option Explicit` -Anweisung verwendet, um die explizite Deklaration aller Variablen zu erzwingen. Der Versuch, eine nicht deklarierte Variable zu verwenden, verursacht einen Fehler zur Kompilierzeit.  
  
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
