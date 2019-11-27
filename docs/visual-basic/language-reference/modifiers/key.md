---
title: Key
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92c8809779d6cab524f67ee47f355b72ab152403
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351515"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
Mit dem `Key`-Schlüsselwort können Sie das Verhalten von Eigenschaften anonymer Typen angeben. Nur Eigenschaften, die Sie als Schlüsseleigenschaften festlegen, nehmen an Gleichheits Tests zwischen anonymen Typinstanzen oder der Berechnung von Hash Code Werten Teil. Die Werte der Schlüsseleigenschaften können nicht geändert werden.  
  
 Sie legen eine Eigenschaft eines anonymen Typs als Schlüsseleigenschaft fest, indem Sie das Schlüsselwort `Key` vor der Deklaration in der Initialisierungs Liste platzieren. Im folgenden Beispiel sind `Airline` und `FlightNo` Schlüsseleigenschaften, aber `Gate` nicht.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 Wenn ein neuer anonymer Typ erstellt wird, erbt er direkt von <xref:System.Object>. Der Compiler überschreibt drei geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>und <xref:System.Object.ToString%2A>. Der für <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> erstellte Überschreibungs Code basiert auf Schlüsseleigenschaften. Wenn keine Schlüsseleigenschaften im Typ vorhanden sind, werden <xref:System.Object.GetHashCode%2A> und <xref:System.Object.Equals%2A> nicht überschrieben.  
  
## <a name="equality"></a>Gleichheit  
 Zwei anonyme Typinstanzen sind gleich, wenn Sie Instanzen desselben Typs sind und die Werte ihrer Schlüsseleigenschaften gleich sind. In den folgenden Beispielen ist `flight2` gleich `flight1` aus dem vorherigen Beispiel, da Sie Instanzen desselben anonymen Typs sind und über übereinstimmende Werte für Ihre Schlüsseleigenschaften verfügen. `flight3` ist jedoch nicht gleich `flight1`, da Sie einen anderen Wert für eine Schlüsseleigenschaft hat, `FlightNo`. Der Instanz`flight4` ist nicht der gleiche Typ wie `flight1`, da Sie andere Eigenschaften als Schlüsseleigenschaften festlegen.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Wenn zwei Instanzen nur mit nicht Schlüsseleigenschaften deklariert werden, die in Name, Typ, Reihenfolge und Wert identisch sind, sind die beiden Instanzen nicht gleich. Eine Instanz ohne Schlüsseleigenschaften ist nur mit sich selbst identisch.  
  
 Weitere Informationen zu den Bedingungen, unter denen zwei Instanzen eines anonymen Typs Instanzen desselben anonymen Typs sind, finden Sie unter [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Hash Code Berechnung  
 Wie <xref:System.Object.Equals%2A>basiert die Hash Funktion, die in <xref:System.Object.GetHashCode%2A> für einen anonymen Typ definiert ist, auf den Schlüsseleigenschaften des Typs. Die folgenden Beispiele zeigen die Interaktion zwischen Schlüsseleigenschaften und Hashcodewerten.  
  
 Instanzen eines anonymen Typs, die dieselben Werte für alle Schlüsseleigenschaften aufweisen, haben denselben Hash Codewert, auch wenn nicht Schlüsseleigenschaften nicht übereinstimmende Werte aufweisen. Die folgende Anweisung gibt `True`zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Instanzen eines anonymen Typs, die unterschiedliche Werte für eine oder mehrere Schlüsseleigenschaften aufweisen, haben unterschiedliche Hashcode-Werte. Die folgende Anweisung gibt `False`zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Instanzen anonymer Typen, die andere Eigenschaften als Schlüsseleigenschaften festlegen, sind keine Instanzen desselben Typs. Sie haben verschiedene Hashcodewerte, auch wenn die Namen und Werte aller Eigenschaften identisch sind. Die folgende Anweisung gibt `False`zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Schreibgeschützte Werte  
 Die Werte der Schlüsseleigenschaften können nicht geändert werden. Beispielsweise sind in `flight1` in den vorherigen Beispielen die Felder `Airline` und `FlightNo` schreibgeschützt, `Gate` können jedoch geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [Definition von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
