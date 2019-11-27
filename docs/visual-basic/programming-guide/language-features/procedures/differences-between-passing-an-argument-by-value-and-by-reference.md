---
title: Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 84ec3bac2532b2cef72ddda347251bc987801c3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341232"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
Wenn Sie ein oder mehrere Argumente an eine Prozedur übergeben, entspricht jedes Argument einem zugrunde liegenden Programmier Element im aufrufenden Code. Sie können entweder den Wert dieses zugrunde liegenden Elements oder einen Verweis darauf übergeben. Dies wird als *Übergabe Mechanismus*bezeichnet.  
  
## <a name="passing-by-value"></a>Übergeben als Wert  
 Sie übergeben ein Argument als *Wert* , indem Sie das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) -Schlüsselwort für den entsprechenden Parameter in der Prozedur Definition angeben. Wenn Sie diesen Übergabe Mechanismus verwenden, kopiert Visual Basic den Wert des zugrunde liegenden Programmier Elements in eine lokale Variable in der Prozedur. Der Prozedur Code hat keinen Zugriff auf das zugrunde liegende Element im aufrufenden Code.  
  
## <a name="passing-by-reference"></a>Übergeben als Verweis  
 Sie übergeben ein Argument als *Verweis* , indem Sie das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort für den entsprechenden Parameter in der Prozedur Definition angeben. Wenn Sie diesen Übergabe Mechanismus verwenden, gibt Visual Basic der Prozedur einen direkten Verweis auf das zugrunde liegende Programmier Element im aufrufenden Code.  
  
## <a name="passing-mechanism-and-element-type"></a>Übergeben von Mechanismen und Elementtyp  
 Der übergebene Mechanismus ist nicht mit der Klassifizierung des zugrunde liegenden Elementtyps identisch. Wenn Sie als Wert oder als Verweis übergeben werden, bezieht sich dies auf die Visual Basic an den Prozedur Code liefert. Ein Werttyp oder Verweistyp bezieht sich darauf, wie ein Programmier Element im Arbeitsspeicher gespeichert wird.  
  
 Der Übergabe Mechanismus und der Elementtyp sind jedoch miteinander verknüpft. Der Wert eines Verweis Typs ist ein Zeiger auf die Daten an anderer Stelle im Arbeitsspeicher. Dies bedeutet Folgendes: Wenn Sie einen Verweistyp als Wert übergeben, verfügt der Prozedur Code über einen Zeiger auf die Daten des zugrunde liegenden Elements, auch wenn er nicht auf das zugrunde liegende Element selbst zugreifen kann. Wenn das Element z. b. eine Array Variable ist, hat der Prozedur Code keinen Zugriff auf die Variable selbst, kann aber auf die Arraymember zugreifen.  
  
## <a name="ability-to-modify"></a>Änderbarkeit  
 Wenn Sie ein nicht änderbares Element als Argument übergeben, kann die Prozedur es niemals im aufrufenden Code ändern, unabhängig davon, ob es `ByVal` oder `ByRef`übergeben wird.  
  
 In der folgenden Tabelle wird für ein änderbares Element die Interaktion zwischen dem Elementtyp und dem Übergabe Mechanismus zusammengefasst.  
  
|Elementtyp|Bestandene `ByVal`|Bestandene `ByRef`|  
|------------------|--------------------|--------------------|  
|Werttyp (enthält nur einen Wert)|Die-Prozedur kann die Variable oder keines ihrer Member nicht ändern.|Die-Prozedur kann die Variable und ihre Member ändern.|  
|Verweistyp (enthält einen Zeiger auf eine Klassen-oder Struktur Instanz)|Die Prozedur kann die Variable nicht ändern, kann jedoch die Member der Instanz ändern, auf die Sie verweist.|Die-Prozedur kann die Variable und die Member der Instanz ändern, auf die Sie verweist.|  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
