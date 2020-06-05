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
ms.openlocfilehash: 405297a25d4b948a6920bd989c7826e8b6f66bb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398206"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="4ef99-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ef99-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="4ef99-103">Gibt an, dass eine Variable oder Eigenschaft gelesen, aber nicht geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="4ef99-103">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ef99-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4ef99-104">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="4ef99-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="4ef99-105">Rules</span></span>

- <span data-ttu-id="4ef99-106">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="4ef99-106">**Declaration Context.**</span></span> <span data-ttu-id="4ef99-107">Sie können `ReadOnly` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ef99-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="4ef99-108">Dies bedeutet, dass der Deklarations Kontext für ein- `ReadOnly` Element eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="4ef99-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="4ef99-109">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="4ef99-109">**Combined Modifiers.**</span></span> <span data-ttu-id="4ef99-110">Sie können nicht `ReadOnly` mit `Static` in der gleichen Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="4ef99-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="4ef99-111">**Zuweisen eines Werts.**</span><span class="sxs-lookup"><span data-stu-id="4ef99-111">**Assigning a Value.**</span></span> <span data-ttu-id="4ef99-112">Code, der eine Eigenschaft beansprucht, `ReadOnly` kann seinen Wert nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="4ef99-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="4ef99-113">Code, der Zugriff auf den zugrunde liegenden Speicher hat, kann den Wert jedoch jederzeit zuweisen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="4ef99-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="4ef99-114">Sie können einer Variablen einen Wert `ReadOnly` nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur zuweisen, in der Sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4ef99-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="4ef99-115">Verwendung einer schreibgeschützten Variablen</span><span class="sxs-lookup"><span data-stu-id="4ef99-115">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="4ef99-116">Es gibt Situationen, in denen Sie keine Konstanten- [Anweisung](../statements/const-statement.md) verwenden können, um einen konstanten Wert zu deklarieren und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ef99-116">There are situations in which you cannot use a [Const Statement](../statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="4ef99-117">Beispielsweise akzeptiert die- `Const` Anweisung möglicherweise nicht den Datentyp, den Sie zuweisen möchten, oder Sie können den Wert möglicherweise nicht zur Kompilierzeit mit einem konstanten Ausdruck berechnen.</span><span class="sxs-lookup"><span data-stu-id="4ef99-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="4ef99-118">Möglicherweise wissen Sie den Wert zum Zeitpunkt der Kompilierung nicht einmal.</span><span class="sxs-lookup"><span data-stu-id="4ef99-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="4ef99-119">In diesen Fällen können Sie eine Variable verwenden, `ReadOnly` um einen konstanten Wert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4ef99-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ef99-120">Wenn der Datentyp der Variablen ein Referenztyp ist, z. b. ein Array oder eine Klasseninstanz, können die Member auch dann geändert werden, wenn die Variable selbst ist `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="4ef99-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="4ef99-121">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4ef99-121">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="4ef99-122">Bei der Initialisierung enthält das Array, auf das verweist, `characterArray()` "x", "y" und "z".</span><span class="sxs-lookup"><span data-stu-id="4ef99-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="4ef99-123">Da die Variable `characterArray` ist `ReadOnly` , können Sie Ihren Wert nicht ändern, nachdem Sie initialisiert wurde, d. h., Sie können kein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ef99-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="4ef99-124">Sie können jedoch die Werte von einem oder mehreren Arraymembern ändern.</span><span class="sxs-lookup"><span data-stu-id="4ef99-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="4ef99-125">Im Anschluss an einen aufzurufenden Vorgang `ChangeArrayElement` enthält das Array, auf das verweist, das Zeichen `characterArray()` "x", "M" und "z".</span><span class="sxs-lookup"><span data-stu-id="4ef99-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="4ef99-126">Beachten Sie, dass dies dem Deklarieren eines Prozedur Parameters als [ByVal](byval.md)ähnelt, wodurch verhindert wird, dass die Prozedur das aufrufende Argument selbst ändert, aber seine Member ändern kann.</span><span class="sxs-lookup"><span data-stu-id="4ef99-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="4ef99-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ef99-127">Example</span></span>

<span data-ttu-id="4ef99-128">Im folgenden Beispiel wird eine- `ReadOnly` Eigenschaft für das Datum definiert, an dem ein Mitarbeiter eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4ef99-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="4ef99-129">Die-Klasse speichert den Eigenschafts Wert intern als `Private` Variable, und nur Code in der Klasse kann diesen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="4ef99-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="4ef99-130">Die-Eigenschaft ist jedoch `Public` , und jeder Code, der auf die-Klasse zugreifen kann, kann die-Eigenschaft lesen.</span><span class="sxs-lookup"><span data-stu-id="4ef99-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="4ef99-131">Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4ef99-131">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="4ef99-132">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4ef99-132">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="4ef99-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4ef99-133">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="4ef99-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ef99-134">See also</span></span>

- [<span data-ttu-id="4ef99-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="4ef99-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="4ef99-136">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4ef99-136">Keywords</span></span>](../keywords/index.md)
