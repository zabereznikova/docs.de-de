---
title: '&amp;-Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 20c2e2088691e68221872cc1dfc5486413515a4d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867155"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="22d7a-102">&amp; Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22d7a-102">&amp; Operator (Visual Basic)</span></span>

<span data-ttu-id="22d7a-103">Generiert eine Zeichen folgen Verkettung von zwei Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="22d7a-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d7a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22d7a-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="22d7a-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="22d7a-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="22d7a-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="22d7a-106">Required.</span></span> <span data-ttu-id="22d7a-107">Beliebige- `String` oder- `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="22d7a-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="22d7a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="22d7a-108">Required.</span></span> <span data-ttu-id="22d7a-109">Jeder Ausdruck mit einem Datentyp, der zu erweitert wird `String` .</span><span class="sxs-lookup"><span data-stu-id="22d7a-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="22d7a-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="22d7a-110">Required.</span></span> <span data-ttu-id="22d7a-111">Jeder Ausdruck mit einem Datentyp, der zu erweitert wird `String` .</span><span class="sxs-lookup"><span data-stu-id="22d7a-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22d7a-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="22d7a-112">Remarks</span></span>  

 <span data-ttu-id="22d7a-113">Wenn der Datentyp von `expression1` oder `expression2` nicht ist `String` `String` , wird er in konvertiert `String` .</span><span class="sxs-lookup"><span data-stu-id="22d7a-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="22d7a-114">Wenn einer der Datentypen nicht in erweitert `String` wird, generiert der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="22d7a-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="22d7a-115">Der Datentyp von `result` ist `String` .</span><span class="sxs-lookup"><span data-stu-id="22d7a-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="22d7a-116">Wenn ein oder beide Ausdrücke als " [Nothing](../nothing.md) " ausgewertet werden oder den Wert aufweisen <xref:System.DBNull.Value?displayProperty=nameWithType> , werden Sie als Zeichenfolge mit dem Wert "" behandelt.</span><span class="sxs-lookup"><span data-stu-id="22d7a-116">If one or both expressions evaluate to [Nothing](../nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22d7a-117">Der `&` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="22d7a-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="22d7a-118">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="22d7a-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="22d7a-119">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="22d7a-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22d7a-120">Das kaufmännische und-Zeichen (&) kann auch verwendet werden, um Variablen als Typ zu identifizieren `Long` .</span><span class="sxs-lookup"><span data-stu-id="22d7a-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="22d7a-121">Weitere Informationen finden Sie unter [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="22d7a-121">For more information, see [Type Characters](../../programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d7a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22d7a-122">Example</span></span>  

 <span data-ttu-id="22d7a-123">In diesem Beispiel wird der- `&` Operator verwendet, um die Zeichen folgen Verkettung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="22d7a-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="22d7a-124">Das Ergebnis ist ein Zeichen folgen Wert, der die Verkettung der beiden Zeichen folgen Operanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="22d7a-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="22d7a-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22d7a-125">See also</span></span>

- [<span data-ttu-id="22d7a-126">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="22d7a-126">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="22d7a-127">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="22d7a-127">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="22d7a-128">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22d7a-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="22d7a-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="22d7a-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="22d7a-130">Verkettungsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22d7a-130">Concatenation Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
