---
title: Typkonvertierungen
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
ms.openlocfilehash: fbf0c9877cf9a9b4364c8c058c61e847ad7bf049
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348724"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="27645-102">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27645-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="27645-103">Der Prozess der Änderung eines Werts von einem Datentyp in einen anderen Typ wird als *Konvertierung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="27645-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="27645-104">Konvertierungen werden entweder *erweitert* oder einschränkend *, abhängig*von den Datenkapazitäten der beteiligten Typen.</span><span class="sxs-lookup"><span data-stu-id="27645-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="27645-105">Sie sind auch *implizit* oder *explizit*, abhängig von der Syntax im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="27645-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27645-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="27645-106">In This Section</span></span>  
 [<span data-ttu-id="27645-107">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="27645-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="27645-108">Erläutert Konvertierungen, die durch den Zieltyp klassifiziert werden, der die Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="27645-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="27645-109">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="27645-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="27645-110">Erläutert Konvertierungen, die von der Visual Basic automatisch durchführt.</span><span class="sxs-lookup"><span data-stu-id="27645-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="27645-111">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="27645-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="27645-112">Veranschaulicht die Typumwandlung zwischen Zeichen folgen und numerischen Werten, `Boolean`oder Datums-/Uhrzeitwerten.</span><span class="sxs-lookup"><span data-stu-id="27645-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="27645-113">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27645-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="27645-114">Zeigt, wie eine `Object` Variable in einen beliebigen anderen Datentyp konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="27645-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="27645-115">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="27645-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="27645-116">Führt Sie schrittweise durch den Prozess der Typumwandlung zwischen Arrays verschiedener Datentypen.</span><span class="sxs-lookup"><span data-stu-id="27645-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="27645-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="27645-117">Related Sections</span></span>  
 [<span data-ttu-id="27645-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="27645-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="27645-119">Führt die Visual Basic Datentypen ein und beschreibt, wie diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27645-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="27645-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="27645-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="27645-121">Listet die von Visual Basic bereitgestellten elementaren Datentypen auf.</span><span class="sxs-lookup"><span data-stu-id="27645-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="27645-122">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="27645-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="27645-123">Erläutert einige häufige Probleme, die bei der Arbeit mit Datentypen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="27645-123">Discusses some common problems that can arise when working with data types.</span></span>
