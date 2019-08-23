---
title: Do...Loop-Anweisung (Visual Basic)
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
ms.openlocfilehash: 75a2129a9f332024831d97021e381f1b3d4fa048
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942998"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop-Anweisung (Visual Basic)
Wiederholt einen Anweisungsblock, `Boolean` während eine `True` Bedingung ist oder bis die `True`Bedingung wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`Do`|Erforderlich. Startet die Definition der `Do` Schleife.|  
|`While`|Erforderlich, außer wenn `Until` verwendet wird. Wiederholen Sie die `condition` Schleife `False`, bis ist.|  
|`Until`|Erforderlich, außer wenn `While` verwendet wird. Wiederholen Sie die `condition` Schleife `True`, bis ist.|  
|`condition`|Optional. `Boolean`Begriff. Wenn `condition`den Wert `False`hat, wird er von Visual Basic behandelt. `Nothing`|  
|`statements`|Optional. Eine oder mehrere-Anweisungen, die während oder bis `condition` `True`wiederholt werden, sind.|  
|`Continue Do`|Optional. Überträgt die Steuerung an die nächste Iterations `Do` Schleife.|  
|`Exit Do`|Optional. Überträgt die Steuerung aus der `Do` Schleife.|  
|`Loop`|Erforderlich. Beendet die Definition der `Do` Schleife.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `Do...Loop` eine Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, bis eine Bedingung erfüllt ist. Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
 Sie können entweder `While` oder `Until` verwenden, um `condition`anzugeben, aber nicht beides.  
  
 Sie können nur `condition` einmal, entweder am Anfang oder am Ende der Schleife, testen. Wenn Sie zu `condition` Beginn der Schleife testen (in der `Do` -Anweisung), wird die Schleife möglicherweise nicht einmal ausgeführt. Wenn Sie am Ende der Schleife testen (in der `Loop` -Anweisung), wird die Schleife immer mindestens einmal ausgeführt.  
  
 Die Bedingung ergibt in der Regel einen Vergleich zweier Werte, kann jedoch ein beliebiger Ausdruck sein, der zu einem [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert`True` ( `False`oder) ausgewertet wird. Dies umfasst auch Werte anderer Datentypen, z. b. numerischer Typen, die in `Boolean`konvertiert wurden.  
  
 Sie können `Do` Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen. Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.  
  
> [!NOTE]
> Die `Do...Loop` Struktur bietet mehr Flexibilität als die [Zeit... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , da Sie Ihnen ermöglicht, zu entscheiden, ob die `condition` Schleife beendet `True` werden soll, wenn Sie `True`nicht mehr oder erst endet. Außerdem können Sie Sie entweder am `condition` Anfang oder am Ende der Schleife testen.  
  
## <a name="exit-do"></a>Beenden  
 Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine alternative Möglichkeit zum Beenden eines `Do…Loop`bereitstellen. `Exit Do`überträgt die Steuerung sofort an die-Anweisung, `Loop` die auf die-Anweisung folgt.  
  
 `Exit Do`wird häufig verwendet, wenn eine bestimmte Bedingung ausgewertet wird, z. `If...Then...Else` b. in einer-Struktur. Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung. Eine Verwendung von `Exit Do` besteht darin, auf eine Bedingung zu testen, die zu einer *Endlosschleife*führen könnte, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen könnte. Mithilfe `Exit Do` von können Sie die Schleife mit Escapezeichen versehen.  
  
 Sie können eine beliebige Anzahl von `Exit Do` -Anweisungen an beliebiger Stelle in einem `Do…Loop`einschließen.  
  
 `Exit Do` Überträgt bei Verwendung in `Do` geschachtelten Schleifen die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index` -Variable größer als 10 ist. Die `Until` -Klausel befindet sich am Ende der-Schleife.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird anstelle `While` einer `Until` -Klausel eine-Klausel verwendet `condition` , und wird am Anfang der Schleife anstelle von am Ende getestet.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `condition` -Schleife beendet, wenn `index` die-Variable größer als 100 ist. Die `If` -Anweisung in der-Schleife bewirkt jedoch, `Exit Do` dass die-Anweisung die-Schleife beendet, wenn die Index Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen. Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt <xref:System.IO.StreamReader> einen zurück, der die Zeichen liest. In der `Do...Loop` Bedingung `StreamReader` bestimmt die <xref:System.IO.StreamReader.Peek%2A> -Methode von, ob zusätzliche Zeichen vorhanden sind.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Siehe auch

- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
