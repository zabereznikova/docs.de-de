---
title: 'Vorgehensweise: Bestimmen des Typs, auf den eine Objekt Variable verweist (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 935623dd4b6edca188f932aca0e560130199e8f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626571"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="3b4d9-102">Vorgehensweise: Bestimmen des Typs, auf den eine Objekt Variable verweist (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b4d9-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="3b4d9-103">Eine Objekt Variable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="3b4d9-104">Der Typ der Daten, die während der Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-104">The type of that data can change during run time.</span></span> <span data-ttu-id="3b4d9-105">Sie können jederzeit die <xref:System.Type.GetTypeCode%2A> -Methode verwenden, um den aktuellen Lauf Zeittyp zu bestimmen, oder den [typeof-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) , um herauszufinden, ob der aktuelle Lauf Zeittyp mit einem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="3b4d9-106">So bestimmen Sie den genauen Typ, auf den eine Objekt Variable zurzeit verweist</span><span class="sxs-lookup"><span data-stu-id="3b4d9-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="3b4d9-107">Rufen Sie die <xref:System.Object.GetType%2A> -Methode für die-Objekt Variable auf <xref:System.Type?displayProperty=nameWithType> , um ein-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="3b4d9-108">Rufen Sie <xref:System.Type?displayProperty=nameWithType> in der-Klasse die Shared <xref:System.Type.GetTypeCode%2A> -Methode auf <xref:System.TypeCode> , um den-Enumerationswert für den Objekttyp abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="3b4d9-109">Sie können den Enumerationswert mit den <xref:System.TypeCode> von Ihnen relevanten Enumerationsmembern testen, `Double`z. b.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="3b4d9-110">So bestimmen Sie, ob der Typ einer Objektvariablen mit einem angegebenen Typ kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="3b4d9-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="3b4d9-111">Verwenden Sie `TypeOf` den-Operator in Kombination mit dem [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) , um `TypeOf`das Objekt mit einem... `Is` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="3b4d9-112">Die `TypeOf`... der Ausdruck `True` gibt zurück, wenn der Lauf Zeittyp des Objekts mit dem angegebenen Typ kompatibel ist. `Is`</span><span class="sxs-lookup"><span data-stu-id="3b4d9-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="3b4d9-113">Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, eine Struktur oder eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="3b4d9-114">Im Allgemeinen sind die Typen kompatibel, wenn das Objekt vom gleichen Typ ist wie, erbt von oder implementiert den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="3b4d9-115">Weitere Informationen finden Sie unter [typeof-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="3b4d9-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="3b4d9-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3b4d9-116">Compiling the Code</span></span>

<span data-ttu-id="3b4d9-117">Beachten Sie, dass der angegebene Typ keine Variable oder kein Ausdruck sein darf.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="3b4d9-118">Dabei muss es sich um den Namen eines definierten Typs handeln, z. b. eine Klasse, Struktur oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="3b4d9-119">Dies schließt intrinsische Typen wie `Integer` und `String`ein.</span><span class="sxs-lookup"><span data-stu-id="3b4d9-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b4d9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b4d9-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="3b4d9-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="3b4d9-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="3b4d9-122">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="3b4d9-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="3b4d9-123">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3b4d9-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
