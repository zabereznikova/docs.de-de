---
title: Verfügbarmachen von .NET Core-Komponenten in COM
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 8f9624414a2b423bd43e8790d11b70ae1ca6286d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216224"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="bda05-102">Verfügbarmachen von .NET Core-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="bda05-102">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="bda05-103">In .NET Core wurde das Verfügbarmachen von .NET-Objekten für COM im Vergleich zum .NET Framework deutlich optimiert.</span><span class="sxs-lookup"><span data-stu-id="bda05-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="bda05-104">Im Folgenden wird erläutert, wie Sie eine Klasse für COM verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="bda05-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="bda05-105">In diesem Tutorial lernen Sie:</span><span class="sxs-lookup"><span data-stu-id="bda05-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="bda05-106">Verfügbarmachen einer Klasse für COM in .NET Core</span><span class="sxs-lookup"><span data-stu-id="bda05-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="bda05-107">Generieren eines COM-Servers bei der Erstellung einer .NET Core-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="bda05-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="bda05-108">Automatisches Generieren eines Manifests zur parallelen Serverausführung ohne COM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="bda05-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bda05-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="bda05-109">Prerequisites</span></span>

- <span data-ttu-id="bda05-110">Installieren Sie [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="bda05-110">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="bda05-111">Erstellen der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="bda05-111">Create the library</span></span>

<span data-ttu-id="bda05-112">Im ersten Schritt erstellen Sie die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="bda05-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="bda05-113">Erstellen Sie einen neuen Ordner, und führen Sie in diesem Ordner den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bda05-113">Create a new folder, and in that folder run the following command:</span></span>
    
    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="bda05-114">Öffnen Sie `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="bda05-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="bda05-115">Fügen Sie `using System.Runtime.InteropServices;` am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="bda05-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="bda05-116">Erstellen Sie eine Schnittstelle mit dem Namen `IServer`.</span><span class="sxs-lookup"><span data-stu-id="bda05-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="bda05-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bda05-117">For example:</span></span>

   [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]

5. <span data-ttu-id="bda05-118">Fügen Sie der Schnittstelle das `[Guid("<IID>")]`-Attribut mit der Schnittstellen-GUID für die COM-Schnittstelle hinzu, die Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="bda05-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="bda05-119">Beispielsweise `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="bda05-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="bda05-120">Diese GUID muss eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="bda05-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="bda05-121">In Visual Studio können Sie eine GUID generieren. Rufen Sie dazu „Extras“ > „GUID erstellen“ auf, um das entsprechende Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bda05-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="bda05-122">Fügen Sie der Schnittstelle das `[InterfaceType]`-Attribut hinzu, und geben Sie an, welche COM-Basisschnittstellen Ihre Schnittstelle implementieren soll.</span><span class="sxs-lookup"><span data-stu-id="bda05-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="bda05-123">Erstellen Sie eine Klasse mit dem Namen `Server`, die `IServer` implementiert.</span><span class="sxs-lookup"><span data-stu-id="bda05-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="bda05-124">Fügen Sie der Klasse das `[Guid("<CLSID>")]`-Attribut mit der Klassenbezeichner-GUID für die COM-Klasse hinzu, die Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="bda05-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="bda05-125">Beispielsweise `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="bda05-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="bda05-126">Diese GUID muss genau wie die Schnittstellen-GUID eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="bda05-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="bda05-127">Fügen Sie der Schnittstelle und der Klasse das `[ComVisible(true)]`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="bda05-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda05-128">Anders als im .NET Framework müssen Sie in .NET Core die CLSID jeder Klasse angeben, die über COM aktivierbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="bda05-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="bda05-129">Generieren des COM-Hosts</span><span class="sxs-lookup"><span data-stu-id="bda05-129">Generate the COM host</span></span>

1. <span data-ttu-id="bda05-130">Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableComHosting>true</EnableComHosting>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="bda05-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="bda05-131">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bda05-131">Build the project.</span></span>

<span data-ttu-id="bda05-132">Die Ausgabe enthält die Dateien `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` und `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="bda05-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="bda05-133">Registrieren des COM-Hosts für COM</span><span class="sxs-lookup"><span data-stu-id="bda05-133">Register the COM host for COM</span></span>

<span data-ttu-id="bda05-134">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie `regsvr32 ProjectName.comhost.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="bda05-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="bda05-135">Dadurch werden alle verfügbaren .NET-Objekte bei COM registriert.</span><span class="sxs-lookup"><span data-stu-id="bda05-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="bda05-136">Aktivieren von COM ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="bda05-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="bda05-137">Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableRegFreeCom>true</EnableRegFreeCom>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="bda05-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="bda05-138">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bda05-138">Build the project.</span></span>

<span data-ttu-id="bda05-139">Die Ausgabe enthält nun auch die Datei `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="bda05-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="bda05-140">Bei dieser Datei handelt es sich um das Manifest zur parallelen Ausführung, das ohne COM-Registrierung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bda05-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="bda05-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bda05-141">Sample</span></span>

<span data-ttu-id="bda05-142">Ein voll funktionsfähiges [Beispiel für COM-Server](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) finden Sie im GitHub-Repository „dotnet/samples“.</span><span class="sxs-lookup"><span data-stu-id="bda05-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="bda05-143">Zusätzliche Hinweise</span><span class="sxs-lookup"><span data-stu-id="bda05-143">Additional notes</span></span>

<span data-ttu-id="bda05-144">Anders als im .NET Framework wird in .NET Core die Erstellung einer COM-Typbibliothek (TLB) aus einer .NET Core-Assembly nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bda05-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="bda05-145">Sie müssen entweder manuell eine IDL-Datei oder einen C++ Header für die nativen Deklarationen Ihrer Schnittstellen schreiben.</span><span class="sxs-lookup"><span data-stu-id="bda05-145">You will either have to manually write an IDL file or a C++ header for the native declarations of your interfaces.</span></span>

<span data-ttu-id="bda05-146">Außerdem können das .NET Framework und .NET Core nicht in denselben Prozess geladen werden. Ein COM-Server für .NET Core kann daher nicht in einen COM-Clientprozess für das .NET Framework geladen werden und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="bda05-146">Additionally, loading both .NET Framework and .NET Core into the same process is unsupported, and as a result loading a .NET Core COM server into a .NET Framework COM client process or vice versa is not supported.</span></span>
