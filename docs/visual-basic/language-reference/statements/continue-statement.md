---
title: Continue-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: cf73ea1b3d402609c9966980dcab9ddd9bc096c2
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874961"
---
# <a name="continue-statement-visual-basic"></a>Continue-Anweisung (Visual Basic)

Überträgt die Steuerung sofort an die nächste Iterations Schleife.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Bemerkungen  

 Sie können von innerhalb einer- `Do` ,- `For` oder- `While` Schleife zur nächsten Iterationen dieser Schleife übertragen. Das Steuerelement wird sofort an den Schleifen Bedingungs Test übergeben, der der Übertragung an die- `For` oder- `While` Anweisung entspricht, oder an die-oder-Anweisung, die die-oder- `Do` `Loop` `Until` Klausel enthält `While` .  
  
 Sie können `Continue` an jeder beliebigen Stelle in der Schleife verwenden, die Übertragungen zulässt. Die Regeln, die die Übertragung der Steuerung zulassen, sind identisch mit der [goto-Anweisung](goto-statement.md).  
  
 Wenn eine-Schleife z. b. vollständig in einem- `Try` Block, einem-Block oder einem-Block enthalten ist `Catch` `Finally` , können Sie verwenden, `Continue` um aus der Schleife zu übertragen. Wenn andererseits die `Try` ... `End Try` -Struktur in der-Schleife enthalten ist, können Sie nicht verwenden, `Continue` um die Steuerung aus dem-Block zu übertragen `Finally` , und Sie können Sie nur verwenden, um aus einem-oder-Block zu übertragen, `Try` `Catch` Wenn Sie vollständig aus der `Try` ...-Struktur übertragen `End Try` .  
  
 Wenn Sie über geschachtelte Schleifen desselben Typs verfügen, z. b `Do` . eine Schleife innerhalb einer anderen `Do` Schleife, springt eine- `Continue Do` Anweisung zur nächsten Iterationen der innersten Schleife, in der `Do` Sie enthalten ist. Sie können nicht verwenden `Continue` , um zur nächsten Iterations Schleife einer enthaltenden Schleife desselben Typs zu springen.  
  
 Wenn Sie geschachtelte Schleifen verschiedener Typen, z. b. eine- `Do` Schleife innerhalb einer-Schleife `For` , verwenden, können Sie mit oder mit der nächsten Iterations Schleife springen `Continue Do` `Continue For` .  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird die- `Continue While` Anweisung verwendet, um zur nächsten Spalte eines Arrays zu springen, wenn ein Divisor gleich 0 (null) ist. Der `Continue While` befindet sich innerhalb einer- `For` Schleife. Es wird zur-Anweisung übertragen, bei der es sich um `While col < lastcol` die nächste Iterations Schleife der innersten Schleife handelt, die `While` die- `For` Schleife enthält.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Do...Loop-Anweisung](do-loop-statement.md)
- [For...Next-Anweisung](for-next-statement.md)
- [While...End While-Anweisung](while-end-while-statement.md)
- [Try... Catch... Abschließend-Anweisung](try-catch-finally-statement.md)
