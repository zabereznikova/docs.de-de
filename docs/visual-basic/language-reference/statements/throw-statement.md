---
title: Throw-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 95572b1739490e90f53da6b6ec283bfb532c46d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404134"
---
# <a name="throw-statement-visual-basic"></a>Throw-Anweisung (Visual Basic)

Löst eine Ausnahme in einer Prozedur aus.

## <a name="syntax"></a>Syntax

```vb
Throw [ expression ]
```

## <a name="part"></a>Teil

`expression`\
Stellt Informationen über die Ausnahme bereit, die ausgelöst werden soll. Optional, wenn in einer-Anweisung gespeichert; `Catch` andernfalls erforderlich.

## <a name="remarks"></a>Bemerkungen

Die- `Throw` Anweisung löst eine Ausnahme aus, die Sie mit strukturiertem Ausnahme Behandlungs Code behandeln können ( `Try` .. `Catch` . ...`Finally`) oder unstrukturierter Ausnahme Behandlungs Code ( `On Error GoTo` ). Sie können die- `Throw` Anweisung verwenden, um Fehler in Ihrem Code abzufangen, da Visual Basic die aufrufsstapel nach oben verschiebt, bis der entsprechende Ausnahme Behandlungs Code gefunden wird.

Eine- `Throw` Anweisung ohne-Ausdruck kann nur in einer- `Catch` Anweisung verwendet werden. in diesem Fall löst die-Anweisung die Ausnahme erneut aus, die zurzeit von der-Anweisung verarbeitet wird `Catch` .

Die- `Throw` Anweisung setzt die-aufrufsstapel für die `expression` Ausnahme zurück. Wenn `expression` nicht angegeben wird, bleibt die-aufrufsstapel unverändert. Sie können über die-Eigenschaft auf die-aufrufsstapel für die Ausnahme zugreifen <xref:System.Exception.StackTrace%2A> .

## <a name="example"></a>Beispiel

Im folgenden Code wird die- `Throw` Anweisung verwendet, um eine Ausnahme auszulösen:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>Weitere Informationen

- [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md)
- [On Error-Anweisung](on-error-statement.md)
