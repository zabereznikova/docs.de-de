---
title: Übersicht zum WCF-Tool „svcutil“
description: Übersicht zum Microsoft-WCF-Tool „dotnet-svcutil“, über das Funktionen für .NET Core- und ASP.NET Core-Projekte hinzugefügt werden, z.B. das WCF-Tool „svcutil“ für .NET Framework-Projekte.
author: mlacouture
ms.date: 02/22/2019
ms.openlocfilehash: 0607c73935f319f2cc0d8d9f92d96a4c71c54edf
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920948"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a><span data-ttu-id="6785b-103">WCF-Tool „dotnet-svcutil“ für .NET Core</span><span class="sxs-lookup"><span data-stu-id="6785b-103">WCF dotnet-svcutil tool for .NET Core</span></span>

<span data-ttu-id="6785b-104">Das **dotnet-svcutil**-Tool der Windows Communication Foundation (WCF) ist ein .NET-Tool, das Metadaten von einem Webdienst aus einem Netzwerkspeicherort oder einer WSDL-Datei abruft und eine WCF-Klasse mit Clientproxymethoden generiert, die auf Webdienstvorgänge zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6785b-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="6785b-105">Ähnlich wie das [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)-Tool für .NET Framework-Projekte ist **dotnet-svcutil** ein Befehlszeilentool zum Generieren eines Webdienstverweises, der mit .NET Core- und .NET Standard-Projekten kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="6785b-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="6785b-106">Das Tool **dotnet-svcutil** ist eine alternative Option zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der zuerst in Visual Studio 2017 Version15.5 enthalten war.</span><span class="sxs-lookup"><span data-stu-id="6785b-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 version 15.5.</span></span> <span data-ttu-id="6785b-107">Das .NET-Tool **dotnet-svcutil** ist plattformübergreifend für Linux, macOS und Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6785b-107">The **dotnet-svcutil** tool as a .NET tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6785b-108">Sie sollten nur auf Dienste aus einer vertrauenswürdigen Quelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="6785b-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="6785b-109">Wenn Sie Verweise aus nicht vertrauenswürdigen Quellen hinzufügen, hat das möglicherweise Auswirkungen auf die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="6785b-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6785b-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6785b-110">Prerequisites</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="6785b-111">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="6785b-111">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

- <span data-ttu-id="6785b-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="6785b-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="6785b-113">Ihr bevorzugter Code-Editor</span><span class="sxs-lookup"><span data-stu-id="6785b-113">Your favorite code editor</span></span>

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="6785b-114">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="6785b-114">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

- <span data-ttu-id="6785b-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="6785b-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="6785b-116">Ihr bevorzugter Code-Editor</span><span class="sxs-lookup"><span data-stu-id="6785b-116">Your favorite code editor</span></span>

---

## <a name="getting-started"></a><span data-ttu-id="6785b-117">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="6785b-117">Getting started</span></span>

<span data-ttu-id="6785b-118">Das folgende Beispiel führt Sie durch die erforderlichen Schritte zum Hinzufügen eines Webdienstverweises zu einem .NET Core- Webprojekt und Aufrufen des Diensts.</span><span class="sxs-lookup"><span data-stu-id="6785b-118">The following example walks you through the steps required to add a web service reference to a .NET Core web project and invoke the service.</span></span> <span data-ttu-id="6785b-119">Sie erstellen eine .NET Core-Webanwendung mit dem Namen *HelloSvcutil* und fügen einen Verweis auf einen Webdienst hinzu, der folgenden Vertrag implementiert:</span><span class="sxs-lookup"><span data-stu-id="6785b-119">You'll create a .NET Core web application named *HelloSvcutil* and add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="6785b-120">In diesem Beispiel wird angenommen, dass der Webdienst unter folgender Adresse gehostet wird: `http://contoso.com/SayHello.svc`.</span><span class="sxs-lookup"><span data-stu-id="6785b-120">For this example, let's assume the web service will be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="6785b-121">Führen Sie in einem Windows-, macOS- oder Linux-Befehlsfenster die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6785b-121">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="6785b-122">Erstellen Sie ein Verzeichnis mit dem Namen _HelloSvcutil_ für das Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6785b-122">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

    ```console
    mkdir HelloSvcutil
    cd HelloSvcutil
    ```

2. <span data-ttu-id="6785b-123">Erstellen Sie mithilfe des [`dotnet new`](../tools/dotnet-new.md)-Befehls wie folgt ein neues C#-Webprojekt in diesem Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="6785b-123">Create a new C# web project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

    ```dotnetcli
    dotnet new web
    ```

3. <span data-ttu-id="6785b-124">Installieren Sie das [`dotnet-svcutil` NuGet-Paket](https://nuget.org/packages/dotnet-svcutil) als CLI-Tool:  </span><span class="sxs-lookup"><span data-stu-id="6785b-124">Install the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool:  </span></span><!-- markdownlint-disable MD023 -->
    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="6785b-125">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="6785b-125">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet tool install --global dotnet-svcutil
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="6785b-126">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="6785b-126">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)
    <span data-ttu-id="6785b-127">Öffnen Sie die `HelloSvcutil.csproj`-Projektdatei im Editor, bearbeiten Sie das `Project`-Element, und fügen Sie mithilfe des folgenden Codes das [`dotnet-svcutil`NuGet-Paket](https://nuget.org/packages/dotnet-svcutil) als CLI-Toolverweis hinzu:</span><span class="sxs-lookup"><span data-stu-id="6785b-127">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
    </ItemGroup>
    ```

    <span data-ttu-id="6785b-128">Stellen Sie dann das _dotnet-svcutil_-Paket mithilfe des [`dotnet restore`](../tools/dotnet-restore.md)-Befehls wie folgt wieder her:</span><span class="sxs-lookup"><span data-stu-id="6785b-128">Then restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

    ---

4. <span data-ttu-id="6785b-129">Führen Sie den Befehl _dotnet-svcutil_ aus, um die Webdienstverweisdatei zu generieren:</span><span class="sxs-lookup"><span data-stu-id="6785b-129">Run the _dotnet-svcutil_ command to generate the web service reference file as follows:</span></span>

    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="6785b-130">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="6785b-130">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet-svcutil http://contoso.com/SayHello.svc
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="6785b-131">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="6785b-131">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

    ```dotnetcli
    dotnet svcutil http://contoso.com/SayHello.svc
    ```

    ---

<span data-ttu-id="6785b-132">Die generierte Datei wird als _HelloSvcutil/ServiceReference/Reference.cs_ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6785b-132">The generated file is saved as _HelloSvcutil/ServiceReference/Reference.cs_.</span></span> <span data-ttu-id="6785b-133">Das _dotnet-svcutil_-Tool fügt dem Projekt auch die entsprechenden WCF-Pakete hinzu, die der Proxycode als Paketverweise benötigt.</span><span class="sxs-lookup"><span data-stu-id="6785b-133">The _dotnet-svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

## <a name="using-the-service-reference"></a><span data-ttu-id="6785b-134">Verwenden des Dienstverweisnamens</span><span class="sxs-lookup"><span data-stu-id="6785b-134">Using the Service Reference</span></span>

1. <span data-ttu-id="6785b-135">Stellen Sie wie folgt die WCF-Pakete mithilfe des [`dotnet restore`](../tools/dotnet-restore.md)-Befehls wieder her:</span><span class="sxs-lookup"><span data-stu-id="6785b-135">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

2. <span data-ttu-id="6785b-136">Suchen Sie den Namen der Clientklasse und den Vorgang, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6785b-136">Find the name of the client class and operation you want to use.</span></span> <span data-ttu-id="6785b-137">`Reference.cs` enthält eine Klasse, die von `System.ServiceModel.ClientBase` erbt, mit Methoden, die zum Aufrufen von Vorgängen für den Dienst verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6785b-137">`Reference.cs` will contain a class that inherits from `System.ServiceModel.ClientBase`, with methods that can be used to call operations on the service.</span></span> <span data-ttu-id="6785b-138">In diesem Beispiel rufen Sie den Vorgang _SayHello_ des Diensts _Hello_ auf.</span><span class="sxs-lookup"><span data-stu-id="6785b-138">In this example, you want to call the _SayHello_ service's _Hello_ operation.</span></span> <span data-ttu-id="6785b-139">`ServiceReference.SayHelloClient` ist der Name der Clientklasse und hat eine Methode `HelloAsync` aufgerufen, die verwendet werden kann, um den Vorgang aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6785b-139">`ServiceReference.SayHelloClient` is the name of the client class, and has a method called `HelloAsync` that can be used to call the operation.</span></span>

3. <span data-ttu-id="6785b-140">Öffnen Sie die `Startup.cs`-Datei in einem Editor, und fügen Sie eine using-Anweisung für den Dienstverweisnamespace oben hinzu:</span><span class="sxs-lookup"><span data-stu-id="6785b-140">Open the `Startup.cs` file in your editor, and add a using statement for the service reference namespace at the top:</span></span>

    ```csharp
    using ServiceReference;
    ```

4. <span data-ttu-id="6785b-141">Bearbeiten Sie die `Configure`-Methode zum Aufrufen des Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="6785b-141">Edit the `Configure` method to invoke the web service.</span></span> <span data-ttu-id="6785b-142">Hierzu erstellen Sie eine Instanz der Klasse, die von `ClientBase` erbt, und rufen die Methode für das Clientobjekt auf:</span><span class="sxs-lookup"><span data-stu-id="6785b-142">You do this by creating an instance of the class that inherits from `ClientBase` and calling the method on the client object:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            var client = new SayHelloClient();
            var response = await client.HelloAsync();
            await context.Response.WriteAsync(response);
        });
    }

    ```

5. <span data-ttu-id="6785b-143">Führen Sie die Anwendung wie folgt mithilfe des [`dotnet run`](../tools/dotnet-run.md)-Befehls aus:</span><span class="sxs-lookup"><span data-stu-id="6785b-143">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

    ```dotnetcli
    dotnet run
    ```

6. <span data-ttu-id="6785b-144">Navigieren Sie in Ihrem Webbrowser zu der URL, die in der Konsole aufgelistet ist, (z.B. `http://localhost:5000`).</span><span class="sxs-lookup"><span data-stu-id="6785b-144">Navigate to the URL listed in the console (for example, `http://localhost:5000`) in your web browser.</span></span>

<span data-ttu-id="6785b-145">Die folgende Ausgabe wird angezeigt: „Hello dotnet-svcutil!“</span><span class="sxs-lookup"><span data-stu-id="6785b-145">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="6785b-146">Um eine ausführliche Beschreibung der Parameter des `dotnet-svcutil`-Tools zu erhalten, rufen Sie das Tool wie folgt mit Übergabe des Hilfeparameters auf:</span><span class="sxs-lookup"><span data-stu-id="6785b-146">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>
# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="6785b-147">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="6785b-147">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

```dotnetcli
dotnet-svcutil --help
```

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="6785b-148">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="6785b-148">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

```dotnetcli
dotnet svcutil --help
```

---

## <a name="feedback--questions"></a><span data-ttu-id="6785b-149">Feedback und Fragen</span><span class="sxs-lookup"><span data-stu-id="6785b-149">Feedback & questions</span></span>

<span data-ttu-id="6785b-150">Wenn Sie Fragen haben oder uns Feedback geben möchten, [öffnen Sie ein Problem auf GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="6785b-150">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="6785b-151">Sie können außerdem bereits vorhandene Fragen oder Probleme [im WCF-Repository auf GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6785b-151">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

## <a name="release-notes"></a><span data-ttu-id="6785b-152">Anmerkungen zu diesem Release</span><span class="sxs-lookup"><span data-stu-id="6785b-152">Release notes</span></span>

- <span data-ttu-id="6785b-153">Aktualisierte Informationen zu den einzelnen Versionen, einschließlich bekannter Probleme, finden Sie in den [Anmerkungen zu den jeweiligen Versionen](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md).</span><span class="sxs-lookup"><span data-stu-id="6785b-153">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

## <a name="information"></a><span data-ttu-id="6785b-154">Information</span><span class="sxs-lookup"><span data-stu-id="6785b-154">Information</span></span>

- [<span data-ttu-id="6785b-155">dotnet-svcutil-NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="6785b-155">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)
