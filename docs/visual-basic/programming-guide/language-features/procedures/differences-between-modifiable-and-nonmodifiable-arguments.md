---
title: "Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab108d064f5c6740f80328a9b6db4785334550ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)
Wenn Sie eine Prozedur aufrufen, übergeben Sie ein oder mehrere Argumente in der Regel darauf. Jedes Argument entspricht einem zugrunde liegenden Programmierelement. Die zugrunde liegenden Elemente und die Argumente selbst können geändert werden kann oder nicht veränderbaren sein.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Veränderbaren und nicht veränderbaren Elemente  
 Ein Programmierelement kann es sich um eine *änderbare Element*, wofür den Wert geändert, oder ein *nicht veränderbaren Element*, die einen festen Wert aufweist, nachdem es erstellt wurde.  
  
 Die folgende Tabelle enthält die veränderbaren und nicht veränderbaren Programmierelemente.  
  
|Änderbare Elemente|Nicht veränderbaren Elemente|  
|-------------------------|----------------------------|  
|Lokale Variablen (deklariert in Prozeduren), einschließlich Objektvariablen, mit Ausnahme von nur-Lese|Schreibgeschützte Variablen, Felder und Eigenschaften|  
|Felder (Membervariablen von Modulen, Klassen und Strukturen), mit Ausnahme von nur-Lese|Konstanten und Literale|  
|Eigenschaften, mit Ausnahme von nur-Lese|Enumerationsmember|  
|Array-Elemente|Ausdrücke (selbst wenn ihre Elemente geändert werden)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Veränderbaren und nicht veränderbaren Argumenten  
 Ein *änderbaren Argument* ist eine mit einem änderbaren zugrunde liegende Element. Der aufrufende Code kann einen neuen Wert zu einem beliebigen Zeitpunkt zu speichern, und wenn das Argument zu übergeben [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), den Code in der Prozedur kann auch das zugrunde liegende Element im aufrufenden Code ändern.  
  
 Ein *nicht veränderbaren Argument* verfügt über einen nicht veränderbaren zugrunde liegende Element, oder übergeben [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Die Prozedur kann nicht das zugrunde liegende Element im aufrufenden Code ändern, selbst wenn es sich um einen änderbaren Element handelt. Wenn es sich um einen nicht veränderbaren Element handelt, kann nicht der aufrufende Code selbst es ändern.  
  
 Die aufgerufene Prozedur kann die lokale Kopie eines nicht veränderbaren Arguments ändern, aber diese Änderung nicht auf das zugrunde liegende Element im aufrufenden Code auswirkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
