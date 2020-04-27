---
title: Erstellen einer Klasse zum Halten von DLL-Funktionen
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
ms.openlocfilehash: 765d4344553a6e65b930a7bf586a41144d220fc6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123625"
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="bdf39-102">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="bdf39-102">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="bdf39-103">Das Umschließen einer häufig verwendeten DLL-Funktion in einer verwalteten Klasse ist als effektiver Ansatz zu verstehen, Plattformfunktionen zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="bdf39-103">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="bdf39-104">Obwohl es nicht in jedem Fall erforderlich ist, können Sie mithilfe von Klassenwrappern DLL-Funktionen mit weniger Aufwand und geringerer Fehleranfälligkeit definieren.</span><span class="sxs-lookup"><span data-stu-id="bdf39-104">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="bdf39-105">Wenn Sie in Visual Basic oder C# programmieren, müssen Sie die DLL-Funktionen innerhalb einer Klasse oder eines Visual Basic-Moduls deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bdf39-105">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="bdf39-106">Innerhalb einer Klasse definieren Sie eine statische Methode für jede DLL-Funktion, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="bdf39-106">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="bdf39-107">Die Definition kann zusätzliche Informationen wie den Zeichensatz oder die Aufrufkonvention, die bei der Übergabe von Methodenargumenten verwendet wird, enthalten; werden diese Informationen weggelassen, werden die Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bdf39-107">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="bdf39-108">Eine vollständige Liste der Deklarationsoptionen und deren Standardeinstellungen finden Sie unter [Erstellen von Prototypen in verwaltetem Code](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="bdf39-108">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="bdf39-109">Sobald sie umschlossen sind, können Sie die Methoden für die Klasse wie für jede andere Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bdf39-109">Once wrapped, you can call the methods on the class as you call static methods on any other class.</span></span> <span data-ttu-id="bdf39-110">Der Plattformaufruf behandelt automatisch die zugrunde liegenden exportierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bdf39-110">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="bdf39-111">Beim Entwurf einer verwalteten Klasse für Plattformaufruf, beachten Sie die Beziehungen zwischen Klassen und DLL-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bdf39-111">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="bdf39-112">Sie haben unter anderem folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="bdf39-112">For example, you can:</span></span>  
  
- <span data-ttu-id="bdf39-113">Deklarieren von DLL-Funktionen innerhalb einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="bdf39-113">Declare DLL functions within an existing class.</span></span>  
  
- <span data-ttu-id="bdf39-114">Erstellen Sie eine einzelne Klasse für jede DLL-Funktion, indem Funktionen isoliert und leicht auffindbar bleiben.</span><span class="sxs-lookup"><span data-stu-id="bdf39-114">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
- <span data-ttu-id="bdf39-115">Erstellen Sie eine Klasse für eine Gruppe von verwandten DLL-Funktionen, um logische Gruppierungen zu bilden und den Verwaltungsaufwand zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="bdf39-115">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="bdf39-116">Sie können die Klasse und ihre Methoden beliebig benennen.</span><span class="sxs-lookup"><span data-stu-id="bdf39-116">You can name the class and its methods as you please.</span></span> <span data-ttu-id="bdf39-117">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="bdf39-117">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf39-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdf39-118">See also</span></span>

- [<span data-ttu-id="bdf39-119">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="bdf39-119">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="bdf39-120">Identifizieren von Funktionen in DLLs</span><span class="sxs-lookup"><span data-stu-id="bdf39-120">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="bdf39-121">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="bdf39-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="bdf39-122">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="bdf39-122">Calling a DLL Function</span></span>](calling-a-dll-function.md)
