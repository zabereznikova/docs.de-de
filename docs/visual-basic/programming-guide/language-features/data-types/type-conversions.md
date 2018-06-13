---
title: Typkonvertierung in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: 7f1a571cda4f68222c5c03c3a8fe31c29eafd8c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647195"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="ebc13-102">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebc13-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="ebc13-103">Der Prozess zum Ändern eines Werts von einem Datentyp in einen anderen Typ wird aufgerufen, *Konvertierung*.</span><span class="sxs-lookup"><span data-stu-id="ebc13-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="ebc13-104">Konvertierungen sind entweder *erweiternde* oder *einschränkende*, abhängig von der Datenkapazität der beteiligten Typen.</span><span class="sxs-lookup"><span data-stu-id="ebc13-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="ebc13-105">Außerdem sind Sie *implizite* oder *explizite*, abhängig von der Syntax in den Quellcode einfügen.</span><span class="sxs-lookup"><span data-stu-id="ebc13-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebc13-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ebc13-106">In This Section</span></span>  
 [<span data-ttu-id="ebc13-107">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ebc13-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="ebc13-108">Erläutert die Konvertierungen klassifiziert, indem Sie, ob der Zieltyp für die Daten aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="ebc13-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="ebc13-109">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ebc13-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="ebc13-110">Erläutert die Konvertierungen, die klassifiziert, indem Sie, ob Visual Basic automatisch ausführt.</span><span class="sxs-lookup"><span data-stu-id="ebc13-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="ebc13-111">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="ebc13-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="ebc13-112">Konvertieren zwischen Zeichenfolgen und numerische, veranschaulicht `Boolean`, oder Datum/Uhrzeit-Werte.</span><span class="sxs-lookup"><span data-stu-id="ebc13-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="ebc13-113">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebc13-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="ebc13-114">Zeigt, wie das Konvertieren einer `Object` -Variable auf einen anderen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ebc13-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="ebc13-115">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ebc13-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="ebc13-116">Führt Sie durch den Prozess der Konvertierung zwischen Arrays mit unterschiedlichen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="ebc13-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ebc13-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ebc13-117">Related Sections</span></span>  
 [<span data-ttu-id="ebc13-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ebc13-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="ebc13-119">Führt das Visual Basic-Datentypen und beschreibt deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ebc13-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="ebc13-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ebc13-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="ebc13-121">Listet die elementaren Datentypen von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ebc13-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="ebc13-122">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="ebc13-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="ebc13-123">Beschreibt einige allgemeine Probleme, die beim Arbeiten mit Datentypen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="ebc13-123">Discusses some common problems that can arise when working with data types.</span></span>
