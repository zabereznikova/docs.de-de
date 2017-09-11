---
title: Datentypen in Visual Basic
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
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b90a5e58d135a3769761ca431fd0c05f79e045f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="data-types-in-visual-basic"></a><span data-ttu-id="df3d6-102">Datentypen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df3d6-102">Data Types in Visual Basic</span></span>
<span data-ttu-id="df3d6-103">Der *Datentyp* eines Programmierelements weist darauf hin, welche Art von Daten es enthalten kann, und wie es diese Daten speichert.</span><span class="sxs-lookup"><span data-stu-id="df3d6-103">The *data type* of a programming element refers to what kind of data it can hold and how it stores that data.</span></span> <span data-ttu-id="df3d6-104">Datentypen gelten für alle Werte, die im Arbeitsspeicher des Computers gespeichert werden oder an der Auswertung eines Ausdrucks teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="df3d6-104">Data types apply to all values that can be stored in computer memory or participate in the evaluation of an expression.</span></span> <span data-ttu-id="df3d6-105">Jeder Variablen-, Literal-, Konstanten-, Enumerations-, Eigenschafts-, Prozedurparameter-, Prozedurarguments- und Prozedurrückgabewert hat einen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="df3d6-105">Every variable, literal, constant, enumeration, property, procedure parameter, procedure argument, and procedure return value has a data type.</span></span>  
  
## <a name="declared-data-types"></a><span data-ttu-id="df3d6-106">Deklarierte Datentypen</span><span class="sxs-lookup"><span data-stu-id="df3d6-106">Declared Data Types</span></span>  
 <span data-ttu-id="df3d6-107">Sie definieren ein Programmierelement mit einer Deklarationsanweisung und geben seinen Datentyp mit der `As`-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="df3d6-107">You define a programming element with a declaration statement, and you specify its data type with the `As` clause.</span></span> <span data-ttu-id="df3d6-108">Die folgende Tabelle zeigt die Anweisungen, die Sie verwenden, um verschiedene Elemente zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="df3d6-108">The following table shows the statements you use to declare various elements.</span></span>  
  
|<span data-ttu-id="df3d6-109">Programmierelement</span><span class="sxs-lookup"><span data-stu-id="df3d6-109">Programming element</span></span>|<span data-ttu-id="df3d6-110">Datentypdeklaration</span><span class="sxs-lookup"><span data-stu-id="df3d6-110">Data type declaration</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="df3d6-111">Variable</span><span class="sxs-lookup"><span data-stu-id="df3d6-111">Variable</span></span>|<span data-ttu-id="df3d6-112">In einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-112">In a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)</span></span><br /><br /> <span data-ttu-id="df3d6-113">`Dim`   `amount As Double`</span><span class="sxs-lookup"><span data-stu-id="df3d6-113">`Dim`   `amount As Double`</span></span><br /><br /> <span data-ttu-id="df3d6-114">`Static`   `yourName As String`</span><span class="sxs-lookup"><span data-stu-id="df3d6-114">`Static`   `yourName As String`</span></span><br /><br /> <span data-ttu-id="df3d6-115">`Public`   `billsPaid As Decimal = 0`</span><span class="sxs-lookup"><span data-stu-id="df3d6-115">`Public`   `billsPaid As Decimal = 0`</span></span>|  
|<span data-ttu-id="df3d6-116">Literal</span><span class="sxs-lookup"><span data-stu-id="df3d6-116">Literal</span></span>|<span data-ttu-id="df3d6-117">Mit einem Literalzeichen; siehe „Literalzeichen“ in [Type Characters (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-117">With a literal type character; see "Literal Type Characters" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span><br /><br /> <span data-ttu-id="df3d6-118">`Dim searchChar As Char = "."`  `C`</span><span class="sxs-lookup"><span data-stu-id="df3d6-118">`Dim searchChar As Char = "."`  `C`</span></span>|  
|<span data-ttu-id="df3d6-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="df3d6-119">Constant</span></span>|<span data-ttu-id="df3d6-120">In einer [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-120">In a [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)</span></span><br /><br /> <span data-ttu-id="df3d6-121">`Const`   `modulus As Single = 4.17825F`</span><span class="sxs-lookup"><span data-stu-id="df3d6-121">`Const`   `modulus As Single = 4.17825F`</span></span>|  
|<span data-ttu-id="df3d6-122">Enumeration</span><span class="sxs-lookup"><span data-stu-id="df3d6-122">Enumeration</span></span>|<span data-ttu-id="df3d6-123">In einer [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-123">In an [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)</span></span><br /><br /> <span data-ttu-id="df3d6-124">`Public`   `Enum`   `colors`</span><span class="sxs-lookup"><span data-stu-id="df3d6-124">`Public`   `Enum`   `colors`</span></span>|  
|<span data-ttu-id="df3d6-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="df3d6-125">Property</span></span>|<span data-ttu-id="df3d6-126">In einer [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-126">In a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)</span></span><br /><br /> <span data-ttu-id="df3d6-127">`Property`   `region() As String`</span><span class="sxs-lookup"><span data-stu-id="df3d6-127">`Property`   `region() As String`</span></span>|  
|<span data-ttu-id="df3d6-128">Prozedurparameter</span><span class="sxs-lookup"><span data-stu-id="df3d6-128">Procedure parameter</span></span>|<span data-ttu-id="df3d6-129">In einer [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) oder [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-129">In a [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md), or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="df3d6-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span><span class="sxs-lookup"><span data-stu-id="df3d6-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span></span>|  
|<span data-ttu-id="df3d6-131">Prozedurargument</span><span class="sxs-lookup"><span data-stu-id="df3d6-131">Procedure argument</span></span>|<span data-ttu-id="df3d6-132">Im aufrufenden Code; jedes Argument ist ein Programmierelement, das bereits deklariert wurde, oder ein deklarierte Elemente enthaltender Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="df3d6-132">In the calling code; each argument is a programming element that has already been declared, or an expression containing declared elements</span></span><br /><br /> <span data-ttu-id="df3d6-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span><span class="sxs-lookup"><span data-stu-id="df3d6-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span></span>|  
|<span data-ttu-id="df3d6-134">Prozedurrückgabewert</span><span class="sxs-lookup"><span data-stu-id="df3d6-134">Procedure return value</span></span>|<span data-ttu-id="df3d6-135">In einer [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) oder [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="df3d6-135">In a [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="df3d6-136">`Function convert(ByVal b As Byte)`   `As String`</span><span class="sxs-lookup"><span data-stu-id="df3d6-136">`Function convert(ByVal b As Byte)`   `As String`</span></span>|  
  
 <span data-ttu-id="df3d6-137">Eine Liste der Visual Basic-Datentypen finden Sie unter [Data Type Summary (Visual Basic)](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="df3d6-137">For a list of Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3d6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df3d6-138">See Also</span></span>  
 <span data-ttu-id="df3d6-139">[Type Characters (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-139">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
 <span data-ttu-id="df3d6-140">[Elementary Data Types (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-140">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
 <span data-ttu-id="df3d6-141">[Composite Data Types (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-141">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
 <span data-ttu-id="df3d6-142">[Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-142">[Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
 <span data-ttu-id="df3d6-143">[Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-143">[Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
 <span data-ttu-id="df3d6-144">[Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-144">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
 <span data-ttu-id="df3d6-145">[Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-145">[Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
 <span data-ttu-id="df3d6-146">[Tupel](tuples.md)   </span><span class="sxs-lookup"><span data-stu-id="df3d6-146">[Tuples](tuples.md)   </span></span>  
 <span data-ttu-id="df3d6-147">[Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-147">[Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
 <span data-ttu-id="df3d6-148">[Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="df3d6-148">[Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
 [<span data-ttu-id="df3d6-149">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="df3d6-149">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

