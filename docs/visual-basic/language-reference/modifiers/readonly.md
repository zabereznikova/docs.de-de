---
title: ReadOnly
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
ms.openlocfilehash: 8c7e7e7c1571fd7c595ebfd54fb5767078ef41f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351281"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="d161b-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d161b-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="d161b-103">Gibt an, dass eine Variable oder Eigenschaft gelesen, aber nicht geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="d161b-103">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="d161b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d161b-104">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="d161b-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="d161b-105">Rules</span></span>

- <span data-ttu-id="d161b-106">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="d161b-106">**Declaration Context.**</span></span> <span data-ttu-id="d161b-107">Sie können `ReadOnly` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="d161b-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="d161b-108">Dies bedeutet, dass der Deklarations Kontext für ein `ReadOnly` Element eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="d161b-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="d161b-109">**Kombinierte modifiziererer.**</span><span class="sxs-lookup"><span data-stu-id="d161b-109">**Combined Modifiers.**</span></span> <span data-ttu-id="d161b-110">Sie können `ReadOnly` nicht mit `Static` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="d161b-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="d161b-111">**Zuweisen eines Werts.**</span><span class="sxs-lookup"><span data-stu-id="d161b-111">**Assigning a Value.**</span></span> <span data-ttu-id="d161b-112">Code, der eine `ReadOnly` Eigenschaft beansprucht, kann seinen Wert nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="d161b-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="d161b-113">Code, der Zugriff auf den zugrunde liegenden Speicher hat, kann den Wert jedoch jederzeit zuweisen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="d161b-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="d161b-114">Sie können einer `ReadOnly` Variable nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur, in der Sie definiert ist, einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d161b-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="d161b-115">Verwendung einer schreibgeschützten Variablen</span><span class="sxs-lookup"><span data-stu-id="d161b-115">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="d161b-116">Es gibt Situationen, in denen Sie keine Konstanten- [Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) verwenden können, um einen konstanten Wert zu deklarieren und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d161b-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="d161b-117">Beispielsweise akzeptiert die `Const`-Anweisung möglicherweise nicht den Datentyp, den Sie zuweisen möchten, oder Sie können den Wert möglicherweise nicht zur Kompilierzeit mit einem konstanten Ausdruck berechnen.</span><span class="sxs-lookup"><span data-stu-id="d161b-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="d161b-118">Möglicherweise wissen Sie den Wert zum Zeitpunkt der Kompilierung nicht einmal.</span><span class="sxs-lookup"><span data-stu-id="d161b-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="d161b-119">In diesen Fällen können Sie eine `ReadOnly` Variable verwenden, um einen konstanten Wert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d161b-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d161b-120">Wenn der Datentyp der Variablen ein Referenztyp ist, z. b. ein Array oder eine Klasseninstanz, können die zugehörigen Member auch dann geändert werden, wenn die Variable selbst `ReadOnly`ist.</span><span class="sxs-lookup"><span data-stu-id="d161b-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="d161b-121">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="d161b-121">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="d161b-122">Bei der Initialisierung zeigt das Array, auf das von `characterArray()` verwiesen wird, "x", "y" und "z".</span><span class="sxs-lookup"><span data-stu-id="d161b-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="d161b-123">Da die Variable `characterArray` `ReadOnly`ist, können Sie Ihren Wert nicht ändern, nachdem Sie initialisiert wurde. Das heißt, Sie können kein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d161b-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="d161b-124">Sie können jedoch die Werte von einem oder mehreren Arraymembern ändern.</span><span class="sxs-lookup"><span data-stu-id="d161b-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="d161b-125">Im Anschluss an einen aufzurufenden Prozedur `ChangeArrayElement`enthält das Array, auf das von `characterArray()` verwiesen wird, "x", "M" und "z".</span><span class="sxs-lookup"><span data-stu-id="d161b-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="d161b-126">Beachten Sie, dass dies dem Deklarieren eines Prozedur Parameters als [ByVal](byval.md)ähnelt, wodurch verhindert wird, dass die Prozedur das aufrufende Argument selbst ändert, aber seine Member ändern kann.</span><span class="sxs-lookup"><span data-stu-id="d161b-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="d161b-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d161b-127">Example</span></span>

<span data-ttu-id="d161b-128">Im folgenden Beispiel wird eine `ReadOnly`-Eigenschaft für das Datum definiert, an dem ein Mitarbeiter eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d161b-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="d161b-129">Die-Klasse speichert den Eigenschafts Wert intern als `Private` Variable, und nur Code in der Klasse kann diesen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="d161b-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="d161b-130">Die-Eigenschaft ist jedoch `Public`, und jeder Code, der auf die-Klasse zugreifen kann, kann die-Eigenschaft lesen.</span><span class="sxs-lookup"><span data-stu-id="d161b-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="d161b-131">Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d161b-131">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="d161b-132">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d161b-132">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="d161b-133">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d161b-133">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="d161b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d161b-134">See also</span></span>

- [<span data-ttu-id="d161b-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="d161b-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="d161b-136">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d161b-136">Keywords</span></span>](../keywords/index.md)
