---
title: 'Erstellen eines neuen ASP.net Core GrpC-Projekts: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie ein GrpC-Projekt mithilfe von Visual Studio oder der Befehlszeile erstellen.
ms.date: 09/02/2019
ms.openlocfilehash: ea6d7658404f61fedb25d7de7ddedb7c51437383
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711449"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="b90ce-103">Erstellen eines neuen ASP.NET Core gRPC-Projekts</span><span class="sxs-lookup"><span data-stu-id="b90ce-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="b90ce-104">Die .net Core SDK verfügt über ein leistungsfähiges CLI-Tool `dotnet`, mit dem Sie Projekte und Projektmappen über die Befehlszeile erstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="b90ce-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="b90ce-105">Das SDK ist eng in Visual Studio integriert, sodass alles auch über die vertraute grafische Benutzeroberfläche verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b90ce-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="b90ce-106">Dieses Kapitel zeigt beide Möglichkeiten zum Erstellen eines neuen ASP.net Core GrpC-Projekts.</span><span class="sxs-lookup"><span data-stu-id="b90ce-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="b90ce-107">Erstellen des Projekts mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b90ce-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b90ce-108">Zum Entwickeln einer ASP.net Core 3,0-App benötigen Sie Visual Studio 2019 16,3 oder höher mit installierter **ASP.net-und Webentwicklungs-** Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="b90ce-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="b90ce-109">Erstellen Sie eine leere Projekt Mappe mit dem Namen **tradersys** aus der Vorlage *leere* Projekt Mappe.</span><span class="sxs-lookup"><span data-stu-id="b90ce-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="b90ce-110">Fügen Sie einen Projektmappenordner namens `src`hinzu.</span><span class="sxs-lookup"><span data-stu-id="b90ce-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="b90ce-111">Klicken Sie dann mit der rechten Maustaste auf den Ordner, und wählen Sie > **Neues Projekt** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b90ce-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="b90ce-112">Geben Sie im Feld für die Vorlagen Suche `grpc` ein, und Sie sollten eine Projektvorlage mit dem Namen `gRPC Service`sehen.</span><span class="sxs-lookup"><span data-stu-id="b90ce-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Screenshot des Dialog Felds "Neues Projekt hinzufügen"](media/create-project/new-grpc-project.png)

<span data-ttu-id="b90ce-114">Wählen **Sie weiter aus** , um mit dem Dialogfeld **Neues Projekt konfigurieren** fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="b90ce-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="b90ce-115">Benennen Sie das Projekt `TraderSys.Portfolios`, und fügen Sie dem **Speicherort**ein `src` Unterverzeichnis hinzu.</span><span class="sxs-lookup"><span data-stu-id="b90ce-115">Name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Screenshot des Dialog Felds "Neues Projekt konfigurieren"](media/create-project/configure-project.png)

<span data-ttu-id="b90ce-117">Wählen **Sie weiter aus** , um mit dem Dialogfeld **neuen GrpC-Dienst erstellen** fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="b90ce-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Screenshot des Dialog Felds "neuen GrpC-Dienst erstellen"](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="b90ce-119">Derzeit haben Sie eingeschränkte Optionen für die Dienst Erstellung.</span><span class="sxs-lookup"><span data-stu-id="b90ce-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="b90ce-120">Docker wird später eingeführt, lassen Sie diese Option vorerst deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b90ce-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="b90ce-121">Wählen Sie einfach **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="b90ce-121">Just select **Create**.</span></span> <span data-ttu-id="b90ce-122">Ihr erstes ASP.net Core 3,0-GrpC-Projekt wird generiert und der Projekt Mappe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b90ce-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="b90ce-123">Wenn Sie nicht wissen möchten, wie Sie mit dem `dotnet CLI`arbeiten, fahren Sie mit dem Abschnitt [Bereinigen des Beispielcodes](#clean-up-the-example-code) fort.</span><span class="sxs-lookup"><span data-stu-id="b90ce-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="b90ce-124">Erstellen Sie das Projekt mithilfe des .net Core-CLI</span><span class="sxs-lookup"><span data-stu-id="b90ce-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="b90ce-125">In diesem Abschnitt wird die Erstellung von Projektmappen und Projekten von der Befehlszeile aus behandelt.</span><span class="sxs-lookup"><span data-stu-id="b90ce-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="b90ce-126">Erstellen Sie die Projekt Mappe, wie im folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b90ce-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="b90ce-127">Das Flag `-o` (oder `--output`) gibt das Ausgabeverzeichnis an, das im aktuellen Verzeichnis erstellt wird, wenn es nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b90ce-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="b90ce-128">Die Projekt Mappe hat denselben Namen wie das Verzeichnis: `TraderSys.sln`.</span><span class="sxs-lookup"><span data-stu-id="b90ce-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="b90ce-129">Sie können einen anderen Namen angeben, indem Sie das Flag `-n` (oder `--name`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b90ce-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="b90ce-130">In ASP.net Core 3,0 ist eine CLI-Vorlage für GrpC-Dienste verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b90ce-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="b90ce-131">Erstellen Sie das neue Projekt mithilfe dieser Vorlage, und platzieren Sie es in einem `src` Unterverzeichnis, das für ASP.net Core Projekte konventionell ist.</span><span class="sxs-lookup"><span data-stu-id="b90ce-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="b90ce-132">Das Projekt wird nach dem Verzeichnis (`TraderSys.Portfolios.csproj`) benannt, es sei denn, Sie geben einen anderen Namen mit dem `-n`-Flag an.</span><span class="sxs-lookup"><span data-stu-id="b90ce-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="b90ce-133">Fügen Sie schließlich das Projekt der Projekt Mappe hinzu, indem Sie den `dotnet sln`-Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="b90ce-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="b90ce-134">Da das jeweilige Verzeichnis nur eine einzige `.csproj` Datei enthält, können Sie nur das Verzeichnis angeben, um die Typisierung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b90ce-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="b90ce-135">Sie können diese Projekt Mappe jetzt in Visual Studio 2019, Visual Studio Code oder einem beliebigen Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="b90ce-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="b90ce-136">Bereinigen des Beispielcodes</span><span class="sxs-lookup"><span data-stu-id="b90ce-136">Clean up the example code</span></span>

<span data-ttu-id="b90ce-137">Sie haben nun einen Beispiel Dienst mithilfe der GrpC-Vorlage erstellt, die weiter oben im Buch erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="b90ce-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="b90ce-138">Dies ist in unserem Aktienhandels Kontext nicht nützlich, daher bearbeiten wir die Dinge für unser erstes Projekt.</span><span class="sxs-lookup"><span data-stu-id="b90ce-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="b90ce-139">Umbenennen und Bearbeiten der Proto-Datei</span><span class="sxs-lookup"><span data-stu-id="b90ce-139">Rename and edit the proto file</span></span>

<span data-ttu-id="b90ce-140">Benennen Sie die Datei `Protos/greet.proto` in `Protos/portfolios.proto`um, und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="b90ce-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="b90ce-141">Löschen Sie alles nach der `package` Zeile.</span><span class="sxs-lookup"><span data-stu-id="b90ce-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="b90ce-142">Ändern Sie dann die Namen der `option csharp_namespace`, `package` und `service`, und entfernen Sie den Standard `SayHello` Dienst.</span><span class="sxs-lookup"><span data-stu-id="b90ce-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="b90ce-143">Der Code sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b90ce-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="b90ce-144">Die Vorlage fügt den `Protos` Namespace-Teil nicht standardmäßig hinzu. durch das hinzufügen wird jedoch die von GrpC generierten Klassen und ihre eigenen Klassen leichter in Ihren Code aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="b90ce-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="b90ce-145">Wenn Sie die `greet.proto` Datei in einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio umbenennen, wird ein Verweis auf diese Datei in der `.csproj`-Datei automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b90ce-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="b90ce-146">In einem anderen Editor, z. b. Visual Studio Code, wird dieser Verweis jedoch nicht automatisch aktualisiert, sodass Sie die Projektdatei manuell bearbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="b90ce-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="b90ce-147">In den GrpC-Build-Zielen gibt es ein `Protobuf` Item-Element, mit dem Sie angeben können, welche `.proto` Dateien kompiliert werden sollen und welche Form der Codegenerierung erforderlich ist (d. h. "Server" oder "Client").</span><span class="sxs-lookup"><span data-stu-id="b90ce-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="b90ce-148">Umbenennen der `GreeterService` Klasse</span><span class="sxs-lookup"><span data-stu-id="b90ce-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="b90ce-149">Die `GreeterService`-Klasse befindet sich im Ordner `Services` und erbt von `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="b90ce-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="b90ce-150">Benennen Sie es in `PortfolioService`um, und ändern Sie die Basisklasse in `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="b90ce-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="b90ce-151">Löschen Sie die `override` Methoden.</span><span class="sxs-lookup"><span data-stu-id="b90ce-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="b90ce-152">Es gab einen Verweis auf die `GreeterService`-Klasse in der `Configure`-Methode in der `Startup`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b90ce-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="b90ce-153">Wenn Sie Refactoring verwendet haben, um die Klasse umzubenennen, sollte diese Referenz automatisch aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b90ce-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="b90ce-154">Wenn dies nicht der Fall ist, müssen Sie Sie manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b90ce-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="b90ce-155">Im nächsten Abschnitt fügen wir diesem neuen Dienstfunktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b90ce-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b90ce-156">[Zurück](migrate-wcf-to-grpc.md)
>[Weiter](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="b90ce-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
