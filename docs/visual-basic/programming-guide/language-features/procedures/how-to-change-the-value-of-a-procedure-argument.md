---
title: 'Vorgehensweise: Ändern des Werts eines Prozedurarguments'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 46cf9062d01e248b6e90882a923a48210780f7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388503"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)
Wenn Sie eine Prozedur aufzurufen, entspricht jedes von Ihnen bereitgestellte Argument einem der in der Prozedur definierten Parameter. In einigen Fällen kann der Prozedur Code den Wert ändern, der einem Argument im aufrufenden Code zugrunde liegt. In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.  
  
 Wenn Sie die Prozedur aufzurufen, erstellt Visual Basic eine lokale Kopie jedes Arguments, das [ByVal](../../../language-reference/modifiers/byval.md)übermittelt wird. Für jedes Argument, das [ByRef](../../../language-reference/modifiers/byref.md)übergibt, gibt Visual Basic dem Prozedur Code einen direkten Verweis auf das Programmier Element, das dem Argument im aufrufenden Code zugrunde liegt.  
  
 Wenn das zugrunde liegende Element im aufrufenden Code ein änderbares Element ist und das Argument weitergegeben wird `ByRef` , kann der Prozedur Code den direkten Verweis verwenden, um den Wert des Elements im aufrufenden Code zu ändern.  
  
## <a name="changing-the-underlying-value"></a>Ändern des zugrunde liegenden Werts  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>So ändern Sie den zugrunde liegenden Wert eines Procedure-Arguments im aufrufenden Code  
  
1. Geben Sie in der Prozedur Deklaration [ByRef](../../../language-reference/modifiers/byref.md) für den Parameter an, der dem Argument entspricht.  
  
2. Übergeben Sie im aufrufenden Code ein änderbares Programmier Element als Argument.  
  
3. Schließen Sie das Argument im aufrufenden Code nicht in Klammern in der Argumentliste ein.  
  
4. Verwenden Sie im Prozedur Code den Parameternamen, um dem zugrunde liegenden Element im aufrufenden Code einen Wert zuzuweisen.  
  
 Eine Demonstration finden Sie im Beispiel weiter unten.  
  
## <a name="changing-local-copies"></a>Ändern von lokalen Kopien  
 Wenn das zugrunde liegende Element im aufrufenden Code ein nicht änderbares Element ist oder wenn das Argument übermittelt wird `ByVal` , kann die Prozedur den Wert im aufrufenden Code nicht ändern. Die Prozedur kann jedoch Ihre lokale Kopie eines solchen Arguments ändern.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>So ändern Sie die Kopie eines Prozedur Arguments im Prozedur Code  
  
1. Geben Sie in der Prozedur Deklaration [ByVal](../../../language-reference/modifiers/byval.md) für den Parameter an, der dem-Argument entspricht.  
  
     Oder  
  
     Schließen Sie das Argument im aufrufenden Code in Klammern in die Argumentliste ein. Dies erzwingt Visual Basic, das Argument als Wert zu übergeben, auch wenn der entsprechende Parameter angibt `ByRef` .  
  
2. Verwenden Sie im Prozedur Code den Parameternamen, um der lokalen Kopie des Arguments einen Wert zuzuweisen. Der zugrunde liegende Wert im aufrufenden Code wird nicht geändert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Prozeduren, die eine Array Variable akzeptieren und deren Elemente verarbeiten. Die `increase` Prozedur fügt einem Element einfach ein Element hinzu. Die `replace` Prozedur weist dem-Parameter ein neues Array zu `a()` und fügt dann einem-Element einen hinzu.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Der erste-Befehl `MsgBox` zeigt "After Increase (n): 11, 21, 31, 41" an. Da es sich bei dem Array `n` um einen Verweistyp handelt, `replace` kann seine Member ändern, auch wenn der Übergabe Mechanismus ist `ByVal` .  
  
 Der zweite- `MsgBox` Befehl zeigt "After replace (n): 101, 201, 301" an. Da erfolgreich `n` ist `ByRef` , `replace` kann die Variable `n` im aufrufenden Code ändern und ihr ein neues Array zuweisen. Da `n` ein Verweistyp ist, `replace` kann auch seine Member ändern.  
  
 Sie können verhindern, dass die Prozedur die Variable selbst im aufrufenden Code ändert. Weitere Informationen finden [Sie unter Gewusst wie: Schützen eines Prozedur Arguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Wenn Sie eine Variable als Verweis übergeben, müssen Sie dieses Verfahren mit dem- `ByRef` Schlüsselwort angeben.  
  
 Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben. Es ist jedoch eine gute Programmier Übung, das [ByVal](../../../language-reference/modifiers/byval.md) -oder [ByRef](../../../language-reference/modifiers/byref.md) -Schlüsselwort mit jedem deklarierten Parameter einzuschließen. Dadurch wird Ihr Code leichter lesbar.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es besteht immer ein potenzielles Risiko, dass eine Prozedur den Wert ändern kann, der einem Argument im aufrufenden Code zugrunde liegt. Stellen Sie sicher, dass dieser Wert geändert wird, und dass Sie darauf vorbereitet sind, ihn vor der Verwendung auf Gültigkeit zu überprüfen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Wert- und Verweistypen](../data-types/value-types-and-reference-types.md)
