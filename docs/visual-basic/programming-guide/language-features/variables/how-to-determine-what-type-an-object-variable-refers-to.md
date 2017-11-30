---
title: 'Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5dd6785ecd48be3f0455de63b9e3f13a485ddbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="4c474-102">Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c474-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="4c474-103">Eine Objektvariable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4c474-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="4c474-104">Der Typ der Daten kann während der Laufzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="4c474-104">The type of that data can change during run time.</span></span> <span data-ttu-id="4c474-105">Zu jedem Zeitpunkt können Sie die <xref:System.Type.GetTypeCode%2A> Methode, um den aktuellen Laufzeittyp festzulegen oder die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) um zu ermitteln, ob der aktuelle Laufzeittyp mit einem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="4c474-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="4c474-106">Um zu bestimmen, dass die genaue geben derzeit eine Objektvariable verweist auf</span><span class="sxs-lookup"><span data-stu-id="4c474-106">To determine the exact type an object variable currently refers to</span></span>  
  
1.  <span data-ttu-id="4c474-107">Rufen Sie die Objektvariable der <xref:System.Object.GetType%2A> Methode zum Abrufen einer <xref:System.Type?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4c474-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <span data-ttu-id="4c474-108">Auf der <xref:System.Type?displayProperty=nameWithType> Klasse, rufen Sie die freigegebene Methode <xref:System.Type.GetTypeCode%2A> zum Abrufen der <xref:System.TypeCode> Enumerationswert für den Typ des Objekts.</span><span class="sxs-lookup"><span data-stu-id="4c474-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="4c474-109">Sie können testen, die <xref:System.TypeCode> Enumerationswert für Enumerationsmember von Interesse, z. B. sind `Double`.</span><span class="sxs-lookup"><span data-stu-id="4c474-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="4c474-110">Um zu bestimmen, ob ein Objekt ist Variablentyp kompatibel mit einem angegebenen Typ</span><span class="sxs-lookup"><span data-stu-id="4c474-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="4c474-111">Verwenden der `TypeOf` Operator in Kombination mit der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) So testen Sie das Objekt mit einem `TypeOf`... `Is` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c474-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="4c474-112">Die `TypeOf`... `Is` Ausdruck gibt `True` Typ ist mit dem angegebenen Typ kompatibel, wenn der zur Laufzeit des Objekts.</span><span class="sxs-lookup"><span data-stu-id="4c474-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="4c474-113">Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, Struktur oder Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="4c474-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="4c474-114">Im Allgemeinen sind die Typen kompatibel, wenn das Objekt des gleichen Typs als ist, erbt oder den angegebenen Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="4c474-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="4c474-115">Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4c474-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c474-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4c474-116">Compiling the Code</span></span>  
 <span data-ttu-id="4c474-117">Beachten Sie, dass der angegebene Typ eine Variable oder ein Ausdruck sein kann.</span><span class="sxs-lookup"><span data-stu-id="4c474-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="4c474-118">Es muss der Name eines definierten Typs, z. B. eine Klasse, Struktur oder Schnittstelle sein.</span><span class="sxs-lookup"><span data-stu-id="4c474-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="4c474-119">Dazu gehören auch die systeminterne Typen `Integer` und `String`.</span><span class="sxs-lookup"><span data-stu-id="4c474-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c474-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c474-120">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [<span data-ttu-id="4c474-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="4c474-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="4c474-122">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="4c474-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="4c474-123">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c474-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
