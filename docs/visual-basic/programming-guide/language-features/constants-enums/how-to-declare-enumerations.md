---
title: 'Gewusst wie: Deklarieren einer Enumeration (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7adaca7e7252ce7165a5fd27b5bc9c049388206c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="0cd4c-102">Gewusst wie: Deklarieren einer Enumeration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="0cd4c-103">Sie erstellen eine Enumeration mit den `Enum` -Anweisung im Deklarationsabschnitt einer Klasse oder eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="0cd4c-104">Sie können eine Enumeration innerhalb einer Methode nicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="0cd4c-105">Verwenden Sie zum Angeben der entsprechenden Ebene des Zugriffs `Private`, `Protected`, `Friend`, oder `Public`.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="0cd4c-106">Ein `Enum` Typ hat einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, von denen jedes eine Konstante darstellt.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="0cd4c-107">Der Name muss ein gültiger [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-107">The name must be a valid [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] qualifier.</span></span> <span data-ttu-id="0cd4c-108">Der zugrunde liegende Typ muss einen ganzzahligen Typ –`Byte`, `Short`, `Long` oder `Integer`.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="0cd4c-109">Standardmäßig ist `Integer` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-109">`Integer` is the default.</span></span> <span data-ttu-id="0cd4c-110">Enumerationen sind immer stark typisiert und nicht mit Ganzzahltypen austauschbar.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="0cd4c-111">Enumerationen können keine Gleitkommawerte haben.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="0cd4c-112">Wenn eine Enumeration einen Gleitkommawert zugewiesen ist `Option Strict On`, ein Compilerfehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="0cd4c-113">Wenn `Option Strict` ist `Off`, der Wert wird automatisch konvertiert, um die `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="0cd4c-114">Informationen zu Namen und Gewusst wie: Verwenden der `Imports` Anweisung, damit Namensqualifikation unnötig, finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="0cd4c-115">Um eine Enumeration zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="0cd4c-116">Schreiben Sie eine Deklaration, die eine Ebene, enthält die `Enum` -Schlüsselwort und einen gültigen Namen, wie in den folgenden Beispielen wird jeweils ein anderes deklariert `Enum`.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     <span data-ttu-id="0cd4c-117">[!code-vb[VbEnumsTask&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0cd4c-117">[!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span></span>  
  
2.  <span data-ttu-id="0cd4c-118">Definieren Sie die Konstanten in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-118">Define the constants in the enumeration.</span></span> <span data-ttu-id="0cd4c-119">Standardmäßig wird die erste Konstante in einer Enumeration mit initialisiert `0`, und alle nachfolgenden Konstanten Wert eins mehr als die vorherigen Konstante initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-119">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="0cd4c-120">Z. B. die folgende Enumeration `Days`, enthält eine Konstante mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante mit dem Namen `Monday` mit dem Wert `1`, eine Konstante mit dem Namen `Tuesday` mit dem Wert des `2`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-120">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     <span data-ttu-id="0cd4c-121">[!code-vb[VbEnumsTask&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0cd4c-121">[!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span></span>  
  
3.  <span data-ttu-id="0cd4c-122">Sie können Konstanten in einer Enumeration explizit Werte zuweisen, mit der eine Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-122">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="0cd4c-123">Sie können eine beliebige Ganzzahl auch negative Zahlen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-123">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="0cd4c-124">Beispielsweise sollten Sie die Konstanten Werte kleiner als&0; (null), um Fehlerzustände darstellen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-124">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="0cd4c-125">In der folgenden Enumeration, die Konstante `Invalid` der Wert explizit zugewiesen `–1`, und die Konstante `Sunday` erhält den Wert `0`.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-125">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="0cd4c-126">Da es sich um die erste Konstante in der Enumeration ist `Saturday` wird auch auf den Wert initialisiert `0`.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-126">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="0cd4c-127">Der Wert der `Monday` ist `1` (eins höher ist als der Wert der `Sunday`); der Wert der `Tuesday` ist `2`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-127">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     <span data-ttu-id="0cd4c-128">[!code-vb[VbEnumsTask&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0cd4c-128">[!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span></span>  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="0cd4c-129">Um eine Enumeration als expliziten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-129">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="0cd4c-130">Geben Sie den Typ der Enumeration mit der `As` -Klausel, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-130">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     <span data-ttu-id="0cd4c-131">[!code-vb[VbEnumsTask&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0cd4c-131">[!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd4c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cd4c-132">See Also</span></span>  
 <span data-ttu-id="0cd4c-133">[Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-133">[Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="0cd4c-134"> [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-134"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="0cd4c-135"> [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-135"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="0cd4c-136"> [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-136"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="0cd4c-137"> [Verwenden Sie eine Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-137"> [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span></span>  
<span data-ttu-id="0cd4c-138"> [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-138"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="0cd4c-139"> [Konstanten und Literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0cd4c-139"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="0cd4c-140"> [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-140"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
