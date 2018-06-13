---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92d54e3135142bc02a17f3ce5ac078a356c139be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599843"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
Die `Key` Schlüsselwort ermöglicht Ihnen das Verhalten für Eigenschaften von anonymen Typen festlegen. Nur Eigenschaften bestimmen Sie, wie die Tests der auf Gleichheit zwischen Instanzen eines anonymen Typs oder eine Berechnung des Hashcodewerte Schlüsseleigenschaften teilnehmen. Die Werte von Schlüsseleigenschaften können nicht geändert werden.  
  
 Eine Eigenschaft eines anonymen Typs wird als Schlüsseleigenschaft gekennzeichnet, indem Sie das Schlüsselwort `Key` vor ihrer Deklaration in der Initialisierungsliste. Im folgenden Beispiel `Airline` und `FlightNo` Schlüsseleigenschaften, sind aber `Gate` nicht.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 Wenn ein neuer anonymer Typ erstellt wird, erbt direkt von <xref:System.Object>. Der Compiler überschreibt drei geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>. Die Außerkraftsetzung-Code, der für erzeugt wird <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> Schlüsseleigenschaften basiert. Wenn keine wichtigsten Eigenschaften vorhanden, geben Sie im sind <xref:System.Object.GetHashCode%2A> und <xref:System.Object.Equals%2A> nicht überschrieben werden.  
  
## <a name="equality"></a>Gleichheit  
 Wenn sie Instanzen desselben Typs sind und die Werte ihrer Schlüssel Eigenschaften gleich sind, werden die zwei Instanzen eines anonymen Typs gleich sind. In den folgenden Beispielen `flight2` gleich `flight1` aus dem vorherigen Beispiel, da sie Instanzen des gleichen anonymen sind Typ und sie haben übereinstimmende Werte für ihre Schlüsseleigenschaften. Allerdings `flight3` stimmt nicht mit `flight1` da sie einen anderen Wert für eine Schlüsseleigenschaft verfügt `FlightNo`. Instanz `flight4` ist nicht vom selben Typ wie `flight1` , da sie andere Eigenschaften als Schlüsseleigenschaften festlegen.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 Wenn zwei Instanzen mit nur nicht schlüsselbezogene Eigenschaften Name, Typ, Reihenfolge und Wert identisch deklariert werden sind die beiden Instanzen ungleich. Eine Instanz ohne Schlüsseleigenschaften ist ungleich sich selbst.  
  
 Weitere Informationen zu den Bedingungen, unter dem sind zwei Instanzen eines anonymen Typs Instanzen desselben anonymen Typs, finden Sie unter [anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Berechnung des Hashs Code  
 Wie <xref:System.Object.Equals%2A>, Hash-Funktion, die in definierten <xref:System.Object.GetHashCode%2A> für ein anonymer Typ auf den Schlüsseleigenschaften des Typs basiert. Die folgenden Beispiele zeigen die Interaktion zwischen Schlüsseleigenschaften und Hash Codewerte.  
  
 Instanzen eines anonymen Typs, die die gleichen Werte für alle Schlüsseleigenschaften verfügen haben den gleichen Code Hashwert an, auch wenn nicht schlüsselbezogene Eigenschaften nicht übereinstimmende Werte verfügen. Die folgende Anweisung gibt `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 Instanzen eines anonymen Typs, die unterschiedliche Werte für eine oder mehrere wichtige Eigenschaften verfügen über anderen Hash Codewerte verfügen. Die folgende Anweisung gibt `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 Instanzen von anonymen Typen, die andere Eigenschaften festlegen, wie Schlüsseleigenschaften keine Instanzen desselben Typs sind. Sie verfügen über anderen Hashcodewerte, selbst wenn die Namen und Werte aller Eigenschaften identisch sind. Die folgende Anweisung gibt `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a>Schreibgeschützte Werte  
 Die Werte von Schlüsseleigenschaften können nicht geändert werden. Beispielsweise ist in `flight1` in den vorherigen Beispielen die `Airline` und `FlightNo` Felder sind schreibgeschützt, aber `Gate` kann geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Definition von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
