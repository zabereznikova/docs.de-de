---
title: Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 989795ee2cdd3a78b71bad4d95cf9b384c2719bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341392"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)
Wenn Sie eine Prozedur aufzurufen, übergeben Sie in der Regel ein oder mehrere Argumente an Sie. Jedes Argument entspricht einem zugrunde liegenden Programmier Element. Sowohl die zugrunde liegenden Elemente als auch die Argumente selbst können entweder änderbar oder nicht änderbar sein.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Änderbare und nicht änderbare Elemente  
 Ein Programmier Element kann entweder ein *änderbares Element*sein, dessen Wert geändert werden kann, oder ein *nicht änderbares Element*, das nach seiner Erstellung einen festgelegten Wert aufweist.  
  
 In der folgenden Tabelle sind änderbare und nicht änderbare Programmier Elemente aufgelistet.  
  
|Änderbare Elemente|Nicht änderbare Elemente|  
|-------------------------|----------------------------|  
|Lokale Variablen (deklariert innerhalb von Prozeduren), einschließlich Objektvariablen, außer schreibgeschützt|Schreibgeschützte Variablen, Felder und Eigenschaften|  
|Felder (Element Variablen von Modulen, Klassen und Strukturen), mit Ausnahme von Schreib geschütztem|Konstanten und Literale|  
|Eigenschaften, außer schreibgeschützt|Enumerationsmember|  
|Array Elemente|Ausdrücke (auch wenn ihre Elemente geändert werden können)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Änderbare und nicht änderbare Argumente  
 Ein *änderbares Argument* ist ein Element mit einem änderbaren zugrunde liegenden Element. Der Aufruf Code kann jederzeit einen neuen Wert speichern. Wenn Sie das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)-Argument übergeben, kann der Code in der Prozedur auch das zugrunde liegende Element im aufrufenden Code ändern.  
  
 Ein *nicht änderbares Argument* weist entweder ein nicht änderbares zugrunde liegendes Element auf oder wird [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)übermittelt. Die Prozedur kann das zugrunde liegende Element im aufrufenden Code nicht ändern, selbst wenn es sich um ein änderbares Element handelt. Wenn es sich um ein nicht änderbares Element handelt, kann der aufrufende Code es nicht ändern.  
  
 Die aufgerufene Prozedur kann die lokale Kopie eines nicht änderbaren Arguments ändern, aber diese Änderung hat keine Auswirkung auf das zugrunde liegende Element im aufrufenden Code.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
