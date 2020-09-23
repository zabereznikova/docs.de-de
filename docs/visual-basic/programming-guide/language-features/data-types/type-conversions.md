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
ms.openlocfilehash: ee8700ea757cee9c20e2598de029f54ae33a7114
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090156"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="bd8a2-102">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd8a2-102">Type Conversions in Visual Basic</span></span>

<span data-ttu-id="bd8a2-103">Der Prozess der Änderung eines Werts von einem Datentyp in einen anderen Typ wird als *Konvertierung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="bd8a2-104">Konvertierungen werden entweder *erweitert* oder einschränkend *, abhängig*von den Datenkapazitäten der beteiligten Typen.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="bd8a2-105">Sie sind auch *implizit* oder *explizit*, abhängig von der Syntax im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd8a2-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bd8a2-106">In This Section</span></span>  

 [<span data-ttu-id="bd8a2-107">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="bd8a2-107">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)  
 <span data-ttu-id="bd8a2-108">Erläutert Konvertierungen, die durch den Zieltyp klassifiziert werden, der die Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="bd8a2-109">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="bd8a2-109">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)  
 <span data-ttu-id="bd8a2-110">Erläutert Konvertierungen, die von der Visual Basic automatisch durchführt.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="bd8a2-111">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="bd8a2-111">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="bd8a2-112">Veranschaulicht die Typumwandlung zwischen Zeichen folgen und numerischen `Boolean` Werten, oder Datums-/Uhrzeitwerten.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="bd8a2-113">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd8a2-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="bd8a2-114">Zeigt, wie eine `Object` Variable in einen beliebigen anderen Datentyp konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="bd8a2-115">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="bd8a2-115">Array Conversions</span></span>](array-conversions.md)  
 <span data-ttu-id="bd8a2-116">Führt Sie schrittweise durch den Prozess der Typumwandlung zwischen Arrays verschiedener Datentypen.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bd8a2-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="bd8a2-117">Related Sections</span></span>  

 [<span data-ttu-id="bd8a2-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="bd8a2-118">Data Types</span></span>](index.md)  
 <span data-ttu-id="bd8a2-119">Führt die Visual Basic Datentypen ein und beschreibt, wie diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="bd8a2-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="bd8a2-120">Data Types</span></span>](../../../language-reference/data-types/index.md)  
 <span data-ttu-id="bd8a2-121">Listet die von Visual Basic bereitgestellten elementaren Datentypen auf.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="bd8a2-122">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="bd8a2-122">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)  
 <span data-ttu-id="bd8a2-123">Erläutert einige häufige Probleme, die bei der Arbeit mit Datentypen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="bd8a2-123">Discusses some common problems that can arise when working with data types.</span></span>
