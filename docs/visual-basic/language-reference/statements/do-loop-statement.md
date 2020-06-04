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
ms.openlocfilehash: a9ec6caccbe161a39b592a642a938b81bae911a6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404783"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop-Anweisung (Visual Basic)
Wiederholt einen Anweisungsblock, während eine `Boolean` Bedingung ist `True` oder bis die Bedingung wird `True` .  
  
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
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`Do`|Erforderlich. Startet die Definition der `Do` Schleife.|  
|`While`|Erforderlich, außer wenn `Until` verwendet wird. Wiederholen Sie die Schleife, bis `condition` ist `False` .|  
|`Until`|Erforderlich, außer wenn `While` verwendet wird. Wiederholen Sie die Schleife, bis `condition` ist `True` .|  
|`condition`|Optional. `Boolean`-Ausdruck. Wenn den Wert `condition` `Nothing` hat, wird er von Visual Basic behandelt `False` .|  
|`statements`|Optional. Eine oder mehrere-Anweisungen, die während oder bis wiederholt werden, sind `condition` `True` .|  
|`Continue Do`|Optional. Überträgt die Steuerung an die nächste Iterations `Do` Schleife.|  
|`Exit Do`|Optional. Überträgt die Steuerung aus der `Do` Schleife.|  
|`Loop`|Erforderlich. Beendet die Definition der `Do` Schleife.|  
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden `Do...Loop` Sie eine Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, bis eine Bedingung erfüllt ist. Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
 Sie können entweder `While` oder verwenden `Until` , um anzugeben `condition` , aber nicht beides.  
  
 Sie können `condition` nur einmal, entweder am Anfang oder am Ende der Schleife, testen. Wenn Sie `condition` zu Beginn der Schleife testen (in der- `Do` Anweisung), wird die Schleife möglicherweise nicht einmal ausgeführt. Wenn Sie am Ende der Schleife testen (in der- `Loop` Anweisung), wird die Schleife immer mindestens einmal ausgeführt.  
  
 Die Bedingung ergibt in der Regel einen Vergleich zweier Werte, kann jedoch ein beliebiger Ausdruck sein, der zu einem [booleschen Datentyp](../data-types/boolean-data-type.md) Wert ( `True` oder) ausgewertet wird `False` . Dies umfasst auch Werte anderer Datentypen, z. b. numerischer Typen, die in konvertiert wurden `Boolean` .  
  
 Sie können Schleifen schachteln, `Do` indem Sie eine Schleife in eine andere einfügen. Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.  
  
> [!NOTE]
> Die `Do...Loop` Struktur bietet mehr Flexibilität als die [Zeit... End While-Anweisung](while-end-while-statement.md) , da Sie Ihnen ermöglicht, zu entscheiden, ob die Schleife beendet werden soll, wenn Sie `condition` nicht mehr `True` oder erst endet `True` . Außerdem können Sie Sie `condition` entweder am Anfang oder am Ende der Schleife testen.  
  
## <a name="exit-do"></a>Beenden  
 Die [Exit Do](exit-statement.md) -Anweisung kann eine alternative Möglichkeit zum Beenden eines bereitstellen `Do…Loop` . `Exit Do`überträgt die Steuerung sofort an die-Anweisung, die auf die- `Loop` Anweisung folgt.  
  
 `Exit Do`wird häufig verwendet, wenn eine bestimmte Bedingung ausgewertet wird, z. b. in einer- `If...Then...Else` Struktur. Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung. Eine Verwendung von besteht darin, auf `Exit Do` eine Bedingung zu testen, die zu einer *Endlosschleife*führen könnte, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen könnte. Mithilfe von können Sie die Schleife mit Escapezeichen versehen `Exit Do` .  
  
 Sie können eine beliebige Anzahl von- `Exit Do` Anweisungen an beliebiger Stelle in einem einschließen `Do…Loop` .  
  
 Überträgt bei Verwendung in geschachtelten `Do` Schleifen `Exit Do` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die- `index` Variable größer als 10 ist. Die- `Until` Klausel befindet sich am Ende der-Schleife.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `While` wird anstelle einer-Klausel eine `Until` -Klausel verwendet, und `condition` wird am Anfang der Schleife anstelle von am Ende getestet.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `condition` die-Schleife beendet, wenn die- `index` Variable größer als 100 ist. Die- `If` Anweisung in der-Schleife bewirkt jedoch, dass die- `Exit Do` Anweisung die-Schleife beendet, wenn die Index Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen. Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt einen zurück <xref:System.IO.StreamReader> , der die Zeichen liest. In der `Do...Loop` Bedingung bestimmt die- <xref:System.IO.StreamReader.Peek%2A> Methode von, `StreamReader` ob zusätzliche Zeichen vorhanden sind.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schleifenstrukturen](../../programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next-Anweisung](for-next-statement.md)
- [Boolean-Datentyp](../data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](exit-statement.md)
- [While...End While-Anweisung](while-end-while-statement.md)
