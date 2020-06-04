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
ms.openlocfilehash: 5b060f5fa0042dfb8ffa6876f5e172d3bcda67a3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396219"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
Mit dem- `Key` Schlüsselwort können Sie das Verhalten von Eigenschaften anonymer Typen angeben. Nur Eigenschaften, die Sie als Schlüsseleigenschaften festlegen, nehmen an Gleichheits Tests zwischen anonymen Typinstanzen oder der Berechnung von Hash Code Werten Teil. Die Werte der Schlüsseleigenschaften können nicht geändert werden.  
  
 Sie legen eine Eigenschaft eines anonymen Typs als Schlüsseleigenschaft fest, indem Sie das-Schlüsselwort `Key` vor der Deklaration in der Initialisierungs Liste platzieren. Im folgenden Beispiel `Airline` `FlightNo` sind und Schlüsseleigenschaften, aber `Gate` nicht.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 Wenn ein neuer anonymer Typ erstellt wird, erbt er direkt von <xref:System.Object> . Der Compiler überschreibt drei geerbte Member: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> und <xref:System.Object.ToString%2A> . Der für und erstellte Überschreibungs Code <xref:System.Object.Equals%2A> <xref:System.Object.GetHashCode%2A> basiert auf Schlüsseleigenschaften. Wenn keine Schlüsseleigenschaften im Typ vorhanden sind <xref:System.Object.GetHashCode%2A> und <xref:System.Object.Equals%2A> nicht überschrieben werden.  
  
## <a name="equality"></a>Gleichheit  
 Zwei anonyme Typinstanzen sind gleich, wenn Sie Instanzen desselben Typs sind und die Werte ihrer Schlüsseleigenschaften gleich sind. In den folgenden Beispielen `flight2` ist gleich `flight1` dem vorherigen Beispiel, da Sie Instanzen desselben anonymen Typs sind und über übereinstimmende Werte für Ihre Schlüsseleigenschaften verfügen. Ist jedoch `flight3` nicht gleich, `flight1` da Sie einen anderen Wert für eine Schlüsseleigenschaft hat: `FlightNo` . Die-Instanz hat `flight4` nicht denselben Typ wie, `flight1` weil Sie unterschiedliche Eigenschaften als Schlüsseleigenschaften festlegen.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Wenn zwei Instanzen nur mit nicht Schlüsseleigenschaften deklariert werden, die in Name, Typ, Reihenfolge und Wert identisch sind, sind die beiden Instanzen nicht gleich. Eine Instanz ohne Schlüsseleigenschaften ist nur mit sich selbst identisch.  
  
 Weitere Informationen zu den Bedingungen, unter denen zwei Instanzen eines anonymen Typs Instanzen desselben anonymen Typs sind, finden Sie unter [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Hash Code Berechnung  
 Ebenso <xref:System.Object.Equals%2A> basiert die Hash Funktion, die in <xref:System.Object.GetHashCode%2A> für einen anonymen Typ definiert ist, auf den Schlüsseleigenschaften des-Typs. Die folgenden Beispiele zeigen die Interaktion zwischen Schlüsseleigenschaften und Hashcodewerten.  
  
 Instanzen eines anonymen Typs, die dieselben Werte für alle Schlüsseleigenschaften aufweisen, haben denselben Hash Codewert, auch wenn nicht Schlüsseleigenschaften nicht übereinstimmende Werte aufweisen. Die folgende Anweisung gibt `True` zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Instanzen eines anonymen Typs, die unterschiedliche Werte für eine oder mehrere Schlüsseleigenschaften aufweisen, haben unterschiedliche Hashcode-Werte. Die folgende Anweisung gibt `False` zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Instanzen anonymer Typen, die andere Eigenschaften als Schlüsseleigenschaften festlegen, sind keine Instanzen desselben Typs. Sie haben verschiedene Hashcodewerte, auch wenn die Namen und Werte aller Eigenschaften identisch sind. Die folgende Anweisung gibt `False` zurück.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Schreibgeschützte Werte  
 Die Werte der Schlüsseleigenschaften können nicht geändert werden. Beispielsweise sind in `flight1` in den vorherigen Beispielen die `Airline` Felder und schreibgeschützt `FlightNo` , `Gate` können aber geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Definition von anonymen Typen](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
