---
title: Strukturen (Visual Basic) | Microsoft-Dokumentation
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
- structures
- user-defined data types, structures
- user-defined types, about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types, about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
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
ms.openlocfilehash: d1ba8671af9ff6d50499149fce6d55b3db78ffe0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="structures-visual-basic"></a><span data-ttu-id="ddf3c-102">Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddf3c-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="ddf3c-103">Ein *Struktur* ist eine Verallgemeinerung des benutzerdefinierten Typs (UDT) unterstützt, die von früheren Versionen von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddf3c-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="ddf3c-104">Zusätzlich zu Feldern können Strukturen Eigenschaften, Methoden und Ereignisse verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="ddf3c-105">Eine Struktur kann eine oder mehrere Schnittstellen implementieren, und Sie können individuelle Zugriffsebenen für die einzelnen Felder deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="ddf3c-106">Sie können Datenelemente verschiedener Typen erstellen eine Struktur kombinieren.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="ddf3c-107">In einer Struktur zugeordnet wird, eine oder mehrere *Elemente* untereinander und mit der Struktur selbst.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="ddf3c-108">Wenn Sie eine Struktur zu deklarieren, es wird ein *zusammengesetzten Datentyp*, und Sie können Variablen dieses Typs deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="ddf3c-109">Strukturen sind hilfreich, wenn Sie eine einzelne Variable verschiedene verwandte Informationen enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="ddf3c-110">Sie möchten z. B. Name, Durchwahl und Gehalt des Mitarbeiters zusammenzuhalten.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="ddf3c-111">Können Sie mehrere Variablen für diese Informationen, oder Sie können eine Struktur definieren und verwenden sie für eine Variable für die einzelnen Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="ddf3c-112">Der Vorteil der Struktur wird offensichtlich, wenn Sie viele Mitarbeiter und somit auch viele Instanzen der Variablen verfügen.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddf3c-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ddf3c-113">In This Section</span></span>  
 [<span data-ttu-id="ddf3c-114">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="ddf3c-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="ddf3c-115">Zeigt, wie eine Struktur und seine Elemente deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="ddf3c-116">Strukturvariablen</span><span class="sxs-lookup"><span data-stu-id="ddf3c-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="ddf3c-117">Erläutert das Zuweisen einer Struktur zu einer Variablen und den Zugriff auf die Elemente.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="ddf3c-118">Strukturen und andere Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="ddf3c-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="ddf3c-119">Fasst zusammen, wie Strukturen mit Arrays, Objekten, Prozeduren und miteinander interagieren.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="ddf3c-120">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="ddf3c-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="ddf3c-121">Beschreibt die ähnlichkeiten und Unterschiede zwischen Strukturen und Klassen.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ddf3c-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ddf3c-122">Related Sections</span></span>  
 [<span data-ttu-id="ddf3c-123">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ddf3c-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="ddf3c-124">Führt die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen und beschreibt deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-124">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="ddf3c-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ddf3c-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="ddf3c-126">Listet die elementaren Datentypen von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddf3c-126">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>
