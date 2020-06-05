---
title: Option Explicit-Anweisung
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
ms.openlocfilehash: a352df0323cfeca1ea0e206ae45c3f85a2cd7da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404368"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit-Anweisung (Visual Basic)
Erzwingt die explizite Deklaration aller Variablen in einer Datei oder das zulassen impliziter Deklarationen von Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Bestandteile  
 `On`  
 Optional. Aktiviert die über `Option Explicit` Prüfung. Wenn `On` oder `Off` nicht angegeben wird, ist der Standardwert `On` .  
  
 `Off`  
 Optional. Deaktiviert die über `Option Explicit` Prüfung.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn `Option Explicit On` oder `Option Explicit` in einer Datei angezeigt wird, müssen Sie mithilfe der-oder-Anweisung explizit alle Variablen deklarieren `Dim` `ReDim` . Wenn Sie versuchen, einen nicht deklarierten Variablennamen zu verwenden, tritt zum Zeitpunkt der Kompilierung ein Fehler auf. Die- `Option Explicit Off` Anweisung ermöglicht die implizite Deklaration von Variablen.  
  
 Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
> [!NOTE]
> Das Festlegen `Option Explicit` von auf `Off` ist im Allgemeinen keine bewährte Vorgehensweise. Sie könnten den Namen einer Variable an einem oder mehreren Orten falsch buchstabieren, wodurch unerwartete Ergebnisse auftreten würden, wenn das Programm ausgeführt wird.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Wenn eine Option explizite Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine- `Option Explicit` Anweisung enthält, wird die **Option explizite** Einstellung auf der Seite "kompilieren" [, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet. Wenn der Befehlszeilen Compiler verwendet wird, wird die [-optionexplizite-Compileroption](../../reference/command-line-compiler/optionexplicit.md) verwendet.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>So legen Sie die Option "explizit" in der IDE fest  
  
1. Wählen Sie in **Projektmappen-Explorer**ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Legen Sie den Wert im Feld **Option explizit** fest.  
  
 Wenn Sie ein neues Projekt erstellen, wird die **Option explizite** Einstellung auf der Registerkarte **Kompilieren** auf die **Option explizite** Einstellung im Dialogfeld **VB-Standardeinstellungen** festgelegt. Um auf das Dialogfeld **VB-Standardeinstellungen** zuzugreifen, klicken Sie **im Menü Extras** auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen****Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standardeinstellungen** ist `On` .  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>So legen Sie die Option explizit in der Befehlszeile fest  
  
- Schließen Sie die [-optionexplizite-](../../reference/command-line-compiler/optionexplicit.md) Compileroption in den **vbc** -Befehl ein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die- `Option Explicit` Anweisung verwendet, um die explizite Deklaration aller Variablen zu erzwingen. Der Versuch, eine nicht deklarierte Variable zu verwenden, verursacht einen Fehler zur Kompilierzeit.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Dim-Anweisung](dim-statement.md)
- [ReDim-Anweisung](redim-statement.md)
- [Option Compare-Anweisung](option-compare-statement.md)
- [Option Strict-Anweisung](option-strict-statement.md)
- [-optioncompare](../../reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../reference/command-line-compiler/optionstrict.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
