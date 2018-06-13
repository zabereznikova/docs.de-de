---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599911"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="16cef-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16cef-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="16cef-103">Gibt an, dass eine Variable oder die Eigenschaft lesen aber nicht geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="16cef-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16cef-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16cef-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="16cef-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="16cef-105">Rules</span></span>  
  
-   <span data-ttu-id="16cef-106">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="16cef-106">**Declaration Context.**</span></span> <span data-ttu-id="16cef-107">Sie können `ReadOnly` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="16cef-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="16cef-108">Dies bedeutet, dass der Deklarationskontext für eine `ReadOnly` Element muss eine Klasse, Struktur oder Modul, und eine Quelldatei, Namespace oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="16cef-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="16cef-109">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="16cef-109">**Combined Modifiers.**</span></span> <span data-ttu-id="16cef-110">Sie können keine angeben `ReadOnly` zusammen mit `Static` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="16cef-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="16cef-111">**Zuweisen eines Werts an.**</span><span class="sxs-lookup"><span data-stu-id="16cef-111">**Assigning a Value.**</span></span> <span data-ttu-id="16cef-112">Code, in dem eine `ReadOnly` Eigenschaft der Wert kann nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="16cef-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="16cef-113">Code, der auf den zugrunde liegenden Speicher zugreifen kann jedoch zuweisen oder ändern Sie den Wert zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="16cef-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="16cef-114">Sie können einen Wert zuweisen einer `ReadOnly` Variable nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur, die in der sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="16cef-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="16cef-115">Eine schreibgeschützte Variable zu verwenden</span><span class="sxs-lookup"><span data-stu-id="16cef-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="16cef-116">Es gibt Situationen, in dem Sie können nicht mit, einem [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) zu deklarieren und Zuweisen eines konstanten Werts.</span><span class="sxs-lookup"><span data-stu-id="16cef-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="16cef-117">Z. B. die `Const` Anweisung möglicherweise nicht übernehmen den Datentyp, die Sie zuweisen möchten, oder Sie können möglicherweise nicht den Wert zum Zeitpunkt der Kompilierung mit einem konstanten Ausdruck zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="16cef-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="16cef-118">Sie bemerken möglicherweise nicht auch den Wert zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="16cef-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="16cef-119">In diesen Fällen können Sie eine `ReadOnly` Variable verweist, einen konstanten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="16cef-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16cef-120">Der Datentyp der Variablen ein Verweistyp, wie z. B. ein Array oder eine Klasseninstanz ist ihre Member können geändert werden, auch wenn die Variable selbst ist `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="16cef-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="16cef-121">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="16cef-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="16cef-122">Bei der Initialisierung, das Array verweist `characterArray()` enthält "X", "y" und "Z".</span><span class="sxs-lookup"><span data-stu-id="16cef-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="16cef-123">Da die Variable `characterArray` ist `ReadOnly`, dessen Wert kann nicht geändert werden, sobald er initialisiert wurde, die; nicht möglich, weisen Sie ein neues Array zu.</span><span class="sxs-lookup"><span data-stu-id="16cef-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="16cef-124">Allerdings können Sie die Werte von mindestens einer der Array-Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="16cef-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="16cef-125">Nach einem Aufruf an die Prozedur `changeArrayElement`, das Array verweist `characterArray()` enthält "X", "M" und "Z".</span><span class="sxs-lookup"><span data-stu-id="16cef-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="16cef-126">Beachten Sie, dass dies deklarieren einen Prozedurparameter werden ähnelt [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), die verhindert, dass der Prozedur das aufrufende Argument selbst zu ändern, jedoch kann er seine Mitglieder ändern.</span><span class="sxs-lookup"><span data-stu-id="16cef-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16cef-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16cef-127">Example</span></span>  
 <span data-ttu-id="16cef-128">Das folgende Beispiel definiert eine `ReadOnly` -Eigenschaft für das Datum, an dem ein Mitarbeiter eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="16cef-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="16cef-129">Die Klasse speichert den Eigenschaftswert intern als eine `Private` Variable, und nur Code innerhalb der Klasse kann diesen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="16cef-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="16cef-130">Die Eigenschaft ist jedoch `Public`, und jeglicher Code, der die Klasse zugreifen kann, kann die Eigenschaft lesen.</span><span class="sxs-lookup"><span data-stu-id="16cef-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 <span data-ttu-id="16cef-131">Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="16cef-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="16cef-132">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16cef-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="16cef-133">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16cef-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="16cef-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16cef-134">See Also</span></span>  
 [<span data-ttu-id="16cef-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="16cef-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="16cef-136">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="16cef-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
