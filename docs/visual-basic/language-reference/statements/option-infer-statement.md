---
title: Option Infer-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: 59766999c5b03aac7aec13b293feaa8c17f2ced0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338565"
---
# <a name="option-infer-statement"></a>Option Infer-Anweisung
Ermöglicht die Verwendung des lokalen Typrückschlusses beim Deklarieren von Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`On`|Dies ist optional. Ermöglicht den lokalen Typrückschluss.|  
|`Off`|Dies ist optional. Deaktiviert den lokalen Typrückschluss.|  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie zum Festlegen von `Option Infer` in einer Datei am Anfang der Datei `Option Infer On` oder `Option Infer Off` ein. Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.  
  
 Wenn Sie für `Option Infer``On` festlegen, können Sie lokale Variablen deklarieren, ohne explizit einen Datentyp anzugeben. Der Compiler leitet den Datentyp einer Variablen vom Typ des Initialisierungsausdrucks ab.  
  
 In der folgenden Abbildung ist `Option Infer` eingeschaltet. Die Variable in der Deklaration `Dim someVar = 2` wird als ganze Zahl durch Typrückschluss deklariert.

 Der folgende Screenshot zeigt IntelliSense, wenn Option Infer aktiviert ist: 
  
 ![Bildschirmabbildung von IntelliSense-Ansicht angezeigt, wenn Option Infer aktiviert ist.](./media/option-infer-statement/option-infer-as-integer-on.png)  
  
 In der folgenden Abbildung ist `Option Infer` deaktiviert. Die Variable in der Deklaration `Dim someVar = 2` ist durch Typrückschluss als `Object` deklariert. In diesem Beispiel die **Option Strict** Einstellung **aus** auf die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
 Der folgende Screenshot zeigt IntelliSense, wenn Option Infer deaktiviert ist:
 
 ![Bildschirmabbildung von IntelliSense-Ansicht angezeigt, wenn Option Infer deaktiviert ist.](./media/option-infer-statement/option-infer-as-object-off.png)  
  
> [!NOTE]
>  Wenn eine Variable als `Object`deklariert ist, kann sich der Laufzeittyp ändern, während das Programm ausgeführt wird. Visual Basic führt Operationen mit Bezeichnung *Boxing* und *unboxing* für die Konvertierung zwischen einer `Object` und ein Werttyp, der Ausführung langsamer macht. Weitere Informationen zu Boxing und unboxing finden Sie unter den [Visual Basic-Sprachspezifikation](~/_vblang/spec/conversions.md#value-type-conversions).
  
 Typrückschluss findet auf Prozedurebene Anwendung und nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.  
  
 Weitere Informationen finden Sie unter [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="when-an-option-infer-statement-is-not-present"></a>Wenn eine Option Infer-Anweisung nicht vorhanden ist  
 Wenn der Quellcode kein `Option Infer` -Anweisung, die **Option Infer** festlegen auf die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) wird verwendet. Wenn der Befehlszeilen-Compiler verwendet wird, die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption verwendet wird.  
  
#### <a name="to-set-option-infer-in-the-ide"></a>Festlegen der Option Infer in der IDE  
  
1. Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Legen Sie den Wert der **Option infer-** Feld.  
  
 Bei der Erstellung eines neuen Projekts die **Option Infer** festlegen auf die **Kompilieren** Registerkarte nastaven NA hodnotu der **Option Infer** festlegen in der **VB Defaults** Das Dialogfeld. Für den Zugriff auf die **VB Defaults** Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB Defaults** ist `On`.  
  
#### <a name="to-set-option-infer-on-the-command-line"></a>Festlegen der Option Infer in der Befehlszeile.  
  
-   Enthalten die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="default-data-types-and-values"></a>Standarddatentypen und -werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen, wie die `Option Infer`-Anweisung den lokalen Typrückschluss ermöglicht.  
  
 [!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, dass der Laufzeittyp abweichen kann, wenn eine Variable als ein `Object` gekennzeichnet ist.  
  
 [!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [VB-Standard, Projekte, Dialogfeld "Optionen"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
