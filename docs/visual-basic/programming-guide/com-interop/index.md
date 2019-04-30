---
title: COM-Interop (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
ms.openlocfilehash: dfd256fa7ccd8f089fab6eb1d42579deb2c4a64d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022414"
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="a15e5-102">COM-Interop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a15e5-102">COM Interop (Visual Basic)</span></span>
<span data-ttu-id="a15e5-103">Das Component Object Model (COM) erlaubt einem Objekt, seine Funktionen für andere Komponenten und Hostanwendungen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="a15e5-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="a15e5-104">Die moderne Software enthält in der Regel COM-Objekte.</span><span class="sxs-lookup"><span data-stu-id="a15e5-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="a15e5-105">Obwohl .NET-Assemblys die beste Wahl für neue Anwendungen sind, müssen Sie von Zeit zu Zeit COM-Objekte nutzen.</span><span class="sxs-lookup"><span data-stu-id="a15e5-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="a15e5-106">In diesem Abschnitt werden einige der Probleme im Zusammenhang mit dem Erstellen und Verwenden von COM-Objekte mit Visual Basic behandelt.</span><span class="sxs-lookup"><span data-stu-id="a15e5-106">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a15e5-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a15e5-107">In This Section</span></span>  
 [<span data-ttu-id="a15e5-108">Einführung in COM-Interop</span><span class="sxs-lookup"><span data-stu-id="a15e5-108">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 <span data-ttu-id="a15e5-109">Stellt eine Übersicht der COM-Interoperabilität bereit.</span><span class="sxs-lookup"><span data-stu-id="a15e5-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="a15e5-110">Vorgehensweise: COM-Verweisobjekte aus Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a15e5-110">How to: Reference COM Objects from Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-reference-com-objects.md)  
 <span data-ttu-id="a15e5-111">Beschreibt, wie COM-Objekten Verweise hinzugefügt werden, die über Typbibliotheken verfügen.</span><span class="sxs-lookup"><span data-stu-id="a15e5-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="a15e5-112">Vorgehensweise: Arbeiten mit ActiveX-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a15e5-112">How to: Work with ActiveX Controls</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 <span data-ttu-id="a15e5-113">Veranschaulicht, wie vorhandene ActiveX-Steuerelemente zum Visual Studio-Toolbox hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a15e5-113">Demonstrates how to use existing ActiveX controls to add features to the Visual Studio Toolbox.</span></span>  
  
 [<span data-ttu-id="a15e5-114">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="a15e5-114">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="a15e5-115">Führt Sie durch den Prozess, APIs aufzurufen, die Teil des Windows-Betriebssystems sind.</span><span class="sxs-lookup"><span data-stu-id="a15e5-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="a15e5-116">Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="a15e5-116">How to: Call Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 <span data-ttu-id="a15e5-117">Veranschaulicht, wie die `MessageBox`-Funktion in User32.dll definiert und aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a15e5-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="a15e5-118">Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="a15e5-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="a15e5-119">Veranschaulicht, wie eine Windows-Funktion aufgerufen wird, die über einen Parameter eines unsignierten Typs verfügt.</span><span class="sxs-lookup"><span data-stu-id="a15e5-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="a15e5-120">Exemplarische Vorgehensweise: Erstellen von COM-Objekte in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a15e5-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 <span data-ttu-id="a15e5-121">Führt Sie durch den Prozess zum Erstellen von COM-Objekten mit und ohne die COM-Klassenvorlage.</span><span class="sxs-lookup"><span data-stu-id="a15e5-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="a15e5-122">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="a15e5-122">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 <span data-ttu-id="a15e5-123">Behandelt einige Probleme, die bei der Verwendung von COM auftreten können.</span><span class="sxs-lookup"><span data-stu-id="a15e5-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="a15e5-124">COM-Interoperabilität in .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a15e5-124">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="a15e5-125">Bietet eine Übersicht, wie COM-Objekte und .NET Framework-Objekte in derselben Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a15e5-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="a15e5-126">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="a15e5-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="a15e5-127">Beschreibt die Verwendung vorhandener COM-Objekte als Grundlage für neue Objekte.</span><span class="sxs-lookup"><span data-stu-id="a15e5-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a15e5-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a15e5-128">Related Sections</span></span>  
 [<span data-ttu-id="a15e5-129">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="a15e5-129">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="a15e5-130">Beschreibt Interoperabilitätsdienste, die von der Common Language Runtime bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a15e5-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="a15e5-131">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a15e5-131">Exposing COM Components to the .NET Framework</span></span>](../../../framework/interop/exposing-com-components.md)  
 <span data-ttu-id="a15e5-132">Beschreibt den Prozess, wie COM-Typen über COM-Interop aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a15e5-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="a15e5-133">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="a15e5-133">Exposing .NET Framework Components to COM</span></span>](../../../framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="a15e5-134">Beschreibt die Vorbereitung und Verwendung von verwalteten Typen von COM.</span><span class="sxs-lookup"><span data-stu-id="a15e5-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="a15e5-135">Anwenden von Interop-Attributen</span><span class="sxs-lookup"><span data-stu-id="a15e5-135">Applying Interop Attributes</span></span>](../../../framework/interop/applying-interop-attributes.md)  
 <span data-ttu-id="a15e5-136">Behandelt Attribute, die Sie verwenden können, wenn Sie mit nicht verwaltetem Code arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a15e5-136">Covers attributes you can use when working with unmanaged code.</span></span>
