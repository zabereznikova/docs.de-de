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
ms.openlocfilehash: 33574eeac5b1f7aa2067b1974f3f2e68fb22e8ff
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577172"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="d50ff-102">Verfügbarmachen von .NET Core-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="d50ff-102">Exposing .NET Core Components to COM</span></span>

<span data-ttu-id="d50ff-103">In .NET Core wurde das Verfügbarmachen von .NET-Objekten für COM im Vergleich zum .NET Framework deutlich optimiert.</span><span class="sxs-lookup"><span data-stu-id="d50ff-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="d50ff-104">Im Folgenden wird erläutert, wie Sie eine Klasse für COM verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="d50ff-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="d50ff-105">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d50ff-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="d50ff-106">Verfügbarmachen einer Klasse für COM in .NET Core</span><span class="sxs-lookup"><span data-stu-id="d50ff-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="d50ff-107">Generieren eines COM-Servers bei der Erstellung einer .NET Core-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d50ff-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="d50ff-108">Automatisches Generieren eines Manifests zur parallelen Serverausführung ohne COM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="d50ff-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d50ff-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="d50ff-109">Prerequisites</span></span>

- <span data-ttu-id="d50ff-110">Installieren Sie das [.NET Core 3.0 Preview 7 SDK](https://www.microsoft.com/net/core) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="d50ff-110">Install the [.NET Core 3.0 Preview 7 SDK](https://www.microsoft.com/net/core) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="d50ff-111">Erstellen der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d50ff-111">Create the library</span></span>

<span data-ttu-id="d50ff-112">Im ersten Schritt erstellen Sie die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="d50ff-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="d50ff-113">Erstellen Sie einen neuen Ordner, und führen Sie `dotnet new classlib` in diesem Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="d50ff-113">Create a new folder, and in that folder run `dotnet new classlib`.</span></span>
2. <span data-ttu-id="d50ff-114">Öffnen Sie `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="d50ff-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="d50ff-115">Fügen Sie `using System.Runtime.InteropServices;` am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="d50ff-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="d50ff-116">Erstellen Sie eine Schnittstelle mit dem Namen `IServer`.</span><span class="sxs-lookup"><span data-stu-id="d50ff-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="d50ff-117">Beispiel: [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)].</span><span class="sxs-lookup"><span data-stu-id="d50ff-117">For example: [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]</span></span>
5. <span data-ttu-id="d50ff-118">Fügen Sie der Schnittstelle das `[Guid("<IID>")]`-Attribut mit der Schnittstellen-GUID für die COM-Schnittstelle hinzu, die Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="d50ff-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="d50ff-119">Beispielsweise `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="d50ff-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="d50ff-120">Diese GUID muss eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="d50ff-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="d50ff-121">In Visual Studio können Sie eine GUID generieren. Rufen Sie dazu „Extras“ > „GUID erstellen“ auf, um das entsprechende Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d50ff-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="d50ff-122">Fügen Sie der Schnittstelle das `[InterfaceType]`-Attribut hinzu, und geben Sie an, welche COM-Basisschnittstellen Ihre Schnittstelle implementieren soll.</span><span class="sxs-lookup"><span data-stu-id="d50ff-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="d50ff-123">Erstellen Sie eine Klasse mit dem Namen `Server`, die `IServer` implementiert.</span><span class="sxs-lookup"><span data-stu-id="d50ff-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="d50ff-124">Fügen Sie der Klasse das `[Guid("<CLSID>")]`-Attribut mit der Klassenbezeichner-GUID für die COM-Klasse hinzu, die Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="d50ff-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="d50ff-125">Beispielsweise `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="d50ff-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="d50ff-126">Diese GUID muss genau wie die Schnittstellen-GUID eindeutig sein, da sie der einzige Bezeichner dieser COM-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="d50ff-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="d50ff-127">Fügen Sie der Schnittstelle und der Klasse das `[ComVisible(true)]`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="d50ff-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d50ff-128">Anders als im .NET Framework müssen Sie in .NET Core die CLSID jeder Klasse angeben, die über COM aktivierbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="d50ff-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="d50ff-129">Generieren des COM-Hosts</span><span class="sxs-lookup"><span data-stu-id="d50ff-129">Generate the COM host</span></span>

1. <span data-ttu-id="d50ff-130">Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableComHosting>true</EnableComHosting>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="d50ff-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="d50ff-131">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d50ff-131">Build the project.</span></span>

<span data-ttu-id="d50ff-132">Die Ausgabe enthält die Dateien `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` und `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="d50ff-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="d50ff-133">Registrieren des COM-Hosts für COM</span><span class="sxs-lookup"><span data-stu-id="d50ff-133">Register the COM host for COM</span></span>

<span data-ttu-id="d50ff-134">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie `regsvr32 ProjectName.comhost.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="d50ff-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="d50ff-135">Dadurch werden alle verfügbaren .NET-Objekte bei COM registriert.</span><span class="sxs-lookup"><span data-stu-id="d50ff-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="d50ff-136">Aktivieren von COM ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="d50ff-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="d50ff-137">Öffnen Sie die Projektdatei `.csproj`, und fügen Sie `<EnableRegFreeCom>true</EnableRegFreeCom>` innerhalb eines `<PropertyGroup></PropertyGroup>`-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="d50ff-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="d50ff-138">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d50ff-138">Build the project.</span></span>

<span data-ttu-id="d50ff-139">Die Ausgabe enthält nun auch die Datei `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="d50ff-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="d50ff-140">Bei dieser Datei handelt es sich um das Manifest zur parallelen Ausführung, das ohne COM-Registrierung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d50ff-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="d50ff-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d50ff-141">Sample</span></span>

<span data-ttu-id="d50ff-142">Ein voll funktionsfähiges [Beispiel für COM-Server](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) finden Sie im GitHub-Repository „dotnet/samples“.</span><span class="sxs-lookup"><span data-stu-id="d50ff-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="d50ff-143">Zusätzliche Hinweise</span><span class="sxs-lookup"><span data-stu-id="d50ff-143">Additional Notes</span></span>

<span data-ttu-id="d50ff-144">Anders als im .NET Framework wird in .NET Core die Erstellung einer COM-Typbibliothek (TLB) aus einer .NET Core-Assembly nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d50ff-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="d50ff-145">Sie müssen entweder manuell eine IDL-Datei oder einen C++ Header für die nativen Deklarationen Ihrer Schnittstellen schreiben.</span><span class="sxs-lookup"><span data-stu-id="d50ff-145">You will either have to manually write an IDL file or a C++ header for the native declarations of your interfaces.</span></span>

<span data-ttu-id="d50ff-146">Außerdem können das .NET Framework und .NET Core nicht in denselben Prozess geladen werden. Ein COM-Server für .NET Core kann daher nicht in einen COM-Clientprozess für das .NET Framework geladen werden und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="d50ff-146">Additionally, loading both .NET Framework and .NET Core into the same process is unsupported, and as a result loading a .NET Core COM server into a .NET Framework COM client process or vice versa is not supported.</span></span>
