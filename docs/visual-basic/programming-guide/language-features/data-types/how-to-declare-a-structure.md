---
title: 'Gewusst wie: Deklarieren einer Struktur (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8203327e189d095c9f7ceeb3b68ea24efe9ba882
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="1cb67-102">Gewusst wie: Deklarieren einer Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cb67-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="1cb67-103">Structure-Deklarationen mit Beginn der [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md), und beenden sie mit der `End` `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1cb67-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End` `Structure` statement.</span></span> <span data-ttu-id="1cb67-104">Zwischen diesen beiden Anweisungen müssen Sie mindestens eine deklarieren *Element*.</span><span class="sxs-lookup"><span data-stu-id="1cb67-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="1cb67-105">Die Elemente können einen beliebigen Datentyp aufweisen, jedoch muss mindestens eine nicht freigegebene Variable oder ein nicht freigegebenes, nicht benutzerdefinierte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1cb67-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="1cb67-106">Sie können nicht der Struktur Elemente in der Strukturdeklaration initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1cb67-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="1cb67-107">Wenn Sie eine Variable eines Strukturtyps deklarieren, weisen Sie Werte mit den Elementen, indem Sie auf diese über die Variable zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1cb67-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="1cb67-108">Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen, finden Sie unter [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="1cb67-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="1cb67-109">Erwägen Sie zu Demonstrationszwecken, wo Sie zum Nachverfolgen eines Mitarbeiters Name Durchwahl und Gehalt erwünscht.</span><span class="sxs-lookup"><span data-stu-id="1cb67-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="1cb67-110">Eine Struktur können Sie hierzu in eine einzelne Variable sein.</span><span class="sxs-lookup"><span data-stu-id="1cb67-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="1cb67-111">Um eine Struktur zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1cb67-111">To declare a structure</span></span>  
  
1.  <span data-ttu-id="1cb67-112">Beginn und Ende von Anweisungen für die Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1cb67-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="1cb67-113">Sie können angeben, die Zugriffsebene einer Struktur mit der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort, oder Sie können Standardmäßig `Public`.</span><span class="sxs-lookup"><span data-stu-id="1cb67-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  <span data-ttu-id="1cb67-114">Fügen Sie Elemente in den Text der Struktur hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cb67-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="1cb67-115">Eine Struktur muss mindestens ein Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="1cb67-115">A structure must have at least one element.</span></span> <span data-ttu-id="1cb67-116">Sie müssen jedes Element deklarieren und eine Zugriffsebene dafür angeben.</span><span class="sxs-lookup"><span data-stu-id="1cb67-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="1cb67-117">Bei Verwendung der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) ohne Schlüsselwörter, die Zugriffsebene standardmäßig `Public`.</span><span class="sxs-lookup"><span data-stu-id="1cb67-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="1cb67-118">Die `salary` Feld im vorherigen Beispiel ist `Private`, d. h. außerhalb der Struktur nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1cb67-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="1cb67-119">Allerdings die `giveRaise` Verfahren ist `Public`, sodass sie von außerhalb der Struktur aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1cb67-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="1cb67-120">Sie können auf ähnliche Weise Auslösen der `salaryReviewTime` Ereignis außerhalb der Struktur.</span><span class="sxs-lookup"><span data-stu-id="1cb67-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="1cb67-121">Zusätzlich zu den Variablen `Sub` Prozeduren und Ereignisse, Sie können auch Konstanten definieren `Function` Prozeduren und Eigenschaften in einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="1cb67-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="1cb67-122">Sie können festlegen, dass höchstens eine Eigenschaft als die *Standardeigenschaft*, sofern er mindestens ein Argument erhält.</span><span class="sxs-lookup"><span data-stu-id="1cb67-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="1cb67-123">Sie können ein Ereignis mit Behandeln einer [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1cb67-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="1cb67-124">Weitere Informationen finden Sie unter [wie: Deklarieren und Aufrufen einer Default-Eigenschaft in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="1cb67-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb67-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cb67-125">See Also</span></span>  
 [<span data-ttu-id="1cb67-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1cb67-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="1cb67-127">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="1cb67-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="1cb67-128">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="1cb67-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="1cb67-129">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="1cb67-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="1cb67-130">Strukturen</span><span class="sxs-lookup"><span data-stu-id="1cb67-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="1cb67-131">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="1cb67-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="1cb67-132">Strukturvariablen</span><span class="sxs-lookup"><span data-stu-id="1cb67-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [<span data-ttu-id="1cb67-133">Strukturen und andere Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="1cb67-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="1cb67-134">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="1cb67-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="1cb67-135">Benutzerdefinierter Datentyp</span><span class="sxs-lookup"><span data-stu-id="1cb67-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
