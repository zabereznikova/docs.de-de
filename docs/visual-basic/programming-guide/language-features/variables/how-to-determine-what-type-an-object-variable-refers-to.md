---
title: 'Vorgehensweise: Bestimmen des Typs, auf den eine Objektvariable verweist'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: d3224000f5958a8619e38c4d2f6dc5dbb275ad45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410489"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="92279-102">Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92279-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="92279-103">Eine Objekt Variable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="92279-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="92279-104">Der Typ der Daten, die während der Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="92279-104">The type of that data can change during run time.</span></span> <span data-ttu-id="92279-105">Sie können jederzeit die-Methode verwenden, <xref:System.Type.GetTypeCode%2A> um den aktuellen Lauf Zeittyp zu bestimmen, oder den [typeof-Operator](../../../language-reference/operators/typeof-operator.md) , um herauszufinden, ob der aktuelle Lauf Zeittyp mit einem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="92279-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="92279-106">So bestimmen Sie den genauen Typ, auf den eine Objekt Variable zurzeit verweist</span><span class="sxs-lookup"><span data-stu-id="92279-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="92279-107">Rufen Sie die-Methode für die-Objekt Variable auf, <xref:System.Object.GetType%2A> um ein- <xref:System.Type?displayProperty=nameWithType> Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="92279-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="92279-108">Rufen Sie in der- <xref:System.Type?displayProperty=nameWithType> Klasse die Shared-Methode auf, <xref:System.Type.GetTypeCode%2A> um den <xref:System.TypeCode> -Enumerationswert für den Objekttyp abzurufen.</span><span class="sxs-lookup"><span data-stu-id="92279-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="92279-109">Sie können den <xref:System.TypeCode> Enumerationswert mit den von Ihnen relevanten Enumerationsmembern testen, z `Double` . b..</span><span class="sxs-lookup"><span data-stu-id="92279-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="92279-110">So bestimmen Sie, ob der Typ einer Objektvariablen mit einem angegebenen Typ kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="92279-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="92279-111">Verwenden Sie den- `TypeOf` Operator in Kombination mit dem [is-Operator](../../../language-reference/operators/is-operator.md) , um das Objekt mit einem `TypeOf` ...-Ausdruck zu testen `Is` .</span><span class="sxs-lookup"><span data-stu-id="92279-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="92279-112">Der `TypeOf` ... `Is` -Ausdruck gibt zurück, `True` Wenn der Lauf Zeittyp des Objekts mit dem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="92279-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="92279-113">Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, eine Struktur oder eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="92279-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="92279-114">Im Allgemeinen sind die Typen kompatibel, wenn das Objekt vom gleichen Typ ist wie, erbt von oder implementiert den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="92279-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="92279-115">Weitere Informationen finden Sie unter [typeof-Operator](../../../language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="92279-115">For more information, see [TypeOf Operator](../../../language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="92279-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="92279-116">Compile the code</span></span>

<span data-ttu-id="92279-117">Beachten Sie, dass der angegebene Typ keine Variable oder kein Ausdruck sein darf.</span><span class="sxs-lookup"><span data-stu-id="92279-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="92279-118">Dabei muss es sich um den Namen eines definierten Typs handeln, z. b. eine Klasse, Struktur oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="92279-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="92279-119">Dies schließt intrinsische Typen wie `Integer` und ein `String` .</span><span class="sxs-lookup"><span data-stu-id="92279-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="92279-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92279-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="92279-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="92279-121">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="92279-122">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="92279-122">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="92279-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="92279-123">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
