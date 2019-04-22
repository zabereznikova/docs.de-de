---
title: Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 1b85941c14721280a5025db442c4793930244ec8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837511"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
Wenn Sie ein oder mehrere Argumente an eine Prozedur übergeben, entspricht jedes Argument im aufrufenden Code eine zugrunde liegende Programmierelement ein Element. Sie können entweder den Wert dieses Elements zugrunde liegenden oder einen Verweis darauf übergeben. Dies bezeichnet man als den *Übergabemechanismus*.  
  
## <a name="passing-by-value"></a>Übergeben als Wert  
 Übergeben Sie ein Argument *nach Wert* durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition. Wenn Sie dieses Übergabemechanismus verwenden, kopiert Visual Basic den Wert des zugrunde liegenden Programmierelements in eine lokale Variable in der Prozedur. Der Code der Prozedur wird im aufrufenden Code keinen Zugriff auf das zugrunde liegende Element.  
  
## <a name="passing-by-reference"></a>Übergeben als Verweis  
 Übergeben Sie ein Argument *als Verweis* durch Angabe der [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition. Wenn Sie dieses Übergabemechanismus verwenden, bietet Visual Basic im aufrufenden Code einen direkten Verweis auf das zugrunde liegende Programmierelement an der Prozedur.  
  
## <a name="passing-mechanism-and-element-type"></a>Übergabemechanismus und Elementtyp  
 Die Wahl des Übergabemechanismus ist nicht identisch mit der Klassifizierung des zugrunde liegenden Elementtyps. Übergeben als Wert oder Verweis bezieht sich auf was Visual Basic zum Code Prozedur bereitstellt. Ein Werttyp oder Verweistyp verweist, wie ein Programmierelement im Arbeitsspeicher gespeichert ist.  
  
 Allerdings stehen die Übergabemechanismus und den Elementtyp in wechselseitiger Beziehung. Der Wert eines Verweistyps ist ein Zeiger auf die Daten an anderer Stelle im Arbeitsspeicher. Dies bedeutet, dass wenn Sie einen Verweistyp als Wert übergeben, der Code der Prozedur einen Zeiger auf die zugrunde liegenden Daten des Elements, obwohl das zugrunde liegende Element selbst nicht darauf zugreifen können. Wenn das Element eine Arrayvariable, z. B. der Code der Prozedur keinen Zugriff auf die Variable selbst, aber kann Sie auf die Array-Elemente zugreifen.  
  
## <a name="ability-to-modify"></a>Fähigkeit zum Ändern  
 Wenn Sie ein nicht veränderbares Element als Argument übergeben, die Prozedur kann nie geändert es im aufrufenden Code Übergabe `ByVal` oder `ByRef`.  
  
 Nach einem änderbaren Element werden in der folgende Tabelle die Interaktion zwischen den Typ des Elements und dem Übergabemechanismus zusammengefasst.  
  
|Elementtyp|Übergeben `ByVal`|Übergeben `ByRef`|  
|------------------|--------------------|--------------------|  
|Werttyp (enthält nur einen Wert)|Die Prozedur kann nicht auf die Variable oder eines ihrer Elemente ändern.|Die Prozedur kann die Variable und ihre Mitglieder ändern.|  
|Verweistyp (enthält einen Zeiger auf eine Klasse oder Struktur-Instanz)|Die Prozedur kann die Variable kann nicht geändert werden jedoch ändern Membern der Instanz auf der er verweist.|Die Variable und den Membern der Instanz auf der er verweist, kann die Prozedur ändern.|  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
