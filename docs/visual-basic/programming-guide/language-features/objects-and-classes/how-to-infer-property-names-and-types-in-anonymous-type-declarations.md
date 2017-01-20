---
title: "Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Ableiten von Eigenschaftennamen [Visual Basic]"
  - "Anonyme Typen [Visual Basic], Ableiten von Eigenschaftennamen und -typen"
  - "Ableiten von Eigenschaftentypen [Visual Basic]"
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Anonyme Typen stellen keinen Mechanismus zum direkten Angeben der Datentypen von Eigenschaften bereit. Die Typen aller Eigenschaften werden abgeleitet. Im folgenden Beispiel werden die Typen von `Name` und `Price` direkt aus den Werten abgeleitet, mit denen sie initialisiert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_1.vb)]  
  
 Anonyme Typen können Eigenschaftennamen und \-typen auch aus anderen Quellen ableiten. In den folgenden Abschnitten werden sowohl eine Liste der Umstände, unter denen Ableitung möglich ist, als auch Beispiele bereitgestellt, in denen keine Ableitung möglich ist.  
  
## Erfolgreiche Ableitung  
  
#### Anonyme Typen können Eigenschaftennamen und \-typen aus folgenden Quellen ableiten:  
  
-   Aus Variablennamen. Der anonyme Typ `anonProduct` hat die beiden Eigenschaften `productName` und `productPrice`. Ihre Datentypen sind gleich denen der ursprünglichen Variablen, also `String` bzw. `Double`.  
  
     [!code-vb[VbVbalrAnonymousTypes#11](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_2.vb)]  
  
-   Aus Eigenschaften\- oder Feldnamen anderer Objekte. Betrachten Sie z. B. ein `car`\-Objekt eines `CarClass`\-Typs, der die `Name`\-Eigenschaft und die `ID`\-Eigenschaft enthält. Um die neue Instanz `car1` des anonymen Typs mit der `Name`\-Eigenschaft und der `ID`\-Eigenschaft zu erstellen, die mit den Werten aus dem `car`\-Objekt initialisiert werden, können Sie folgenden Code schreiben:  
  
     [!code-vb[VbVbalrAnonymousTypes#34](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_3.vb)]  
  
     Die vorherige Deklaration ist mit der längeren Codezeile gleichwertig, in der der anonyme Typ `car2` definiert ist.  
  
     [!code-vb[VbVbalrAnonymousTypes#35](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_4.vb)]  
  
-   Aus XML\-Membernamen.  
  
     [!code-vb[VbVbalrAnonymousTypes#12](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_5.vb)]  
  
     Der resultierende Typ für `anon` hätte eine Eigenschaft, `Book`, des Typs <xref:System.Collections.IEnumerable>\(Of XElement\).  
  
-   Aus einer Funktion, die keine Parameter hat, z. B. `SomeFunction` im folgenden Beispiel.  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     Die Variable `anon2` im folgenden Code ist ein anonymer Typ, der eine Eigenschaft hat: ein Zeichen namens `First`. Dieser Code zeigt den Buchstaben "E" an, der von der Funktion <xref:System.Linq.Enumerable.First%2A> zurückgegeben wird.  
  
     [!code-vb[VbVbalrAnonymousTypes#13](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_6.vb)]  
  
## Ableitungsfehler  
  
#### Die Ableitung von Namen schlägt in vielen Fällen fehl, etwa in den folgenden:  
  
-   Die Ableitung erfolgt über den Aufruf einer Methode, eines Konstruktors oder einer parametrisierten Eigenschaft, die Argumente erfordert. Die vorherige Deklaration von `anon1` schlägt fehl, wenn `someFunction` ein oder mehrere Argumente hat.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     Durch Zuweisung zu einem neuen Eigenschaftennamen kann das Problem gelöst werden.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   Die Ableitung erfolgt aus einem komplexen Ausdruck.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     Der Fehler kann behoben werden, indem das Ergebnis des Ausdrucks einem Eigenschaftennamen zugewiesen wird.  
  
     [!code-vb[VbVbalrAnonymousTypes#14](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_7.vb)]  
  
-   Die Ableitung für mehrere Eigenschaften führt zu zwei oder mehr Eigenschaften mit demselben Namen. Ein Rückblick auf die Deklarationen in früheren Beispielen zeigt, dass es nicht möglich ist, sowohl `product.Name` als auch `car1.Name` als Eigenschaften desselben anonymen Typs aufzulisten. Dies liegt daran, dass der abgeleitete Bezeichner für beide Eigenschaften gleich `Name` wäre.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     Das Problem kann gelöst werden, indem die Werte unterschiedlichen Eigenschaftennamen zugewiesen werden.  
  
     [!code-vb[VbVbalrAnonymousTypes#36](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_8.vb)]  
  
     Beachten Sie, dass eine unterschiedliche Schreibweise \(Unterschiede in der Groß\- und Kleinschreibung\) nicht dazu führt, dass zwei Namen unterschiedlich sind.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   Der ursprüngliche Typ und Wert einer Eigenschaft sind von einer anderen Eigenschaft abhängig, die noch nicht festgelegt wurde. Zum Beispiel ist `.IDName = .LastName` in der Deklaration eines anonymen Typs nicht zulässig, wenn `.LastName` noch nicht initialisiert wurde.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     In diesem Beispiel kann das Problem behoben werden, indem die Reihenfolge, in der die Eigenschaften deklariert werden, umgekehrt wird.  
  
     [!code-vb[VbVbalrAnonymousTypes#15](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_9.vb)]  
  
-   Ein Eigenschaftennamen eines anonymen Typs ist mit dem Namen eines Members von <xref:System.Object> identisch. Zum Beispiel schlägt die folgende Deklaration fehl, weil `Equals` eine Methode von <xref:System.Object> ist.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     Sie können das Problem beheben, indem Sie den Eigenschaftennamen ändern:  
  
     [!code-vb[VbVbalrAnonymousTypes#16](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names_10.vb)]  
  
## Siehe auch  
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)