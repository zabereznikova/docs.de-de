---
title: 'Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 89a39e8e9cd66b1d774da70be47c7c6824cccef2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350037"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen (Visual Basic)

Anonyme Typen stellen keinen Mechanismus zum direkten Angeben der Datentypen von Eigenschaften bereit. Die Typen aller Eigenschaften werden abgeleitet. Im folgenden Beispiel werden die Typen von `Name` und `Price` direkt aus den Werten abgeleitet, mit denen sie initialisiert werden.

[!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]

Anonyme Typen können Eigenschaftennamen und -typen auch aus anderen Quellen ableiten. In den folgenden Abschnitten werden sowohl eine Liste der Umstände, unter denen Ableitung möglich ist, als auch Beispiele bereitgestellt, in denen keine Ableitung möglich ist.

## <a name="successful-inference"></a>Erfolgreiche Ableitung

#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>Anonyme Typen können Eigenschaftennamen und -typen aus folgenden Quellen ableiten:

- Aus Variablennamen. Der anonyme Typ `anonProduct` hat die beiden Eigenschaften `productName` und `productPrice`. Ihre Datentypen sind gleich denen der ursprünglichen Variablen, also `String` bzw. `Double`.

  [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]

- Aus Eigenschaften- oder Feldnamen anderer Objekte. Betrachten Sie z. B. ein `car` -Objekt eines `CarClass` -Typs, der die `Name` -Eigenschaft und die `ID` -Eigenschaft enthält. Um die neue Instanz `car1`des anonymen Typs mit der `Name` -Eigenschaft und der `ID` -Eigenschaft zu erstellen, die mit den Werten aus dem `car` -Objekt initialisiert werden, können Sie folgenden Code schreiben:

  [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]

  Die vorherige Deklaration ist mit der längeren Codezeile gleichwertig, in der der anonyme Typ `car2`definiert ist.

  [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]

- Aus XML-Membernamen.

  [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]

  Der resultierende Typ für `anon` hätte eine Eigenschaft, `Book`, des Typs <xref:System.Collections.IEnumerable>(Of XElement).

- Aus einer Funktion, die keine Parameter hat, z. B. `SomeFunction` im folgenden Beispiel.

  ```vb
  Dim sc As New SomeClass
  Dim anon1 = New With {Key sc.SomeFunction()}
  ```

  Die Variable `anon2` im folgenden Code ist ein anonymer Typ, der eine Eigenschaft hat: ein Zeichen namens `First`. Dieser Code zeigt den Buchstaben "E" an, der von der Funktion <xref:System.Linq.Enumerable.First%2A>zurückgegeben wird.

  [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]

## <a name="inference-failures"></a>Ableitungsfehler

#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>Die Ableitung von Namen schlägt in vielen Fällen fehl, etwa in den folgenden:

- Die Ableitung erfolgt über den Aufruf einer Methode, eines Konstruktors oder einer parametrisierten Eigenschaft, die Argumente erfordert. Die vorherige Deklaration von `anon1` schlägt fehl, wenn `someFunction` ein oder mehrere Argumente hat.

  ```vb
  ' Not valid.
  ' Dim anon3 = New With {Key sc.someFunction(someArg)}
  ```

  Durch Zuweisung zu einem neuen Eigenschaftennamen kann das Problem gelöst werden.

  ```vb
  ' Valid.
  Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}
  ```

- Die Ableitung erfolgt aus einem komplexen Ausdruck.

  ```vb
  Dim aString As String = "Act "
  ' Not valid.
  ' Dim label = New With {Key aString & "IV"}
  ```

  Der Fehler kann behoben werden, indem das Ergebnis des Ausdrucks einem Eigenschaftennamen zugewiesen wird.

  [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]

- Die Ableitung für mehrere Eigenschaften führt zu zwei oder mehr Eigenschaften mit demselben Namen. Ein Rückblick auf die Deklarationen in früheren Beispielen zeigt, dass es nicht möglich ist, sowohl `product.Name` als auch `car1.Name` als Eigenschaften desselben anonymen Typs aufzulisten. Dies liegt daran, dass der abgeleitete Bezeichner für beide Eigenschaften gleich `Name`wäre.

  ```vb
  ' Not valid.
  ' Dim anon5 = New With {Key product.Name, Key car1.Name}
  ```

  Das Problem kann gelöst werden, indem die Werte unterschiedlichen Eigenschaftennamen zugewiesen werden.

  [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]

  Beachten Sie, dass eine unterschiedliche Schreibweise (Unterschiede in der Groß- und Kleinschreibung) nicht dazu führt, dass zwei Namen unterschiedlich sind.

  ```vb
  Dim price = 0
  ' Not valid, because Price and price are the same name.
  ' Dim anon7 = New With {Key product.Price, Key price}
  ```

- Der ursprüngliche Typ und Wert einer Eigenschaft sind von einer anderen Eigenschaft abhängig, die noch nicht festgelegt wurde. Zum Beispiel ist `.IDName = .LastName` in der Deklaration eines anonymen Typs nicht zulässig, wenn `.LastName` noch nicht initialisiert wurde.

  ```vb
  ' Not valid.
  ' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}
  ```

  In diesem Beispiel kann das Problem behoben werden, indem die Reihenfolge, in der die Eigenschaften deklariert werden, umgekehrt wird.

  [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]

- Ein Eigenschaftennamen eines anonymen Typs ist mit dem Namen eines Members von <xref:System.Object>identisch. Zum Beispiel schlägt die folgende Deklaration fehl, weil `Equals` eine Methode von <xref:System.Object>ist.

  ```vb
  ' Not valid.
  ' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _
  '                       "greater than", Key .Less = "less than"}
  ```

  Sie können das Problem beheben, indem Sie den Eigenschaftennamen ändern:

  [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]

## <a name="see-also"></a>Siehe auch

- [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
