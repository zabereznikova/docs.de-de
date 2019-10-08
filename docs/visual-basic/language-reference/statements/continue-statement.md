---
title: Continue-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005101"
---
# <a name="continue-statement-visual-basic"></a>Continue-Anweisung (Visual Basic)
Überträgt die Steuerung sofort an die nächste Iterations Schleife.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können von innerhalb einer `Do`-, `For`-oder `While`-Schleife zur nächsten Iterationen dieser Schleife übertragen. Das Steuerelement wird sofort an den Schleifen Bedingungs Test übergeben, der der Übertragung an die `For`-oder `While`-Anweisung oder an die `Do`-oder `Loop`-Anweisung entspricht, die die `Until`-oder `While`-Klausel enthält.  
  
 Sie können `Continue` an jeder beliebigen Stelle in der Schleife verwenden, die Übertragungen zulässt. Die Regeln, die die Übertragung der Steuerung zulassen, sind identisch mit der [goto-Anweisung](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Wenn eine-Schleife z. b. vollständig in einem `Try`-Block, einem `Catch`-Block oder einem `Finally`-Block enthalten ist, können Sie `Continue` zum Übertragen der Schleife verwenden. Wenn andererseits die Struktur `Try`... `End Try` in der Schleife enthalten ist, können Sie `Continue` nicht verwenden, um die Steuerung aus dem `Finally`-Block zu übertragen, und Sie können Sie verwenden, um aus einem `Try`-oder `Catch`-Block nur zu übertragen, wenn Sie vollständig aus dem @no_ _T-6... `End Try`-Struktur.  
  
 Wenn Sie über geschachtelte Schleifen desselben Typs verfügen, z. b. eine `Do`-Schleife innerhalb einer anderen `Do`-Schleife, überspringt eine `Continue Do`-Anweisung die nächste Iterations Schleife der innersten `Do`-Schleife, in der Sie enthalten ist. @No__t-0 kann nicht verwendet werden, um zur nächsten Iterations Schleife einer enthaltenden Schleife desselben Typs zu springen.  
  
 Wenn Sie geschachtelte Schleifen verschiedener Typen haben, z. b. eine `Do`-Schleife innerhalb einer `For`-Schleife, können Sie mit `Continue Do` oder `Continue For` mit der nächsten Iterationen der beiden Schleifen springen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Continue While`-Anweisung verwendet, um zur nächsten Spalte eines Arrays zu springen, wenn ein Divisor gleich 0 (null) ist. Der `Continue While` befindet sich innerhalb einer `For`-Schleife. Es wird auf die `While col < lastcol`-Anweisung übertragen, bei der es sich um die nächste Iterationen der innersten `While`-Schleife handelt, die die `For`-Schleife enthält.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Siehe auch

- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
