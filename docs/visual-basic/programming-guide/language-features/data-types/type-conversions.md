---
title: Typkonvertierung in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b46d813b4fcadd975d87b235e9f3350a365949fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="ff2da-102">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff2da-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="ff2da-103">Der Prozess zum Ändern eines Werts von einem Datentyp in einen anderen Typ wird aufgerufen, *Konvertierung*.</span><span class="sxs-lookup"><span data-stu-id="ff2da-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="ff2da-104">Konvertierungen sind entweder *erweiternde* oder *einschränkende*, abhängig von der Datenkapazität der beteiligten Typen.</span><span class="sxs-lookup"><span data-stu-id="ff2da-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="ff2da-105">Außerdem sind Sie *implizite* oder *explizite*, abhängig von der Syntax in den Quellcode einfügen.</span><span class="sxs-lookup"><span data-stu-id="ff2da-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff2da-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ff2da-106">In This Section</span></span>  
 [<span data-ttu-id="ff2da-107">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ff2da-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="ff2da-108">Erläutert die Konvertierungen klassifiziert, indem Sie, ob der Zieltyp für die Daten aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="ff2da-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="ff2da-109">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ff2da-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="ff2da-110">Erläutert die Konvertierungen von, ob das Geschäft klassifiziert [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sie automatisch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ff2da-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="ff2da-111">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="ff2da-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="ff2da-112">Konvertieren zwischen Zeichenfolgen und numerische, veranschaulicht `Boolean`, oder Datum/Uhrzeit-Werte.</span><span class="sxs-lookup"><span data-stu-id="ff2da-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="ff2da-113">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff2da-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="ff2da-114">Zeigt, wie das Konvertieren einer `Object` -Variable auf einen anderen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ff2da-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="ff2da-115">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ff2da-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="ff2da-116">Führt Sie durch den Prozess der Konvertierung zwischen Arrays mit unterschiedlichen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="ff2da-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ff2da-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ff2da-117">Related Sections</span></span>  
 [<span data-ttu-id="ff2da-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ff2da-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="ff2da-119">Führt die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Datentypen und beschreibt deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ff2da-119">Introduces the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="ff2da-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ff2da-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="ff2da-121">Listet die elementare Datentypen von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff2da-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="ff2da-122">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="ff2da-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="ff2da-123">Beschreibt einige allgemeine Probleme, die beim Arbeiten mit Datentypen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="ff2da-123">Discusses some common problems that can arise when working with data types.</span></span>
