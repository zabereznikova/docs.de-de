---
title: Throw-Anweisung (Visual Basic)
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
ms.openlocfilehash: a6d10982cf199e9285334e0d72e6622275d51b4d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626197"
---
# <a name="throw-statement-visual-basic"></a>Throw-Anweisung (Visual Basic)
Löst eine Ausnahme in einer Prozedur aus.

## <a name="syntax"></a>Syntax

```vb
Throw [ expression ]
```

## <a name="part"></a>Segment
 `expression`Stellt Informationen über die Ausnahme bereit, die ausgelöst werden soll. Optional, wenn in einer `Catch` -Anweisung gespeichert; andernfalls erforderlich.
  
## <a name="remarks"></a>Hinweise
 Die `Throw` -Anweisung löst eine Ausnahme aus, die Sie mit strukturiertem Ausnahme Behandlungs`Try`Code behandeln können (... `Catch`... ) oder unstrukturierter Ausnahme Behandlungs Code (`On Error GoTo`). `Finally` Sie können die `Throw` -Anweisung verwenden, um Fehler in Ihrem Code abzufangen, da Visual Basic die aufrufsstapel nach oben verschiebt, bis der entsprechende Ausnahme Behandlungs Code gefunden wird.
 
 Eine `Throw` -Anweisung ohne-Ausdruck kann nur in einer `Catch` -Anweisung verwendet werden. in diesem Fall löst die-Anweisung die Ausnahme erneut aus, `Catch` die zurzeit von der-Anweisung verarbeitet wird.

 Die `Throw` -Anweisung setzt die-aufrufsstapel für die `expression` Ausnahme zurück. Wenn `expression` nicht angegeben wird, bleibt die-aufrufsstapel unverändert. Sie können über die <xref:System.Exception.StackTrace%2A> -Eigenschaft auf die-aufrufsstapel für die Ausnahme zugreifen.

## <a name="example"></a>Beispiel
 Im folgenden Code wird die `Throw` -Anweisung verwendet, um eine Ausnahme auszulösen:
 
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

  
## <a name="see-also"></a>Siehe auch

- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
