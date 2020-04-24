---
title: Verfügbarmachen von .NET Core-Komponenten in COM
description: In diesem Tutorial erfahren Sie, wie Sie eine Klasse für COM aus .NET Core freigeben. Sie generieren einen COM-Server und ein paralleles Servermanifest für COM ohne Registrierung.
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 17d85b9e9734fae0bb69f94da8c08669216ab0ae
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242867"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="aa0f8-104">Verfügbarmachen von .NET Core-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="aa0f8-104">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="aa0f8-105">In .NET Core wurde das Verfügbarmachen von .NET-Objekten für COM im Vergleich zum .NET Framework deutlich optimiert.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-105">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="aa0f8-106">Im Folgenden wird erläutert, wie Sie eine Klasse für COM verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-106">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="aa0f8-107">In diesem Tutorial lernen Sie:</span><span class="sxs-lookup"><span data-stu-id="aa0f8-107">This tutorial shows you how to:</span></span>

- <span data-ttu-id="aa0f8-108">Verfügbarmachen einer Klasse für COM in .NET Core</span><span class="sxs-lookup"><span data-stu-id="aa0f8-108">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="aa0f8-109">Generieren eines COM-Servers bei der Erstellung einer .NET Core-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="aa0f8-109">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="aa0f8-110">Automatisches Generieren eines Manifests zur parallelen Serverausführung ohne COM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="aa0f8-110">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa0f8-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="aa0f8-111">Prerequisites</span></span>

- <span data-ttu-id="aa0f8-112">Installieren Sie [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-112">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="aa0f8-113">Erstellen der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="aa0f8-113">Create the library</span></span>

<span data-ttu-id="aa0f8-114">Im ersten Schritt erstellen Sie die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-114">The first step is to create the library.</span></span>

1. <span data-ttu-id="aa0f8-115">Erstellen Sie einen neuen Ordner, und führen Sie in diesem Ordner den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="aa0f8-115">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="aa0f8-116">Öffnen Sie `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-116">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="aa0f8-117">Fügen Sie `using System.Runtime.InteropServices;` am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-117">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="aa0f8-118">Erstellen Sie eine Schnittstelle mit dem Namen `IServer`.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-118">Create an interface named `IServer`.</span></span> <span data-ttu-id="aa0f8-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aa0f8-119">For example:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   [ComVisible(true)]
   [Guid(ContractGuids.ServerInterface)]
   [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
   public interface IServer
   {
       /// <summary>
       /// Compute the value of the constant Pi.
       /// </summary>
       double ComputePi();
   }
   ```

5. <span data-ttu-id="aa0f8-120">Fügen Sie der Schnittstelle das `[Guid("<IID>")]`-Attribut mit der Schnittstellen-GUID für die COM-Schnittstelle hinzu, die Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-120">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="aa0f8-121">Beispielsweise `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-121">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="aa0f8-122">Diese GUID muss eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-122">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="aa0f8-123">In Visual Studio können Sie eine GUID generieren. Rufen Sie dazu „Extras“ > „GUID erstellen“ auf, um das entsprechende Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-123">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="aa0f8-124">Fügen Sie der Schnittstelle das `[InterfaceType]`-Attribut hinzu, und geben Sie an, welche COM-Basisschnittstellen Ihre Schnittstelle implementieren soll.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-124">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="aa0f8-125">Erstellen Sie eine Klasse mit dem Namen `Server`, die `IServer` implementiert.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-125">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="aa0f8-126">Fügen Sie der Klasse das `[Guid("<CLSID>")]`-Attribut mit der Klassenbezeichner-GUID für die COM-Klasse hinzu, die Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-126">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="aa0f8-127">Beispielsweise `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-127">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="aa0f8-128">Diese GUID muss genau wie die Schnittstellen-GUID eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-128">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="aa0f8-129">Fügen Sie der Schnittstelle und der Klasse das `[ComVisible(true)]`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-129">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa0f8-130">Anders als im .NET Framework müssen Sie in .NET Core die CLSID jeder Klasse angeben, die über COM aktivierbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-130">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="aa0f8-131">Generieren des COM-Hosts</span><span class="sxs-lookup"><span data-stu-id="aa0f8-131">Generate the COM host</span></span>

1. <span data-ttu-id="aa0f8-132">Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableComHosting>true</EnableComHosting>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-132">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="aa0f8-133">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-133">Build the project.</span></span>

<span data-ttu-id="aa0f8-134">Die Ausgabe enthält die Dateien `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` und `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-134">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="aa0f8-135">Registrieren des COM-Hosts für COM</span><span class="sxs-lookup"><span data-stu-id="aa0f8-135">Register the COM host for COM</span></span>

<span data-ttu-id="aa0f8-136">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie `regsvr32 ProjectName.comhost.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-136">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="aa0f8-137">Dadurch werden alle verfügbaren .NET-Objekte bei COM registriert.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-137">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="aa0f8-138">Aktivieren von COM ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="aa0f8-138">Enabling RegFree COM</span></span>

1. <span data-ttu-id="aa0f8-139">Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableRegFreeCom>true</EnableRegFreeCom>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-139">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="aa0f8-140">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-140">Build the project.</span></span>

<span data-ttu-id="aa0f8-141">Die Ausgabe enthält nun auch die Datei `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-141">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="aa0f8-142">Bei dieser Datei handelt es sich um das Manifest zur parallelen Ausführung, das ohne COM-Registrierung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-142">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="aa0f8-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa0f8-143">Sample</span></span>

<span data-ttu-id="aa0f8-144">Ein voll funktionsfähiges [Beispiel für COM-Server](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) finden Sie im GitHub-Repository „dotnet/samples“.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-144">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="aa0f8-145">Zusätzliche Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa0f8-145">Additional notes</span></span>

<span data-ttu-id="aa0f8-146">Anders als im .NET Framework wird in .NET Core die Erstellung einer COM-Typbibliothek (TLB) aus einer .NET Core-Assembly nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-146">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="aa0f8-147">Die Anweisung besagt, dass Sie manuell eine IDL-Datei oder einen C++ Header für die nativen Deklarationen Ihrer Schnittstellen schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-147">The guidance is to either manually write an IDL file or a C/C++ header for the native declarations of the COM interfaces.</span></span>

<span data-ttu-id="aa0f8-148">[Eigenständige Bereitstellungen](../deploying/index.md#publish-self-contained) von COM-Komponenten werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-148">[Self-contained deployments](../deploying/index.md#publish-self-contained) of COM components are not supported.</span></span> <span data-ttu-id="aa0f8-149">Nur [laufzeitabhängige Bereitstellungen](../deploying/index.md#publish-runtime-dependent) von COM-Komponenten werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-149">Only [runtime-dependent deployments](../deploying/index.md#publish-runtime-dependent) of COM components are supported.</span></span>

<span data-ttu-id="aa0f8-150">Zusätzlich gelten für das Laden von .NET Framework und .NET Core in denselben Prozess Diagnoseeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-150">Additionally, loading both .NET Framework and .NET Core into the same process does have diagnostic limitations.</span></span> <span data-ttu-id="aa0f8-151">Die erste Einschränkung ist das Debuggen von verwalteten Komponenten, da es nicht möglich ist, .NET Framework und .NET Core gleichzeitig zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-151">The primary limitation is the debugging of managed components as it is not possible to debug both .NET Framework and .NET Core at the same time.</span></span> <span data-ttu-id="aa0f8-152">Zusätzlich teilen die beiden Runtimeinstanzen keine verwalteten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-152">In addition, the two runtime instances don't share managed assemblies.</span></span> <span data-ttu-id="aa0f8-153">Das bedeutet, dass es nicht möglich ist, die tatsächlichen .NET-Typen über zwei Runtimes freizugeben. Stattdessen unterliegen alle Interaktionen den verfügbar gemachten Verträgen zur COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="aa0f8-153">This means that it isn't possible to share actual .NET types across the two runtimes and instead all interactions must be restricted to the exposed COM interface contracts.</span></span>
