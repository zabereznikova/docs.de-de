---
title: Verwenden des Microsoft XML Serializer Generators auf .NET Core
description: Übersicht zum Microsoft XML Serializer Generator.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 98d85821784757db903c97e240c55a3d7bb656d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="81d02-103">Verwenden des Microsoft XML Serializer Generators auf .NET Core</span><span class="sxs-lookup"><span data-stu-id="81d02-103">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="81d02-104">In diesem Tutorial erfahren Sie, wie Sie den Microsoft XML Serializer Generator in einer .NET Core-Anwendung für C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="81d02-104">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="81d02-105">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="81d02-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="81d02-106">Erstellen einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="81d02-106">How to create a .NET Core app</span></span>
> * <span data-ttu-id="81d02-107">Hinzufügen eines Verweises zum Microsoft.XmlSerializer.Generator-Paket</span><span class="sxs-lookup"><span data-stu-id="81d02-107">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="81d02-108">Bearbeiten Ihrer MyApp.csproj-Datei zum Hinzufügen von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="81d02-108">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="81d02-109">Hinzufügen von „XmlSerializer“ und einer Klasse</span><span class="sxs-lookup"><span data-stu-id="81d02-109">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="81d02-110">Erstellen und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="81d02-110">How to build and run the application</span></span> 

<span data-ttu-id="81d02-111">Das [NuGet-Paket „Microsoft.XmlSerializer.Generator“](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Projekte.</span><span class="sxs-lookup"><span data-stu-id="81d02-111">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="81d02-112">Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="81d02-112">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81d02-113">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="81d02-113">Prerequisites</span></span>

<span data-ttu-id="81d02-114">Zum Abschließen dieses Tutorials benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="81d02-114">To complete this tutorial:</span></span>

* <span data-ttu-id="81d02-115">Installieren Sie [.NET Core SDK 2.1.3 oder höher](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="81d02-115">Install [.NET Core SDK 2.1.3 or later](https://www.microsoft.com/net/download)</span></span>
* <span data-ttu-id="81d02-116">Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.</span><span class="sxs-lookup"><span data-stu-id="81d02-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="81d02-117">Benötigen Sie einen Code-Editor?</span><span class="sxs-lookup"><span data-stu-id="81d02-117">Need to install a code editor?</span></span> <span data-ttu-id="81d02-118">Testen Sie [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="81d02-118">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="81d02-119">Verwenden des Microsoft XML Serializer Generators in einer .NET Core-Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="81d02-119">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="81d02-120">In den folgenden Anweisungen wird erläutert, wie Sie den XML Serializer Generator in einer .NET Core-Konsolenanwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="81d02-120">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="81d02-121">Erstellen einer .NET Core-Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="81d02-121">Create a .NET Core console application</span></span>

<span data-ttu-id="81d02-122">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="81d02-122">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="81d02-123">Navigieren Sie zum erstellten Ordner, und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="81d02-123">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="81d02-124">Hinzufügen eines Verweises zum Microsoft.XmlSerializer.Generator-Paket im MyApp-Projekt</span><span class="sxs-lookup"><span data-stu-id="81d02-124">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="81d02-125">Verwenden Sie den [`dotnet add package`](../tools//dotnet-add-package.md)-Befehl, um den Verweis Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="81d02-125">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="81d02-126">Typ:</span><span class="sxs-lookup"><span data-stu-id="81d02-126">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="81d02-127">Überprüfen der Änderungen an der MyApp.csproj-Datei nach dem Hinzufügen des Pakets</span><span class="sxs-lookup"><span data-stu-id="81d02-127">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="81d02-128">Öffnen Sie Ihren Code-Editor, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="81d02-128">Open your code editor and let's get started!</span></span> <span data-ttu-id="81d02-129">Sie arbeiten weiterhin mit dem *MyApp*-Verzeichnis, in dem die App erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="81d02-129">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="81d02-130">Öffnen Sie *MyApp.csproj* in Ihrem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="81d02-130">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="81d02-131">Wenn Sie den Befehl [`dotnet add package`](../tools//dotnet-add-package.md) ausführen, werden die folgenden Zeilen zu Ihrer *MyApp.csproj*-Projektdatei hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="81d02-131">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="81d02-132">Hinzufügen eines weiteren ItemGroup-Abschnitts zur Unterstützung des .NET Core-CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="81d02-132">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="81d02-133">Fügen Sie nach dem zuvor betrachteten Abschnitt `ItemGroup` die folgenden Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="81d02-133">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="81d02-134">Hinzufügen einer Klasse zu der Anwendung</span><span class="sxs-lookup"><span data-stu-id="81d02-134">Add a class in the application</span></span>

<span data-ttu-id="81d02-135">Öffnen Sie *Program.cs* in Ihrem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="81d02-135">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="81d02-136">Fügen Sie die Klasse mit dem Namen *MyClass* unter *Program.cs* hinzu.</span><span class="sxs-lookup"><span data-stu-id="81d02-136">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="81d02-137">Erstellen eines `XmlSerializer` für MyClass</span><span class="sxs-lookup"><span data-stu-id="81d02-137">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="81d02-138">Fügen Sie die folgende Zeile unter *Main* hinzu, um einen `XmlSerializer` für MyClass zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="81d02-138">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="81d02-139">Erstellen eines Builds und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="81d02-139">Build and run the application</span></span>

<span data-ttu-id="81d02-140">Führen Sie (immer noch im Ordner *MyApp*) die Anwendung über [`dotnet run`](../tools/dotnet-run.md) aus. Dann werden die zuvor generierten Serializer zur Runtime automatisch geladen und verwendet.</span><span class="sxs-lookup"><span data-stu-id="81d02-140">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="81d02-141">Geben Sie den folgenden Befehl in Ihr Konsolenfenster ein:</span><span class="sxs-lookup"><span data-stu-id="81d02-141">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="81d02-142">[`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="81d02-142">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81d02-143">Die Befehle und Schritte zum Ausführen der Anwendung, die in diesem Tutorial dargestellt werden, werden nur während zur Entwicklungszeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="81d02-143">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="81d02-144">Wenn Ihre Anwendung bereitgestellt werden kann, sollten Sie einen Blick auf die verschiedenen [Bereitstellungsstrategien](../deploying/index.md) für .NET Core-Apps und den [`dotnet publish`](../tools/dotnet-publish.md)-Befehl werfen.</span><span class="sxs-lookup"><span data-stu-id="81d02-144">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="81d02-145">Wenn alle Vorgänge erfolgreich ausgeführt werden, wird eine Assembly mit dem Namen *MyApp.XmlSerializers.dll* im Ausgabeordner generiert.</span><span class="sxs-lookup"><span data-stu-id="81d02-145">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="81d02-146">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="81d02-146">Congratulations!</span></span> <span data-ttu-id="81d02-147">Sie haben gerade:</span><span class="sxs-lookup"><span data-stu-id="81d02-147">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="81d02-148">eine lokale .NET Core-App erstellt</span><span class="sxs-lookup"><span data-stu-id="81d02-148">Created a .NET Core app.</span></span>
> * <span data-ttu-id="81d02-149">einen Verweis zum Microsoft.XmlSerializer.Generator-Paket hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="81d02-149">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="81d02-150">Ihre MyApp.csproj-Datei bearbeitet, um Abhängigkeiten hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="81d02-150">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="81d02-151">„XmlSerializer“ und eine Klasse hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="81d02-151">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="81d02-152">die Anwendung erstellt und ausgeführt</span><span class="sxs-lookup"><span data-stu-id="81d02-152">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="81d02-153">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="81d02-153">Related Resources</span></span>

* [<span data-ttu-id="81d02-154">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="81d02-154">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* [<span data-ttu-id="81d02-155">How to: Serialize Using XmlSerializer (C#) (Vorgehensweise: Serialisieren mit XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="81d02-155">How to: Serialize Using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
* [<span data-ttu-id="81d02-156">How to: Serialize Using XmlSerializer (Visual Basic) (Vorgehensweise: Serialisieren mit „XmlSerializer“ (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="81d02-156">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
