---
title: Definition von anonymen Typen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 832d56f5c51aea87185f36ec306c3fec036a40e0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825546"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="63c1b-102">Definition von anonymen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63c1b-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="63c1b-103">Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften für den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="63c1b-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="63c1b-104">Vom Compiler generierter Code</span><span class="sxs-lookup"><span data-stu-id="63c1b-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="63c1b-105">Für die folgende Definition `product`, erstellt der Compiler eine neue Klassendefinition, die Eigenschaften enthält `Name`, `Price`, und `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="63c1b-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]  
  
 <span data-ttu-id="63c1b-106">Die Definition der Klasse enthält die Eigenschaftsdefinitionen, die etwa wie folgt.</span><span class="sxs-lookup"><span data-stu-id="63c1b-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="63c1b-107">Beachten Sie, dass es keine `Set` -Methode für die wichtigsten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="63c1b-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="63c1b-108">Die Werte der Eigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="63c1b-108">The values of key properties are read-only.</span></span>  
  
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
  
 <span data-ttu-id="63c1b-109">Darüber hinaus enthalten die Definitionen von anonymen Typen einen standardmäßigen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="63c1b-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="63c1b-110">Konstruktoren, die Parameter erfordern, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="63c1b-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="63c1b-111">Wenn die Deklaration eines anonymen Typs mindestens eine Schlüsseleigenschaft enthält, überschreibt die Typdefinition drei von geerbte Member <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="63c1b-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="63c1b-112">Wenn keine Eigenschaften, nur deklariert werden <xref:System.Object.ToString%2A> überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="63c1b-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="63c1b-113">Die Außerkraftsetzungen werden die folgenden Funktionen enthalten:</span><span class="sxs-lookup"><span data-stu-id="63c1b-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="63c1b-114">`Equals` Gibt `True` Wenn zwei Instanzen eines anonymen Typs dieselbe Instanz sind oder wenn sie die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="63c1b-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="63c1b-115">Sie haben die gleiche Anzahl von Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="63c1b-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="63c1b-116">Die Eigenschaften werden deklariert, in der gleichen Reihenfolge, mit dem gleichen Namen und denselben abgeleiteten Typen.</span><span class="sxs-lookup"><span data-stu-id="63c1b-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="63c1b-117">Beim Vergleichen wird nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="63c1b-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="63c1b-118">Mindestens eine der Eigenschaften ist eine wichtige Eigenschaft, und die `Key` -Schlüsselwort auf die gleichen Eigenschaften angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="63c1b-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="63c1b-119">Vergleich der einzelnen entsprechenden Schlüsseleigenschaften gibt `True`.</span><span class="sxs-lookup"><span data-stu-id="63c1b-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="63c1b-120">In den folgenden Beispielen wird z. B. `Equals` gibt `True` nur für `employee01` und `employee08`.</span><span class="sxs-lookup"><span data-stu-id="63c1b-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="63c1b-121">Der Kommentar vor jeder Zeile gibt den Grund an, warum die neue Instanz stimmt nicht überein `employee01`.</span><span class="sxs-lookup"><span data-stu-id="63c1b-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]  
  
-   <span data-ttu-id="63c1b-122">`GetHashcode` Stellt einen entsprechend eindeutigen GetHashCode-Algorithmus bereit.</span><span class="sxs-lookup"><span data-stu-id="63c1b-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="63c1b-123">Der Algorithmus verwendet nur die wichtigsten Eigenschaften, um den Hash zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="63c1b-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="63c1b-124">`ToString` Gibt eine Zeichenfolge mit verketteten Eigenschaftswerte zurück, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="63c1b-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="63c1b-125">Sowohl Schlüssel als auch nicht schlüsselbezogene Eigenschaften sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="63c1b-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]  
  
 <span data-ttu-id="63c1b-126">Explizit benannte Eigenschaften eines anonymen Typs können nicht in Konflikt mit diesen generierten Methoden stehen.</span><span class="sxs-lookup"><span data-stu-id="63c1b-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="63c1b-127">D. h. Sie können keine `.Equals`, `.GetHashCode`, oder `.ToString` um eine Eigenschaft zu nennen.</span><span class="sxs-lookup"><span data-stu-id="63c1b-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="63c1b-128">Definitionen von anonymen Typen, die über mindestens einen Schlüsseleigenschaft auch implementieren die <xref:System.IEquatable%601?displayProperty=nameWithType> -Schnittstelle, in denen `T` ist der Typ des anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="63c1b-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63c1b-129">Deklarationen von anonymen Typen erstellen desselben anonymen Typs nur dann, wenn die Zeitpunkte in der gleichen Assembly, deren Eigenschaften die gleichen Namen haben und denselben Typen abgeleiteten, die Eigenschaften in der gleichen Reihenfolge deklariert werden und die gleichen Eigenschaften werden als Schlüsseleigenschaften gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="63c1b-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c1b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63c1b-130">See also</span></span>

- [<span data-ttu-id="63c1b-131">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="63c1b-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="63c1b-132">Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="63c1b-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
