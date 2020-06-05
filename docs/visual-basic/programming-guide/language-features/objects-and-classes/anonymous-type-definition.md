---
title: Definition von anonymen Typen
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 952eb295cc71eab5d0ad6e18f2b697a9b701b434
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404900"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="0afb4-102">Definition von anonymen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0afb4-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="0afb4-103">Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften für den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="0afb4-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="0afb4-104">Vom Compiler generierter Code</span><span class="sxs-lookup"><span data-stu-id="0afb4-104">Compiler-Generated Code</span></span>

<span data-ttu-id="0afb4-105">Für die folgende Definition von `product` erstellt der Compiler eine neue Klassendefinition, die die Eigenschaften `Name` , `Price` und enthält `OnHand` .</span><span class="sxs-lookup"><span data-stu-id="0afb4-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="0afb4-106">Die Klassendefinition enthält Eigenschafts Definitionen ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="0afb4-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="0afb4-107">Beachten Sie, dass es keine `Set` Methode für die Schlüsseleigenschaften gibt.</span><span class="sxs-lookup"><span data-stu-id="0afb4-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="0afb4-108">Die Werte der Schlüsseleigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="0afb4-108">The values of key properties are read-only.</span></span>

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

<span data-ttu-id="0afb4-109">Außerdem enthalten anonyme Typdefinitionen einen Parameter losen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="0afb4-109">In addition, anonymous type definitions contain a parameterless constructor.</span></span> <span data-ttu-id="0afb4-110">Konstruktoren, die Parameter erfordern, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0afb4-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="0afb4-111">Wenn eine Deklaration eines anonymen Typs mindestens eine Schlüsseleigenschaft enthält, überschreibt die Typdefinition drei von geerbte Member <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> und <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="0afb4-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="0afb4-112">Wenn keine Schlüsseleigenschaften deklariert werden, <xref:System.Object.ToString%2A> wird nur überschrieben.</span><span class="sxs-lookup"><span data-stu-id="0afb4-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="0afb4-113">Die außer Kraft setzungen bieten die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="0afb4-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="0afb4-114">`Equals`Gibt zurück `True` , wenn zwei anonyme Typinstanzen dieselbe Instanz sind, oder, wenn Sie die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="0afb4-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="0afb4-115">Sie verfügen über die gleiche Anzahl von Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0afb4-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="0afb4-116">Die Eigenschaften werden in derselben Reihenfolge deklariert, mit denselben Namen und denselben abhergenten Typen.</span><span class="sxs-lookup"><span data-stu-id="0afb4-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="0afb4-117">Bei namens vergleichen wird die Groß-/Kleinschreibung nicht beachtet</span><span class="sxs-lookup"><span data-stu-id="0afb4-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="0afb4-118">Mindestens eine der Eigenschaften ist eine Schlüsseleigenschaft, und das `Key` Schlüsselwort wird auf die gleichen Eigenschaften angewendet.</span><span class="sxs-lookup"><span data-stu-id="0afb4-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="0afb4-119">Der Vergleich der einzelnen entsprechenden paar Schlüsseleigenschaften gibt zurück `True` .</span><span class="sxs-lookup"><span data-stu-id="0afb4-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="0afb4-120">In den folgenden Beispielen gibt z. b `Equals` `True` . nur für `employee01` und zurück `employee08` .</span><span class="sxs-lookup"><span data-stu-id="0afb4-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="0afb4-121">Der Kommentar vor jeder Zeile gibt den Grund an, warum die neue Instanz nicht übereinstimmt `employee01` .</span><span class="sxs-lookup"><span data-stu-id="0afb4-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="0afb4-122">`GetHashcode`stellt einen entsprechend eindeutigen GetHashCode-Algorithmus bereit.</span><span class="sxs-lookup"><span data-stu-id="0afb4-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="0afb4-123">Der Algorithmus verwendet nur die Schlüsseleigenschaften, um den Hashcode zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="0afb4-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="0afb4-124">`ToString`gibt eine Zeichenfolge mit verketteten Eigenschafts Werten zurück, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0afb4-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="0afb4-125">Es sind sowohl Schlüssel-als auch nicht Schlüsseleigenschaften enthalten.</span><span class="sxs-lookup"><span data-stu-id="0afb4-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="0afb4-126">Explizit benannte Eigenschaften eines anonymen Typs können nicht mit diesen generierten Methoden in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="0afb4-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="0afb4-127">Das heißt, Sie können, oder nicht verwenden, `.Equals` `.GetHashCode` `.ToString` um eine Eigenschaft zu benennen.</span><span class="sxs-lookup"><span data-stu-id="0afb4-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="0afb4-128">Anonyme Typdefinitionen, die mindestens eine Schlüsseleigenschaft enthalten, implementieren auch die- <xref:System.IEquatable%601?displayProperty=nameWithType> Schnittstelle, wobei `T` der Typ des anonymen Typs ist.</span><span class="sxs-lookup"><span data-stu-id="0afb4-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="0afb4-129">Deklarationen anonymer Typen erstellen nur dann denselben anonymen Typ, wenn Sie in derselben Assembly auftreten, deren Eigenschaften dieselben Namen und die gleichen abhergenten Typen aufweisen, die Eigenschaften in der gleichen Reihenfolge deklariert werden und dieselben Eigenschaften als Schlüsseleigenschaften gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="0afb4-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="0afb4-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0afb4-130">See also</span></span>

- [<span data-ttu-id="0afb4-131">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0afb4-131">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="0afb4-132">Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="0afb4-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
