---
title: Option Infer-Anweisung
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
ms.openlocfilehash: 53bc9d41f28f63061db2012395480aa6be7515dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346497"
---
# <a name="option-infer-statement"></a>Option Infer-Anweisung

Ermöglicht die Verwendung des lokalen Typrückschlusses beim Deklarieren von Variablen.

## <a name="syntax"></a>Syntax

```vb
Option Infer { On | Off }
```

## <a name="parts"></a>-Komponenten

|Begriff|Definition|
|---|---|
|`On`|Optional. Ermöglicht den lokalen Typrückschluss.|
|`Off`|Optional. Deaktiviert den lokalen Typrückschluss.|

## <a name="remarks"></a>Hinweise

Geben Sie zum Festlegen von `Option Infer` in einer Datei am Anfang der Datei `Option Infer On` oder `Option Infer Off` ein. Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.

Wenn Sie für `Option Infer``On` festlegen, können Sie lokale Variablen deklarieren, ohne explizit einen Datentyp anzugeben. Der Compiler leitet den Datentyp einer Variablen vom Typ des Initialisierungsausdrucks ab.

In der folgenden Abbildung ist `Option Infer` eingeschaltet. Die Variable in der Deklaration `Dim someVar = 2` wird als ganze Zahl durch Typrückschluss deklariert.

Der folgende Screenshot zeigt IntelliSense, wenn Option Infer auf on gilt:

![Screenshot der IntelliSense-Ansicht, wenn die Option Infer On ist.](./media/option-infer-statement/option-infer-as-integer-on.png)

In der folgenden Abbildung ist `Option Infer` deaktiviert. Die Variable in der Deklaration `Dim someVar = 2` ist durch Typrückschluss als `Object` deklariert. In diesem Beispiel ist die **Option Strict** -Einstellung auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)auf **Off** festgelegt.

Der folgende Screenshot zeigt IntelliSense, wenn die Option Infer deaktiviert ist:

![Screenshot der IntelliSense-Ansicht, wenn die Option Infer deaktiviert ist.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> Wenn eine Variable als `Object`deklariert ist, kann sich der Laufzeittyp ändern, während das Programm ausgeführt wird. Visual Basic führt Vorgänge aus, die als *Boxing* und *Unboxing* bezeichnet werden, um zwischen einem `Object` und einem Werttyp zu konvertieren, wodurch die Ausführung langsamer wird. Weitere Informationen zu Boxing und Unboxing finden Sie in der [Visual Basic-Sprachspezifikation](~/_vblang/spec/conversions.md#value-type-conversions).

Typrückschluss findet auf Prozedurebene Anwendung und nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.

Weitere Informationen finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

## <a name="when-an-option-infer-statement-is-not-present"></a>Wenn eine Option Infer-Anweisung nicht vorhanden ist

Wenn der Quellcode keine `Option Infer`-Anweisung enthält, wird die Einstellung **Option Infer** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet. Wenn der Befehlszeilen Compiler verwendet wird, wird die [-optioninfer-Compileroption](../../../visual-basic/reference/command-line-compiler/optioninfer.md) verwendet.

#### <a name="to-set-option-infer-in-the-ide"></a>Festlegen der Option Infer in der IDE

1. Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie auf die Registerkarte **Kompilieren**.

3. Legen Sie den Wert im Feld **Option ableiten** fest.

Wenn Sie ein neues Projekt erstellen, wird die Einstellung **Option Infer** auf der Registerkarte **Kompilieren** auf die Einstellung **Option Infer** im Dialogfeld **VB-Standardwerte** festgelegt. Um auf das Dialogfeld **VB-Standardeinstellungen** zuzugreifen, klicken Sie **im Menü Extras** auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standardeinstellungen** ist `On`.

#### <a name="to-set-option-infer-on-the-command-line"></a>Festlegen der Option Infer in der Befehlszeile.

Schließen Sie die [-optioninfer-](../../../visual-basic/reference/command-line-compiler/optioninfer.md) Compileroption in den **vbc** -Befehl ein.

## <a name="default-data-types-and-values"></a>Standarddatentypen und -werte

Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.

|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|
|---|---|---|---|
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Siehe [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|
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
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
