---
title: 'Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 9ebbbe9d2e6d36f5ab2bc7f7c916d18c9240a06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404887"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a><span data-ttu-id="69400-102">Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69400-102">How to: Infer Property Names and Types in Anonymous Type Declarations (Visual Basic)</span></span>

<span data-ttu-id="69400-103">Anonyme Typen stellen keinen Mechanismus zum direkten Angeben der Datentypen von Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="69400-103">Anonymous types provide no mechanism for directly specifying the data types of properties.</span></span> <span data-ttu-id="69400-104">Die Typen aller Eigenschaften werden abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="69400-104">Types of all properties are inferred.</span></span> <span data-ttu-id="69400-105">Im folgenden Beispiel werden die Typen von `Name` und `Price` direkt aus den Werten abgeleitet, mit denen sie initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="69400-105">In the following example, the types of `Name` and `Price` are inferred directly from the values that are used to initialize them.</span></span>

[!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]

<span data-ttu-id="69400-106">Anonyme Typen können Eigenschaftennamen und -typen auch aus anderen Quellen ableiten.</span><span class="sxs-lookup"><span data-stu-id="69400-106">Anonymous types can also infer property names and types from other sources.</span></span> <span data-ttu-id="69400-107">In den folgenden Abschnitten werden sowohl eine Liste der Umstände, unter denen Ableitung möglich ist, als auch Beispiele bereitgestellt, in denen keine Ableitung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="69400-107">The sections that follow provide a list of the circumstances where inference is possible, and examples of situations where it is not.</span></span>

## <a name="successful-inference"></a><span data-ttu-id="69400-108">Erfolgreiche Ableitung</span><span class="sxs-lookup"><span data-stu-id="69400-108">Successful Inference</span></span>

#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a><span data-ttu-id="69400-109">Anonyme Typen können Eigenschaftennamen und -typen aus folgenden Quellen ableiten:</span><span class="sxs-lookup"><span data-stu-id="69400-109">Anonymous types can infer property names and types from the following sources:</span></span>

- <span data-ttu-id="69400-110">Aus Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="69400-110">From variable names.</span></span> <span data-ttu-id="69400-111">Der anonyme Typ `anonProduct` hat die beiden Eigenschaften `productName` und `productPrice`.</span><span class="sxs-lookup"><span data-stu-id="69400-111">Anonymous type `anonProduct` will have two properties, `productName` and `productPrice`.</span></span> <span data-ttu-id="69400-112">Ihre Datentypen sind gleich denen der ursprünglichen Variablen, also `String` bzw. `Double`.</span><span class="sxs-lookup"><span data-stu-id="69400-112">Their data types will be those of the original variables, `String` and `Double`, respectively.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]

- <span data-ttu-id="69400-113">Aus Eigenschaften- oder Feldnamen anderer Objekte.</span><span class="sxs-lookup"><span data-stu-id="69400-113">From property or field names of other objects.</span></span> <span data-ttu-id="69400-114">Betrachten Sie z. B. ein `car` -Objekt eines `CarClass` -Typs, der die `Name` -Eigenschaft und die `ID` -Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="69400-114">For example, consider a `car` object of a `CarClass` type that includes `Name` and `ID` properties.</span></span> <span data-ttu-id="69400-115">Um die neue Instanz `car1`des anonymen Typs mit der `Name` -Eigenschaft und der `ID` -Eigenschaft zu erstellen, die mit den Werten aus dem `car` -Objekt initialisiert werden, können Sie folgenden Code schreiben:</span><span class="sxs-lookup"><span data-stu-id="69400-115">To create a new anonymous type instance, `car1`, with `Name` and `ID` properties that are initialized with the values from the `car` object, you can write the following:</span></span>

  [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]

  <span data-ttu-id="69400-116">Die vorherige Deklaration ist mit der längeren Codezeile gleichwertig, in der der anonyme Typ `car2`definiert ist.</span><span class="sxs-lookup"><span data-stu-id="69400-116">The previous declaration is equivalent to the longer line of code that defines anonymous type `car2`.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]

- <span data-ttu-id="69400-117">Aus XML-Membernamen.</span><span class="sxs-lookup"><span data-stu-id="69400-117">From XML member names.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]

  <span data-ttu-id="69400-118">Der resultierende Typ für `anon` hätte eine Eigenschaft, `Book`, des Typs <xref:System.Collections.IEnumerable>(Of XElement).</span><span class="sxs-lookup"><span data-stu-id="69400-118">The resulting type for `anon` would have one property, `Book`, of type <xref:System.Collections.IEnumerable>(Of XElement).</span></span>

- <span data-ttu-id="69400-119">Aus einer Funktion, die keine Parameter hat, z. B. `SomeFunction` im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="69400-119">From a function that has no parameters, such as `SomeFunction` in the following example.</span></span>

  ```vb
  Dim sc As New SomeClass
  Dim anon1 = New With {Key sc.SomeFunction()}
  ```

  <span data-ttu-id="69400-120">Die Variable `anon2` im folgenden Code ist ein anonymer Typ, der eine Eigenschaft hat: ein Zeichen namens `First`.</span><span class="sxs-lookup"><span data-stu-id="69400-120">The variable `anon2` in the following code is an anonymous type that has one property, a character named `First`.</span></span> <span data-ttu-id="69400-121">Dieser Code zeigt den Buchstaben "E" an, der von der Funktion <xref:System.Linq.Enumerable.First%2A>zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="69400-121">This code will display a letter "E," the letter that is returned by function <xref:System.Linq.Enumerable.First%2A>.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]

## <a name="inference-failures"></a><span data-ttu-id="69400-122">Ableitungsfehler</span><span class="sxs-lookup"><span data-stu-id="69400-122">Inference Failures</span></span>

#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a><span data-ttu-id="69400-123">Die Ableitung von Namen schlägt in vielen Fällen fehl, etwa in den folgenden:</span><span class="sxs-lookup"><span data-stu-id="69400-123">Name inference will fail in many circumstances, including the following:</span></span>

- <span data-ttu-id="69400-124">Die Ableitung erfolgt über den Aufruf einer Methode, eines Konstruktors oder einer parametrisierten Eigenschaft, die Argumente erfordert.</span><span class="sxs-lookup"><span data-stu-id="69400-124">The inference derives from the invocation of a method, a constructor, or a parameterized property that requires arguments.</span></span> <span data-ttu-id="69400-125">Die vorherige Deklaration von `anon1` schlägt fehl, wenn `someFunction` ein oder mehrere Argumente hat.</span><span class="sxs-lookup"><span data-stu-id="69400-125">The previous declaration of `anon1` fails if `someFunction` has one or more arguments.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon3 = New With {Key sc.someFunction(someArg)}
  ```

  <span data-ttu-id="69400-126">Durch Zuweisung zu einem neuen Eigenschaftennamen kann das Problem gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="69400-126">Assignment to a new property name solves the problem.</span></span>

  ```vb
  ' Valid.
  Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}
  ```

- <span data-ttu-id="69400-127">Die Ableitung erfolgt aus einem komplexen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="69400-127">The inference derives from a complex expression.</span></span>

  ```vb
  Dim aString As String = "Act "
  ' Not valid.
  ' Dim label = New With {Key aString & "IV"}
  ```

  <span data-ttu-id="69400-128">Der Fehler kann behoben werden, indem das Ergebnis des Ausdrucks einem Eigenschaftennamen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="69400-128">The error can be resolved by assigning the result of the expression to a property name.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]

- <span data-ttu-id="69400-129">Die Ableitung für mehrere Eigenschaften führt zu zwei oder mehr Eigenschaften mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="69400-129">Inference for multiple properties produces two or more properties that have the same name.</span></span> <span data-ttu-id="69400-130">Ein Rückblick auf die Deklarationen in früheren Beispielen zeigt, dass es nicht möglich ist, sowohl `product.Name` als auch `car1.Name` als Eigenschaften desselben anonymen Typs aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="69400-130">Referring back to declarations in earlier examples, you cannot list both `product.Name` and `car1.Name` as properties of the same anonymous type.</span></span> <span data-ttu-id="69400-131">Dies liegt daran, dass der abgeleitete Bezeichner für beide Eigenschaften gleich `Name`wäre.</span><span class="sxs-lookup"><span data-stu-id="69400-131">This is because the inferred identifier for each of these would be `Name`.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon5 = New With {Key product.Name, Key car1.Name}
  ```

  <span data-ttu-id="69400-132">Das Problem kann gelöst werden, indem die Werte unterschiedlichen Eigenschaftennamen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="69400-132">The problem can be solved by assigning the values to distinct property names.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]

  <span data-ttu-id="69400-133">Beachten Sie, dass eine unterschiedliche Schreibweise (Unterschiede in der Groß- und Kleinschreibung) nicht dazu führt, dass zwei Namen unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="69400-133">Note that changes in case (changes between uppercase and lowercase letters) do not make two names distinct.</span></span>

  ```vb
  Dim price = 0
  ' Not valid, because Price and price are the same name.
  ' Dim anon7 = New With {Key product.Price, Key price}
  ```

- <span data-ttu-id="69400-134">Der ursprüngliche Typ und Wert einer Eigenschaft sind von einer anderen Eigenschaft abhängig, die noch nicht festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="69400-134">The initial type and value of one property depends on another property that is not yet established.</span></span> <span data-ttu-id="69400-135">Zum Beispiel ist `.IDName = .LastName` in der Deklaration eines anonymen Typs nicht zulässig, wenn `.LastName` noch nicht initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="69400-135">For example, `.IDName = .LastName` is not valid in an anonymous type declaration unless `.LastName` is already initialized.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}
  ```

  <span data-ttu-id="69400-136">In diesem Beispiel kann das Problem behoben werden, indem die Reihenfolge, in der die Eigenschaften deklariert werden, umgekehrt wird.</span><span class="sxs-lookup"><span data-stu-id="69400-136">In this example, you can fix the problem by reversing the order in which the properties are declared.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]

- <span data-ttu-id="69400-137">Ein Eigenschaftennamen eines anonymen Typs ist mit dem Namen eines Members von <xref:System.Object>identisch.</span><span class="sxs-lookup"><span data-stu-id="69400-137">A property name of the anonymous type is the same as the name of a member of <xref:System.Object>.</span></span> <span data-ttu-id="69400-138">Zum Beispiel schlägt die folgende Deklaration fehl, weil `Equals` eine Methode von <xref:System.Object>ist.</span><span class="sxs-lookup"><span data-stu-id="69400-138">For example, the following declaration fails because `Equals` is a method of <xref:System.Object>.</span></span>

  ```vb
  ' Not valid.
  ' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _
  '                       "greater than", Key .Less = "less than"}
  ```

  <span data-ttu-id="69400-139">Sie können das Problem beheben, indem Sie den Eigenschaftennamen ändern:</span><span class="sxs-lookup"><span data-stu-id="69400-139">You can fix the problem by changing the property name:</span></span>

  [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]

## <a name="see-also"></a><span data-ttu-id="69400-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69400-140">See also</span></span>

- [<span data-ttu-id="69400-141">Objektinitialisierer: benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="69400-141">Object Initializers: Named and Anonymous Types</span></span>](object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="69400-142">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="69400-142">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="69400-143">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="69400-143">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="69400-144">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="69400-144">Key</span></span>](../../../language-reference/modifiers/key.md)
