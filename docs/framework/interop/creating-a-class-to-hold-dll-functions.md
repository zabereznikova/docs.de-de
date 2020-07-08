---
title: Erstellen einer Klasse zum Halten von DLL-Funktionen
description: Erstellen Sie in .NET einen Wrapper für verwaltete Klassen zur Aufnahme von DLL-Funktionen, mit dessen Hilfe Plattformfunktionalität gekapselt werden kann.
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
ms.openlocfilehash: b8aa0361ee5213cb947a102f903d1a7a35331f17
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622171"
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="d3939-103">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3939-103">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="d3939-104">Das Umschließen einer häufig verwendeten DLL-Funktion in einer verwalteten Klasse ist als effektiver Ansatz zu verstehen, Plattformfunktionen zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="d3939-104">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="d3939-105">Obwohl es nicht in jedem Fall erforderlich ist, können Sie mithilfe von Klassenwrappern DLL-Funktionen mit weniger Aufwand und geringerer Fehleranfälligkeit definieren.</span><span class="sxs-lookup"><span data-stu-id="d3939-105">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="d3939-106">Wenn Sie in Visual Basic oder C# programmieren, müssen Sie die DLL-Funktionen innerhalb einer Klasse oder eines Visual Basic-Moduls deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d3939-106">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="d3939-107">Innerhalb einer Klasse definieren Sie eine statische Methode für jede DLL-Funktion, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d3939-107">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="d3939-108">Die Definition kann zusätzliche Informationen wie den Zeichensatz oder die Aufrufkonvention, die bei der Übergabe von Methodenargumenten verwendet wird, enthalten; werden diese Informationen weggelassen, werden die Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3939-108">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="d3939-109">Eine vollständige Liste der Deklarationsoptionen und deren Standardeinstellungen finden Sie unter [Erstellen von Prototypen in verwaltetem Code](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="d3939-109">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="d3939-110">Sobald sie umschlossen sind, können Sie die Methoden für die Klasse wie für jede andere Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d3939-110">Once wrapped, you can call the methods on the class as you call static methods on any other class.</span></span> <span data-ttu-id="d3939-111">Der Plattformaufruf behandelt automatisch die zugrunde liegenden exportierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d3939-111">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="d3939-112">Beim Entwurf einer verwalteten Klasse für Plattformaufruf, beachten Sie die Beziehungen zwischen Klassen und DLL-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d3939-112">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="d3939-113">Sie haben unter anderem folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="d3939-113">For example, you can:</span></span>  
  
- <span data-ttu-id="d3939-114">Deklarieren von DLL-Funktionen innerhalb einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="d3939-114">Declare DLL functions within an existing class.</span></span>  
  
- <span data-ttu-id="d3939-115">Erstellen Sie eine einzelne Klasse für jede DLL-Funktion, indem Funktionen isoliert und leicht auffindbar bleiben.</span><span class="sxs-lookup"><span data-stu-id="d3939-115">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
- <span data-ttu-id="d3939-116">Erstellen Sie eine Klasse für eine Gruppe von verwandten DLL-Funktionen, um logische Gruppierungen zu bilden und den Verwaltungsaufwand zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="d3939-116">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="d3939-117">Sie können die Klasse und ihre Methoden beliebig benennen.</span><span class="sxs-lookup"><span data-stu-id="d3939-117">You can name the class and its methods as you please.</span></span> <span data-ttu-id="d3939-118">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="d3939-118">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3939-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3939-119">See also</span></span>

- [<span data-ttu-id="d3939-120">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3939-120">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="d3939-121">Identifizieren von Funktionen in DLLs</span><span class="sxs-lookup"><span data-stu-id="d3939-121">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="d3939-122">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="d3939-122">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="d3939-123">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="d3939-123">Calling a DLL Function</span></span>](calling-a-dll-function.md)
