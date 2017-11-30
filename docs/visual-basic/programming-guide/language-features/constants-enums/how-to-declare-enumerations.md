---
title: 'Gewusst wie: Deklarieren einer Enumeration (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="171fb-102">Gewusst wie: Deklarieren einer Enumeration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="171fb-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="171fb-103">Sie erstellen eine Enumeration mit den `Enum` Anweisung im Deklarationsabschnitt einer Klasse oder das Modul.</span><span class="sxs-lookup"><span data-stu-id="171fb-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="171fb-104">Eine Enumeration innerhalb einer Methode nicht deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="171fb-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="171fb-105">Verwenden Sie zum Angeben der entsprechenden Ebene des Zugriffs `Private`, `Protected`, `Friend`, oder `Public`.</span><span class="sxs-lookup"><span data-stu-id="171fb-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="171fb-106">Ein `Enum` Typ hat einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, von denen jedes eine Konstante darstellt.</span><span class="sxs-lookup"><span data-stu-id="171fb-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="171fb-107">Der Name muss ein gültiger Visual Basic .NET Qualifizierer sein.</span><span class="sxs-lookup"><span data-stu-id="171fb-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="171fb-108">Der zugrunde liegende Typ muss eines der ganzzahligen Typen sein –`Byte`, `Short`, `Long` oder `Integer`.</span><span class="sxs-lookup"><span data-stu-id="171fb-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="171fb-109">Standardmäßig ist `Integer` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="171fb-109">`Integer` is the default.</span></span> <span data-ttu-id="171fb-110">Enumerationen sind immer stark typisiert und sind nicht austauschbar mit Ganzzahltypen.</span><span class="sxs-lookup"><span data-stu-id="171fb-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="171fb-111">Enumerationen können keine Gleitkommawerte haben.</span><span class="sxs-lookup"><span data-stu-id="171fb-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="171fb-112">Wenn eine Enumeration einen Gleitkommawert mit zugewiesen ist `Option Strict On`, ein Compilerfehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="171fb-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="171fb-113">Wenn `Option Strict` ist `Off`, der Wert wird automatisch konvertiert, um die `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="171fb-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="171fb-114">Informationen zu Namen und zum Verwenden der `Imports` -Anweisung Namensqualifikation unnötig, finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="171fb-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="171fb-115">Um eine Enumeration zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="171fb-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="171fb-116">Schreiben Sie eine Deklaration, die eine Codezugriffsebene enthält die `Enum` -Schlüsselwort verwenden und einen gültigen Namen ein, wie in den folgenden Beispielen, von denen jede ein anderes deklariert `Enum`.</span><span class="sxs-lookup"><span data-stu-id="171fb-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  <span data-ttu-id="171fb-117">Definieren Sie Konstanten in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="171fb-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="171fb-118">Standardmäßig wird das erste Konstante in einer Enumeration mit initialisiert `0`, und nachfolgende Konstanten mit einem Wert von mehr als die vorherigen Konstante initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="171fb-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="171fb-119">Z. B. die folgende Enumeration `Days`, enthält eine Konstante, die mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante, die mit dem Namen `Monday` mit dem Wert `1`, eine Konstante, die mit dem Namen `Tuesday` mit dem Wert des `2`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="171fb-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  <span data-ttu-id="171fb-120">Sie können Konstanten in einer Enumeration explizit Werte zuweisen, mithilfe einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="171fb-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="171fb-121">Sie können jeden ganzzahligen Wert, einschließlich negative Zahlen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="171fb-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="171fb-122">Beispielsweise sollten Sie die Konstanten Werte kleiner als 0 (null), um Fehlerzustände darstellen.</span><span class="sxs-lookup"><span data-stu-id="171fb-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="171fb-123">In der folgenden Enumeration gilt die Konstante `Invalid` der Wert explizit zugewiesen `–1`, und die Konstante `Sunday` der Wert zugewiesen `0`.</span><span class="sxs-lookup"><span data-stu-id="171fb-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="171fb-124">Da es das erste Konstante in der Enumeration ist `Saturday` ist auch auf den Wert initialisiert `0`.</span><span class="sxs-lookup"><span data-stu-id="171fb-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="171fb-125">Den Wert der `Monday` ist `1` (mehr als der Wert der `Sunday`); der Wert der `Tuesday` ist `2`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="171fb-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="171fb-126">Um eine Enumeration als einen expliziten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="171fb-126">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="171fb-127">Geben Sie den Typ der Enumeration mit den `As` -Klausel, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="171fb-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="171fb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="171fb-128">See Also</span></span>  
 [<span data-ttu-id="171fb-129">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="171fb-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="171fb-130">Gewusst wie: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="171fb-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="171fb-131">Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="171fb-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="171fb-132">Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="171fb-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="171fb-133">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="171fb-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="171fb-134">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="171fb-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="171fb-135">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="171fb-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="171fb-136">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="171fb-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
