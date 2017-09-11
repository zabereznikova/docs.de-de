---
title: Geben Sie in Visual Basic Konvertierungen | Microsoft-Dokumentation
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
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion
- conversions, data type
- changing data types
- data type conversion
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: 13
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
ms.openlocfilehash: 61606572dd1f10dc5df4ed4baec02f230a23c8d6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="dda65-102">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dda65-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="dda65-103">Einen Wert von einem Datentyp in einen anderen Typ umgewandelt wird bezeichnet *Konvertierung*.</span><span class="sxs-lookup"><span data-stu-id="dda65-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="dda65-104">Konvertierungen sind entweder *erweiternde* oder *einschränkende*, je nach Datenkapazität der betreffenden Typen.</span><span class="sxs-lookup"><span data-stu-id="dda65-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="dda65-105">Sie sind auch *implizite* oder *explizite*, abhängig von der Syntax im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="dda65-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dda65-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dda65-106">In This Section</span></span>  
 [<span data-ttu-id="dda65-107">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dda65-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="dda65-108">Erläutert die Konvertierungen klassifiziert, indem Sie, ob der Zieltyp der Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="dda65-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="dda65-109">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dda65-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="dda65-110">Erläutert Konvertierungen klassifiziert, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sie automatisch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dda65-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="dda65-111">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="dda65-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="dda65-112">Veranschaulicht die Konvertierung zwischen Zeichenfolgen und numerischen, `Boolean`, oder Datum/Uhrzeit-Werte.</span><span class="sxs-lookup"><span data-stu-id="dda65-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="dda65-113">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dda65-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="dda65-114">Veranschaulicht das Konvertieren einer `Object` -Variable auf einen anderen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="dda65-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="dda65-115">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="dda65-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="dda65-116">Führt Sie durch den Prozess der Konvertierung zwischen Arrays mit unterschiedlichen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="dda65-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dda65-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="dda65-117">Related Sections</span></span>  
 [<span data-ttu-id="dda65-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="dda65-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="dda65-119">Führt die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen und beschreibt deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="dda65-119">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="dda65-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="dda65-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="dda65-121">Listet die elementaren Datentypen von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="dda65-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 [<span data-ttu-id="dda65-122">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="dda65-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="dda65-123">Beschreibt einige allgemeine Probleme, die beim Arbeiten mit Datentypen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="dda65-123">Discusses some common problems that can arise when working with data types.</span></span>
