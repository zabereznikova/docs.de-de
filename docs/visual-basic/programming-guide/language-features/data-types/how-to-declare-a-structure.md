---
title: 'Gewusst wie: Deklarieren einer Struktur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: c3090b5b8e53e5a5a990ae11c91464797bde9803
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582305"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="4fdd1-102">Gewusst wie: Deklarieren einer Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fdd1-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="4fdd1-103">Sie beginnen eine Struktur Deklaration mit der [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)und beenden Sie mit der `End Structure`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="4fdd1-104">Zwischen diesen beiden Anweisungen müssen Sie mindestens ein *Element*deklarieren.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="4fdd1-105">Die Elemente können einen beliebigen Datentyp aufweisen, aber mindestens einen muss entweder eine nicht freigegebene Variable oder ein nicht frei gegebenes, Nichtbenutzer definiertes Ereignis sein.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="4fdd1-106">Sie können keines der Structure-Elemente in der Struktur Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="4fdd1-107">Wenn Sie eine Variable als Strukturtyp deklarieren, weisen Sie den Elementen Werte zu, indem Sie über die Variable darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="4fdd1-108">Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen finden Sie unter [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="4fdd1-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="4fdd1-109">Berücksichtigen Sie zu Demonstrationszwecken eine Situation, in der Sie den Namen, die telefonerweiterung und das Gehalt eines Mitarbeiters nachverfolgen möchten.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="4fdd1-110">Eine-Struktur ermöglicht es Ihnen, dies in einer einzelnen Variablen zu tun.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="4fdd1-111">So deklarieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="4fdd1-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="4fdd1-112">Erstellen Sie die Start-und End-Anweisungen für die-Struktur.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="4fdd1-113">Sie können die Zugriffsebene einer Struktur mithilfe des Schlüssel Worts [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)oder [private](../../../../visual-basic/language-reference/modifiers/private.md) angeben, oder Sie können die Standardeinstellung `Public` festlegen.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="4fdd1-114">Fügen Sie dem Text der-Strukturelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="4fdd1-115">Eine-Struktur muss mindestens ein-Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-115">A structure must have at least one element.</span></span> <span data-ttu-id="4fdd1-116">Sie müssen jedes Element deklarieren und eine Zugriffsebene dafür angeben.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="4fdd1-117">Wenn Sie die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) ohne Schlüsselwörter verwenden, ist die Barrierefreiheit standardmäßig `Public`.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="4fdd1-118">Das `salary`-Feld im vorangehenden Beispiel ist `Private`. Dies bedeutet, dass außerhalb der Struktur nicht auf Sie zugegriffen werden kann, auch nicht aus der enthaltenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="4fdd1-119">Die `giveRaise` Prozedur ist jedoch `Public`, sodass Sie von außerhalb der Struktur aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="4fdd1-120">Auf ähnliche Weise können Sie das `salaryReviewTime`-Ereignis von außerhalb der-Struktur aus erhöhen.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="4fdd1-121">Zusätzlich zu Variablen, `Sub` Prozeduren und Ereignissen können Sie auch Konstanten, `Function` Prozeduren und Eigenschaften in einer Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="4fdd1-122">Sie können höchstens eine Eigenschaft als *Standard Eigenschaft*festlegen, sofern Sie mindestens ein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="4fdd1-123">Sie können ein Ereignis mit einem frei [gegebenen](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Verfahren verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4fdd1-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="4fdd1-124">Weitere Informationen finden Sie unter Vorgehens [Weise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="4fdd1-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fdd1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fdd1-125">See also</span></span>

- [<span data-ttu-id="4fdd1-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="4fdd1-127">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="4fdd1-128">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="4fdd1-129">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="4fdd1-130">Strukturen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4fdd1-131">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="4fdd1-132">Strukturvariablen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="4fdd1-133">Strukturen und andere Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="4fdd1-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="4fdd1-134">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="4fdd1-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="4fdd1-135">Benutzerdefinierter Datentyp</span><span class="sxs-lookup"><span data-stu-id="4fdd1-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
