---
title: 'Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 67cc9e85d249365a7b4b7636c99766087314622d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596858"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a><span data-ttu-id="cab30-102">Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab30-102">How to: Infer Property Names and Types in Anonymous Type Declarations (Visual Basic)</span></span>
<span data-ttu-id="cab30-103">Anonyme Typen stellen keinen Mechanismus zum direkten Angeben der Datentypen von Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="cab30-103">Anonymous types provide no mechanism for directly specifying the data types of properties.</span></span> <span data-ttu-id="cab30-104">Die Typen aller Eigenschaften werden abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="cab30-104">Types of all properties are inferred.</span></span> <span data-ttu-id="cab30-105">Im folgenden Beispiel werden die Typen von `Name` und `Price` direkt aus den Werten abgeleitet, mit denen sie initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cab30-105">In the following example, the types of `Name` and `Price` are inferred directly from the values that are used to initialize them.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_1.vb)]  
  
 <span data-ttu-id="cab30-106">Anonyme Typen können Eigenschaftennamen und -typen auch aus anderen Quellen ableiten.</span><span class="sxs-lookup"><span data-stu-id="cab30-106">Anonymous types can also infer property names and types from other sources.</span></span> <span data-ttu-id="cab30-107">In den folgenden Abschnitten werden sowohl eine Liste der Umstände, unter denen Ableitung möglich ist, als auch Beispiele bereitgestellt, in denen keine Ableitung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="cab30-107">The sections that follow provide a list of the circumstances where inference is possible, and examples of situations where it is not.</span></span>  
  
## <a name="successful-inference"></a><span data-ttu-id="cab30-108">Erfolgreiche Ableitung</span><span class="sxs-lookup"><span data-stu-id="cab30-108">Successful Inference</span></span>  
  
#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a><span data-ttu-id="cab30-109">Anonyme Typen können Eigenschaftennamen und -typen aus folgenden Quellen ableiten:</span><span class="sxs-lookup"><span data-stu-id="cab30-109">Anonymous types can infer property names and types from the following sources:</span></span>  
  
-   <span data-ttu-id="cab30-110">Aus Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="cab30-110">From variable names.</span></span> <span data-ttu-id="cab30-111">Der anonyme Typ `anonProduct` hat die beiden Eigenschaften `productName` und `productPrice`.</span><span class="sxs-lookup"><span data-stu-id="cab30-111">Anonymous type `anonProduct` will have two properties, `productName` and `productPrice`.</span></span> <span data-ttu-id="cab30-112">Ihre Datentypen sind gleich denen der ursprünglichen Variablen, also `String` bzw. `Double`.</span><span class="sxs-lookup"><span data-stu-id="cab30-112">Their data types will be those of the original variables, `String` and `Double`, respectively.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#11](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_2.vb)]  
  
-   <span data-ttu-id="cab30-113">Aus Eigenschaften- oder Feldnamen anderer Objekte.</span><span class="sxs-lookup"><span data-stu-id="cab30-113">From property or field names of other objects.</span></span> <span data-ttu-id="cab30-114">Betrachten Sie z. B. ein `car` -Objekt eines `CarClass` -Typs, der die `Name` -Eigenschaft und die `ID` -Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="cab30-114">For example, consider a `car` object of a `CarClass` type that includes `Name` and `ID` properties.</span></span> <span data-ttu-id="cab30-115">Um die neue Instanz `car1`des anonymen Typs mit der `Name` -Eigenschaft und der `ID` -Eigenschaft zu erstellen, die mit den Werten aus dem `car` -Objekt initialisiert werden, können Sie folgenden Code schreiben:</span><span class="sxs-lookup"><span data-stu-id="cab30-115">To create a new anonymous type instance, `car1`, with `Name` and `ID` properties that are initialized with the values from the `car` object, you can write the following:</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#34](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_3.vb)]  
  
     <span data-ttu-id="cab30-116">Die vorherige Deklaration ist mit der längeren Codezeile gleichwertig, in der der anonyme Typ `car2`definiert ist.</span><span class="sxs-lookup"><span data-stu-id="cab30-116">The previous declaration is equivalent to the longer line of code that defines anonymous type `car2`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#35](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_4.vb)]  
  
-   <span data-ttu-id="cab30-117">Aus XML-Membernamen.</span><span class="sxs-lookup"><span data-stu-id="cab30-117">From XML member names.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#12](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_5.vb)]  
  
     <span data-ttu-id="cab30-118">Der resultierende Typ für `anon` hätte eine Eigenschaft, `Book`, des Typs <xref:System.Collections.IEnumerable>(Of XElement).</span><span class="sxs-lookup"><span data-stu-id="cab30-118">The resulting type for `anon` would have one property, `Book`, of type <xref:System.Collections.IEnumerable>(Of XElement).</span></span>  
  
-   <span data-ttu-id="cab30-119">Aus einer Funktion, die keine Parameter hat, z. B. `SomeFunction` im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cab30-119">From a function that has no parameters, such as `SomeFunction` in the following example.</span></span>  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     <span data-ttu-id="cab30-120">Die Variable `anon2` im folgenden Code ist ein anonymer Typ, der eine Eigenschaft hat: ein Zeichen namens `First`.</span><span class="sxs-lookup"><span data-stu-id="cab30-120">The variable `anon2` in the following code is an anonymous type that has one property, a character named `First`.</span></span> <span data-ttu-id="cab30-121">Dieser Code zeigt den Buchstaben "E" an, der von der Funktion <xref:System.Linq.Enumerable.First%2A>zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cab30-121">This code will display a letter "E," the letter that is returned by function <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#13](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_6.vb)]  
  
## <a name="inference-failures"></a><span data-ttu-id="cab30-122">Ableitungsfehler</span><span class="sxs-lookup"><span data-stu-id="cab30-122">Inference Failures</span></span>  
  
#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a><span data-ttu-id="cab30-123">Die Ableitung von Namen schlägt in vielen Fällen fehl, etwa in den folgenden:</span><span class="sxs-lookup"><span data-stu-id="cab30-123">Name inference will fail in many circumstances, including the following:</span></span>  
  
-   <span data-ttu-id="cab30-124">Die Ableitung erfolgt über den Aufruf einer Methode, eines Konstruktors oder einer parametrisierten Eigenschaft, die Argumente erfordert.</span><span class="sxs-lookup"><span data-stu-id="cab30-124">The inference derives from the invocation of a method, a constructor, or a parameterized property that requires arguments.</span></span> <span data-ttu-id="cab30-125">Die vorherige Deklaration von `anon1` schlägt fehl, wenn `someFunction` ein oder mehrere Argumente hat.</span><span class="sxs-lookup"><span data-stu-id="cab30-125">The previous declaration of `anon1` fails if `someFunction` has one or more arguments.</span></span>  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     <span data-ttu-id="cab30-126">Durch Zuweisung zu einem neuen Eigenschaftennamen kann das Problem gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="cab30-126">Assignment to a new property name solves the problem.</span></span>  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   <span data-ttu-id="cab30-127">Die Ableitung erfolgt aus einem komplexen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="cab30-127">The inference derives from a complex expression.</span></span>  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     <span data-ttu-id="cab30-128">Der Fehler kann behoben werden, indem das Ergebnis des Ausdrucks einem Eigenschaftennamen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cab30-128">The error can be resolved by assigning the result of the expression to a property name.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#14](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_7.vb)]  
  
-   <span data-ttu-id="cab30-129">Die Ableitung für mehrere Eigenschaften führt zu zwei oder mehr Eigenschaften mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="cab30-129">Inference for multiple properties produces two or more properties that have the same name.</span></span> <span data-ttu-id="cab30-130">Ein Rückblick auf die Deklarationen in früheren Beispielen zeigt, dass es nicht möglich ist, sowohl `product.Name` als auch `car1.Name` als Eigenschaften desselben anonymen Typs aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="cab30-130">Referring back to declarations in earlier examples, you cannot list both `product.Name` and `car1.Name` as properties of the same anonymous type.</span></span> <span data-ttu-id="cab30-131">Dies liegt daran, dass der abgeleitete Bezeichner für beide Eigenschaften gleich `Name`wäre.</span><span class="sxs-lookup"><span data-stu-id="cab30-131">This is because the inferred identifier for each of these would be `Name`.</span></span>  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     <span data-ttu-id="cab30-132">Das Problem kann gelöst werden, indem die Werte unterschiedlichen Eigenschaftennamen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cab30-132">The problem can be solved by assigning the values to distinct property names.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#36](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_8.vb)]  
  
     <span data-ttu-id="cab30-133">Beachten Sie, dass eine unterschiedliche Schreibweise (Unterschiede in der Groß- und Kleinschreibung) nicht dazu führt, dass zwei Namen unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="cab30-133">Note that changes in case (changes between uppercase and lowercase letters) do not make two names distinct.</span></span>  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   <span data-ttu-id="cab30-134">Der ursprüngliche Typ und Wert einer Eigenschaft sind von einer anderen Eigenschaft abhängig, die noch nicht festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="cab30-134">The initial type and value of one property depends on another property that is not yet established.</span></span> <span data-ttu-id="cab30-135">Zum Beispiel ist `.IDName = .LastName` in der Deklaration eines anonymen Typs nicht zulässig, wenn `.LastName` noch nicht initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cab30-135">For example, `.IDName = .LastName` is not valid in an anonymous type declaration unless `.LastName` is already initialized.</span></span>  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     <span data-ttu-id="cab30-136">In diesem Beispiel kann das Problem behoben werden, indem die Reihenfolge, in der die Eigenschaften deklariert werden, umgekehrt wird.</span><span class="sxs-lookup"><span data-stu-id="cab30-136">In this example, you can fix the problem by reversing the order in which the properties are declared.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#15](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_9.vb)]  
  
-   <span data-ttu-id="cab30-137">Ein Eigenschaftennamen eines anonymen Typs ist mit dem Namen eines Members von <xref:System.Object>identisch.</span><span class="sxs-lookup"><span data-stu-id="cab30-137">A property name of the anonymous type is the same as the name of a member of <xref:System.Object>.</span></span> <span data-ttu-id="cab30-138">Zum Beispiel schlägt die folgende Deklaration fehl, weil `Equals` eine Methode von <xref:System.Object>ist.</span><span class="sxs-lookup"><span data-stu-id="cab30-138">For example, the following declaration fails because `Equals` is a method of <xref:System.Object>.</span></span>  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     <span data-ttu-id="cab30-139">Sie können das Problem beheben, indem Sie den Eigenschaftennamen ändern:</span><span class="sxs-lookup"><span data-stu-id="cab30-139">You can fix the problem by changing the property name:</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#16](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_10.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cab30-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cab30-140">See also</span></span>
- [<span data-ttu-id="cab30-141">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="cab30-141">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="cab30-142">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="cab30-142">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="cab30-143">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="cab30-143">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="cab30-144">Key</span><span class="sxs-lookup"><span data-stu-id="cab30-144">Key</span></span>](../../../../visual-basic/language-reference/modifiers/key.md)
