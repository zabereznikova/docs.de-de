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
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352786"
---
# <a name="throw-statement-visual-basic"></a>Throw-Anweisung (Visual Basic)

Löst eine Ausnahme in einer Prozedur aus.

## <a name="syntax"></a>Syntax

```vb
Throw [ expression ]
```

## <a name="part"></a>-Komponente

`expression`\
Stellt Informationen über die Ausnahme bereit, die ausgelöst werden soll. Ist optional, wenn Sie sich in einer `Catch`-Anweisung befindet, andernfalls erforderlich.

## <a name="remarks"></a>Hinweise

Die `Throw`-Anweisung löst eine Ausnahme aus, die Sie mit strukturiertem Ausnahme Behandlungs Code (`Try`...`Catch`...`Finally`) oder unstrukturiertem Ausnahme Behandlungs Code (`On Error GoTo`) behandeln können. Sie können die `Throw`-Anweisung verwenden, um Fehler in Ihrem Code abzufangen, da Visual Basic die aufrufsstapel nach oben verschiebt, bis der entsprechende Ausnahme Behandlungs Code gefunden wird.

Eine `Throw`-Anweisung ohne Ausdruck kann nur in einer `Catch`-Anweisung verwendet werden. in diesem Fall löst die-Anweisung die Ausnahme, die derzeit von der `Catch`-Anweisung behandelt wird, erneut aus.

Die `Throw`-Anweisung setzt die aufrufsstapel für die `expression` Ausnahme zurück. Wenn `expression` nicht angegeben wird, bleibt die-aufrufsstapel unverändert. Sie können über die <xref:System.Exception.StackTrace%2A>-Eigenschaft auf die aufrufsstapel für die Ausnahme zugreifen.

## <a name="example"></a>Beispiel

Im folgenden Code wird die `Throw`-Anweisung verwendet, um eine Ausnahme auszulösen:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>Siehe auch

- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
