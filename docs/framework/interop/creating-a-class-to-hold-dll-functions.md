---
title: Erstellen einer Klasse zum Halten von DLL-Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d64034f8059dc094b3fc8a71c6a2b7e96fe8d89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="4453e-102">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="4453e-102">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="4453e-103">Das Umschließen einer häufig verwendeten DLL-Funktion in einer verwalteten Klasse ist als effektiver Ansatz zu verstehen, Plattformfunktionen zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="4453e-103">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="4453e-104">Obwohl es nicht in jedem Fall erforderlich ist, können Sie mithilfe von Klassenwrappern DLL-Funktionen mit weniger Aufwand und geringerer Fehleranfälligkeit definieren.</span><span class="sxs-lookup"><span data-stu-id="4453e-104">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="4453e-105">Wenn Sie in Visual Basic oder C# programmieren, müssen Sie die DLL-Funktionen innerhalb einer Klasse oder eines Visual Basic-Moduls deklarieren.</span><span class="sxs-lookup"><span data-stu-id="4453e-105">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="4453e-106">Innerhalb einer Klasse definieren Sie eine statische Methode für jede DLL-Funktion, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="4453e-106">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="4453e-107">Die Definition kann zusätzliche Informationen wie den Zeichensatz oder die Aufrufkonvention, die bei der Übergabe von Methodenargumenten verwendet wird, enthalten; werden diese Informationen weggelassen, werden die Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4453e-107">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="4453e-108">Eine vollständige Liste der Deklarationsoptionen und deren Standardeinstellungen finden Sie unter [Erstellen von Prototypen in verwaltetem Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="4453e-108">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="4453e-109">Sobald eine Funktion umschlossen ist, können Sie Methoden für die Funktion wie für jede andere statische Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4453e-109">Once wrapped, you can call methods on the function as you call methods on any other static function.</span></span> <span data-ttu-id="4453e-110">Der Plattformaufruf behandelt automatisch die zugrunde liegenden exportierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4453e-110">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="4453e-111">Beim Entwurf einer verwalteten Klasse für Plattformaufruf, beachten Sie die Beziehungen zwischen Klassen und DLL-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4453e-111">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="4453e-112">Sie haben unter anderem folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="4453e-112">For example, you can:</span></span>  
  
-   <span data-ttu-id="4453e-113">Deklarieren von DLL-Funktionen innerhalb einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="4453e-113">Declare DLL functions within an existing class.</span></span>  
  
-   <span data-ttu-id="4453e-114">Erstellen Sie eine einzelne Klasse für jede DLL-Funktion, indem Funktionen isoliert und leicht auffindbar bleiben.</span><span class="sxs-lookup"><span data-stu-id="4453e-114">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
-   <span data-ttu-id="4453e-115">Erstellen Sie eine Klasse für eine Gruppe von verwandten DLL-Funktionen, um logische Gruppierungen zu bilden und den Verwaltungsaufwand zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="4453e-115">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="4453e-116">Sie können die Klasse und ihre Methoden beliebig benennen.</span><span class="sxs-lookup"><span data-stu-id="4453e-116">You can name the class and its methods as you please.</span></span> <span data-ttu-id="4453e-117">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="4453e-117">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4453e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4453e-118">See Also</span></span>  
 [<span data-ttu-id="4453e-119">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="4453e-119">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="4453e-120">Identifizieren von Funktionen in DLLs</span><span class="sxs-lookup"><span data-stu-id="4453e-120">Identifying Functions in DLLs</span></span>](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [<span data-ttu-id="4453e-121">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="4453e-121">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="4453e-122">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="4453e-122">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
