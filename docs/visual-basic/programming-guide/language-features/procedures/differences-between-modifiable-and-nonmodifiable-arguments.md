---
title: Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 06f3009d984f7a303a0ee6e8d529a3ff60900fbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498682"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)
Wenn Sie eine Prozedur aufrufen, übergeben Sie ein oder mehrere Argumente in der Regel darauf. Jedes Argument entspricht einem zugrunde liegenden Programmierelement. Die zugrunde liegenden Elemente und die Argumente selbst können geändert werden kann oder als nicht änderbar sein.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Veränderbaren und nicht veränderbaren Elemente  
 Ein Programmierelement kann es sich um entweder eine *änderbare Element*, die aufweisen kann, dessen Wert sich ändert, oder ein *nicht veränderbares Element*, die über einen festen Wert verfügt, nachdem es erstellt wurde.  
  
 Die folgende Tabelle enthält die veränderbaren und nicht veränderbaren Programmierelemente.  
  
|Änderbare Elemente|Als nicht änderbar Elemente|  
|-------------------------|----------------------------|  
|Lokale Variablen (deklariert in Prozeduren), einschließlich der Objektvariablen, ausgenommen schreibgeschützte|Schreibgeschützte Variablen, Felder und Eigenschaften|  
|Felder (Membervariablen der Module, Klassen und Strukturen), mit Ausnahme von nur-Lese|Konstanten und Literale|  
|Eigenschaften, ausgenommen schreibgeschützte|Enumerationsmember|  
|Array-Elemente|Ausdrücke (auch wenn ihre Elemente geändert werden)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Veränderbaren und nicht veränderbaren Argumenten  
 Ein *änderbaren Argument* ist ein URI mit einer änderbaren zugrunde liegende Element. Der aufrufende Code kann einen neuen Wert zu jedem Zeitpunkt speichern, und wenn Sie das Argument zu übergeben [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), den Code in der Prozedur kann auch das zugrunde liegende Element im aufrufenden Code ändern.  
  
 Ein *nicht veränderbaren Argument* entweder ein nicht veränderbares zugrunde liegende Element, oder übergeben [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Die Prozedur ändern nicht das zugrunde liegende Element im aufrufenden Code, selbst wenn es sich um eine änderbare Element handelt. Wenn es sich um ein nicht veränderbares Element handelt, kann nicht der aufrufende Code selbst ändern.  
  
 Die aufgerufene Prozedur kann die lokale Kopie der veränderbaren Arguments ändern, aber diese Änderung keine Auswirkungen auf das zugrunde liegende Element im aufrufenden Code hat.  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
