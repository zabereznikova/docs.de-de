---
title: 'Vorgehensweise: Definieren eines Konvertierungsoperators'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 53b0211c6304625edd7ac24fa52ff0c051d8f0a0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388088"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="0e914-102">Gewusst wie: Definieren eines Konvertierungsoperators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e914-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="0e914-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Typkonvertierungs Operator zwischen dem Typ der Klasse oder Struktur und einem anderen Datentyp (z `Integer` . b `Double` ., oder `String` ) definieren.</span><span class="sxs-lookup"><span data-stu-id="0e914-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="0e914-104">Definieren Sie die Typkonvertierung als [CType-Funktions](../../../language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="0e914-104">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="0e914-105">Alle Konvertierungs Prozeduren müssen sein `Public Shared` , und jeder muss entweder eine [Erweiterung](../../../language-reference/modifiers/widening.md) oder eine [Einschränkung](../../../language-reference/modifiers/narrowing.md)angeben.</span><span class="sxs-lookup"><span data-stu-id="0e914-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="0e914-106">Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e914-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e914-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e914-107">Example</span></span>  
 <span data-ttu-id="0e914-108">Im folgenden Beispiel werden Konvertierungs Operatoren zwischen einer Struktur mit `digit` dem Namen und einer definiert `Byte` .</span><span class="sxs-lookup"><span data-stu-id="0e914-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="0e914-109">Sie können die Struktur `digit` mit dem folgenden Code testen.</span><span class="sxs-lookup"><span data-stu-id="0e914-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="0e914-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e914-110">See also</span></span>

- [<span data-ttu-id="0e914-111">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="0e914-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0e914-112">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="0e914-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="0e914-113">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="0e914-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="0e914-114">Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="0e914-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="0e914-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0e914-115">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="0e914-116">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="0e914-116">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0e914-117">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="0e914-117">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="0e914-118">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0e914-118">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="0e914-119">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="0e914-119">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
