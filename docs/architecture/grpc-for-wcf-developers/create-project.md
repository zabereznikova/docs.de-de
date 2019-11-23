---
title: 'Erstellen eines neuen ASP.net Core GrpC-Projekts: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie ein GrpC-Projekt mithilfe von Visual Studio oder über die Befehlszeile erstellen.
ms.date: 09/02/2019
ms.openlocfilehash: 992c3f57be25ae2517d41437170dc287f58934b6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967893"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="f1105-103">Erstellen eines neuen ASP.NET Core gRPC-Projekts</span><span class="sxs-lookup"><span data-stu-id="f1105-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="f1105-104">.Net Core verfügt über ein leistungsfähiges CLI-Tool, `dotnet`, das es Ihnen ermöglicht, Projekte und Projektmappen über die Befehlszeile zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f1105-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="f1105-105">Das Tool ist eng in Visual Studio integriert, sodass alles auch über die vertraute GUI-Oberfläche verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f1105-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="f1105-106">In diesem Kapitel werden beide Methoden zum Erstellen eines neuen ASP.net Core GrpC-Projekts gezeigt: zuerst mit Visual Studio, dann mit dem .net Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="f1105-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="f1105-107">Erstellen des Projekts mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f1105-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1105-108">Zum Entwickeln einer ASP.net Core 3,0-App benötigen Sie Visual Studio 2019,3 oder höher mit installierter **ASP.net-und Webentwicklungs-** Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="f1105-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="f1105-109">Erstellen Sie eine leere Projekt Mappe mit dem Namen **tradersys** aus der Vorlage *leere* Projekt Mappe.</span><span class="sxs-lookup"><span data-stu-id="f1105-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="f1105-110">Fügen Sie einen Projektmappenordner namens `src`hinzu, klicken Sie mit der rechten Maustaste auf den Ordner, und wählen Sie im Kontextmenü > **Neues Projekt** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f1105-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="f1105-111">Geben Sie im Feld für die Vorlagen Suche `grpc` ein, und Sie sollten eine Projektvorlage mit dem Namen `gRPC Service`sehen.</span><span class="sxs-lookup"><span data-stu-id="f1105-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![Dialogfeld "Neues Projekt hinzufügen" mit der Projektvorlage "GrpC](media/create-project/new-grpc-project.png)

<span data-ttu-id="f1105-113">Klicken Sie auf weiter **, um mit** dem Dialogfeld **Projekt konfigurieren** fortzufahren, benennen Sie das Projekt `TraderSys.Portfolios`, und fügen Sie dem **Speicherort**ein `src` Unterverzeichnis hinzu.</span><span class="sxs-lookup"><span data-stu-id="f1105-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Dialogfeld "Projekt konfigurieren](media/create-project/configure-project.png)

<span data-ttu-id="f1105-115">Klicken **Sie auf weiter** , um zum Dialogfeld **Neues GrpC-Projekt** zu klicken.</span><span class="sxs-lookup"><span data-stu-id="f1105-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![Neues GrpC-Projekt Dialogfeld](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="f1105-117">Derzeit sind für die Dienst Erstellung begrenzte Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1105-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="f1105-118">Docker wird später im Buch eingeführt, lassen Sie das Kontrollkästchen jetzt deaktiviert, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f1105-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="f1105-119">Ihr erstes ASP.net Core 3,0-GrpC-Projekt wird generiert und der Projekt Mappe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f1105-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="f1105-120">Wenn Sie nicht wissen möchten, wie Sie mit dem `dotnet CLI`arbeiten, fahren Sie mit dem Abschnitt [Bereinigen des Beispielcodes](#clean-up-the-example-code) fort.</span><span class="sxs-lookup"><span data-stu-id="f1105-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="f1105-121">Erstellen Sie das Projekt mit dem .net Core-CLI</span><span class="sxs-lookup"><span data-stu-id="f1105-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="f1105-122">In diesem Abschnitt wird die Erstellung von Projektmappen und Projekten von der Befehlszeile aus behandelt.</span><span class="sxs-lookup"><span data-stu-id="f1105-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="f1105-123">Erstellen Sie die Lösung wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1105-123">Create the solution as shown below.</span></span> <span data-ttu-id="f1105-124">Das Flag `-o` (oder `--output`) gibt das Ausgabeverzeichnis an, das im aktuellen Verzeichnis erstellt wird, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1105-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="f1105-125">Die Lösung erhält denselben Namen wie das Verzeichnis, d. h. `TraderSys.sln`. Mit dem `-n`-Flag (oder `--name`) können Sie einen anderen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="f1105-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="f1105-126">In ASP.net Core 3,0 ist eine CLI-Vorlage für GrpC-Dienste verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1105-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="f1105-127">Erstellen Sie das neue Projekt mithilfe dieser Vorlage, und legen Sie es in einem `src` Unterverzeichnis ab, das der Konvention für ASP.net Core Projekte entspricht.</span><span class="sxs-lookup"><span data-stu-id="f1105-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="f1105-128">Das Projekt wird nach dem Verzeichnis benannt (d. h. `TraderSys.Portfolios.csproj`), es sei denn, Sie geben einen anderen Namen mit dem `-n`-Flag an.</span><span class="sxs-lookup"><span data-stu-id="f1105-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="f1105-129">Fügen Sie schließlich das Projekt der Projekt Mappe mit dem Befehl `dotnet sln` hinzu.</span><span class="sxs-lookup"><span data-stu-id="f1105-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="f1105-130">Da das angegebene Verzeichnis nur eine einzige `.csproj` Datei enthält, können Sie mit der Angabe des Verzeichnisses, in dem die Typisierung gespeichert wird, nicht nur das Verzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="f1105-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="f1105-131">Sie können diese Projekt Mappe jetzt in Visual Studio 2019, Visual Studio Code oder einem beliebigen Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1105-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="f1105-132">Bereinigen des Beispielcodes</span><span class="sxs-lookup"><span data-stu-id="f1105-132">Clean up the example code</span></span>

<span data-ttu-id="f1105-133">Sie haben nun einen Beispiel Dienst mithilfe der GrpC-Vorlage erstellt, die weiter oben im Buch erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1105-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="f1105-134">Dies ist in unserem Aktienhandels Kontext nicht nützlich, daher bearbeiten wir die Dinge für unser erstes Projekt.</span><span class="sxs-lookup"><span data-stu-id="f1105-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="f1105-135">Umbenennen und Bearbeiten der Proto-Datei</span><span class="sxs-lookup"><span data-stu-id="f1105-135">Rename and edit the proto file</span></span>

<span data-ttu-id="f1105-136">Benennen Sie die Datei `Protos/greet.proto` in `Protos/portfolios.proto` um, und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="f1105-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="f1105-137">Löschen Sie alles nach der `package` Zeile, ändern Sie die Namen der `option csharp_namespace`, `package` und `service`, und entfernen Sie den Standard-`SayHello` Dienst, sodass der Code wie folgt aussieht.</span><span class="sxs-lookup"><span data-stu-id="f1105-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="f1105-138">Die Vorlage fügt den `Protos` Namespace-Teil nicht standardmäßig hinzu. durch das hinzufügen wird jedoch die von GrpC generierten Klassen und ihre eigenen Klassen leichter in Ihren Code aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="f1105-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="f1105-139">Wenn Sie die `greet.proto` Datei in einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio umbenennen, wird ein Verweis auf diese Datei in der `.csproj`-Datei automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f1105-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="f1105-140">In einem anderen Editor, z. b. Visual Studio Code, wird dieser Verweis jedoch nicht automatisch aktualisiert, sodass Sie die Projektdatei manuell bearbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="f1105-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="f1105-141">In den GrpC-Build-Zielen gibt es ein `Protobuf` Item-Element, mit dem Sie angeben können, welche `.proto` Dateien kompiliert werden sollen und welche Form der Codegenerierung erforderlich ist (d. h. "Server" oder "Client").</span><span class="sxs-lookup"><span data-stu-id="f1105-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="f1105-142">Umbenennen der greeterservice-Klasse</span><span class="sxs-lookup"><span data-stu-id="f1105-142">Rename the GreeterService class</span></span>

<span data-ttu-id="f1105-143">Die `GreeterService`-Klasse befindet sich im Ordner `Services` und erbt von `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="f1105-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="f1105-144">Benennen Sie es in `PortfolioService` um, und ändern Sie die Basisklasse in `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="f1105-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="f1105-145">Löschen Sie die `override` Methoden.</span><span class="sxs-lookup"><span data-stu-id="f1105-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="f1105-146">Es gab einen Verweis auf die `GreeterService`-Klasse in der `Configure`-Methode in der `Startup`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1105-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="f1105-147">Wenn Sie Refactoring verwendet haben, um die Klasse umzubenennen, sollte diese Referenz automatisch aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f1105-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="f1105-148">Wenn dies nicht der Fall ist, müssen Sie Sie manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f1105-148">However, if you didn't, you need to edit it manually.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="f1105-149">Im nächsten Abschnitt fügen wir diesem neuen Dienstfunktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="f1105-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f1105-150">[Zurück](migrate-wcf-to-grpc.md)
>[Weiter](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="f1105-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
