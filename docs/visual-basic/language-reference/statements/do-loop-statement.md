---
title: Do...Loop-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 9384cbb355189be448fa4b8d274721b4a7ca6a20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351255"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop-Anweisung (Visual Basic)
Wiederholt einen Anweisungsblock, während eine `Boolean` Bedingung `True` ist oder bis die Bedingung `True`wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`Do`|Erforderlich Startet die Definition der `Do` Schleife.|  
|`While`|Erforderlich, außer wenn `Until` verwendet wird. Wiederholen Sie die Schleife, bis `condition` `False`ist.|  
|`Until`|Erforderlich, außer wenn `While` verwendet wird. Wiederholen Sie die Schleife, bis `condition` `True`ist.|  
|`condition`|Optional. `Boolean` Ausdruck. Wenn `condition` `Nothing`ist, wird es von Visual Basic als `False`behandelt.|  
|`statements`|Optional. Eine oder mehrere-Anweisungen, die wiederholt werden, während oder bis `condition` sind `True`.|  
|`Continue Do`|Optional. Überträgt die Steuerung an die nächste Iterations `Do` Schleife.|  
|`Exit Do`|Optional. Überträgt die Steuerung aus der `Do` Schleife.|  
|`Loop`|Erforderlich Beendet die Definition der `Do` Schleife.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie eine `Do...Loop` Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, bis eine Bedingung erfüllt ist. Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
 Sie können entweder `While` oder `Until` verwenden, um `condition`anzugeben, aber nicht beides.  
  
 Sie können `condition` nur einmal entweder am Anfang oder am Ende der Schleife testen. Wenn Sie `condition` am Anfang der Schleife testen (in der `Do`-Anweisung), wird die Schleife möglicherweise nicht einmal ausgeführt. Wenn Sie am Ende der Schleife testen (in der `Loop`-Anweisung), wird die Schleife immer mindestens einmal ausgeführt.  
  
 Die Bedingung ergibt in der Regel einen Vergleich zweier Werte, kann jedoch ein beliebiger Ausdruck sein, der zu einem [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`) ausgewertet wird. Dies umfasst auch Werte anderer Datentypen, z. b. numerischer Typen, die in `Boolean`konvertiert wurden.  
  
 Sie können `Do` Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen. Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.  
  
> [!NOTE]
> Die `Do...Loop` Struktur bietet mehr Flexibilität als die [Zeit... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , da Sie Ihnen ermöglicht, zu entscheiden, ob die Schleife beendet werden soll, wenn `condition` beendet `True` wird, oder wenn Sie zum ersten Mal `True`wird. Außerdem können Sie `condition` entweder am Anfang oder am Ende der Schleife testen.  
  
## <a name="exit-do"></a>Beenden  
 Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine alternative Möglichkeit zum Beenden einer `Do…Loop`bereitstellen. `Exit Do` überträgt die Steuerung sofort an die Anweisung, die auf die `Loop` Anweisung folgt.  
  
 `Exit Do` wird häufig verwendet, wenn eine bestimmte Bedingung ausgewertet wird, z. b. in einer `If...Then...Else` Struktur. Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung. Eine Verwendung von `Exit Do` besteht darin, auf eine Bedingung zu testen, die eine *Endlosschleife*verursachen könnte. Dies ist eine Schleife, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann. Mit `Exit Do` können Sie die Schleife mit Escapezeichen versehen.  
  
 Sie können beliebig viele `Exit Do` Anweisungen in einem `Do…Loop`einschließen.  
  
 Wenn Sie in geschachtelten `Do` Schleifen verwendet wird, überträgt `Exit Do` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index`-Variable größer als 10 ist. Die `Until`-Klausel befindet sich am Ende der Schleife.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird anstelle einer `Until`-Klausel eine `While`-Klausel verwendet, und `condition` wird am Anfang der Schleife anstelle von am Ende getestet.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel beendet `condition` die Schleife, wenn die `index` Variable größer als 100 ist. Die `If` Anweisung in der Schleife bewirkt jedoch, dass die `Exit Do` Anweisung die Schleife beendet, wenn die Index Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen. Die <xref:System.IO.File.OpenText%2A>-Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> zurück, die die Zeichen liest. In der `Do...Loop` Bedingung bestimmt die <xref:System.IO.StreamReader.Peek%2A>-Methode des `StreamReader`, ob zusätzliche Zeichen vorhanden sind.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Siehe auch

- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
