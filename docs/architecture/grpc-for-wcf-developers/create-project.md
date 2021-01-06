---
title: 'Erstellen eines neuen ASP.net Core GrpC-Projekts: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie ein GrpC-Projekt mithilfe von Visual Studio oder der Befehlszeile erstellen.
ms.date: 12/15/2020
ms.openlocfilehash: 960725a9507797f43b2c15283e384b0ad827c2b1
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938654"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="f63b0-103">Erstellen eines neuen ASP.NET Core gRPC-Projekts</span><span class="sxs-lookup"><span data-stu-id="f63b0-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="f63b0-104">Das .NET SDK verfügt über ein leistungsfähiges CLI-Tool, `dotnet` das es Ihnen ermöglicht, Projekte und Projektmappen über die Befehlszeile zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f63b0-104">The .NET SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="f63b0-105">Das SDK ist eng in Visual Studio integriert, sodass alles auch über die vertraute grafische Benutzeroberfläche verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f63b0-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="f63b0-106">Dieses Kapitel zeigt beide Möglichkeiten zum Erstellen eines neuen ASP.net Core GrpC-Projekts.</span><span class="sxs-lookup"><span data-stu-id="f63b0-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="f63b0-107">Erstellen des Projekts mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f63b0-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f63b0-108">Zum Entwickeln einer ASP.net Core 5,0-App benötigen Sie Visual Studio 2019 Version 16,3 oder höher mit installierter **ASP.net-und Webentwicklungs-** Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="f63b0-108">To develop any ASP.NET Core 5.0 app, you need Visual Studio 2019 version 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="f63b0-109">Erstellen Sie eine leere Projekt Mappe mit dem Namen **tradersys** aus der Vorlage *leere* Projekt Mappe.</span><span class="sxs-lookup"><span data-stu-id="f63b0-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="f63b0-110">Fügen Sie einen Lösungs Ordner mit dem Namen hinzu `src` .</span><span class="sxs-lookup"><span data-stu-id="f63b0-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="f63b0-111">Klicken Sie dann mit der rechten Maustaste auf den Ordner , und wählen Sie  >  **Neues Projekt** hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="f63b0-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="f63b0-112">Geben `grpc` Sie im Feld für die Vorlagen Suche ein, und Sie sollten eine Projektvorlage mit dem Namen sehen `gRPC Service` .</span><span class="sxs-lookup"><span data-stu-id="f63b0-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Screenshot des Dialog Felds "Neues Projekt hinzufügen"](media/create-project/new-grpc-project.png)

<span data-ttu-id="f63b0-114">Wählen **Sie weiter aus** , um mit dem Dialogfeld **Neues Projekt konfigurieren** fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="f63b0-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="f63b0-115">Benennen Sie das Projekt `TraderSys.Portfolios` , und fügen Sie `src` dem **Speicherort** ein Unterverzeichnis hinzu.</span><span class="sxs-lookup"><span data-stu-id="f63b0-115">Name the project `TraderSys.Portfolios` and add an `src` subdirectory to the **Location**.</span></span>

![Screenshot des Dialog Felds "Neues Projekt konfigurieren"](media/create-project/configure-project.png)

<span data-ttu-id="f63b0-117">Wählen **Sie weiter aus** , um mit dem Dialogfeld **neuen GrpC-Dienst erstellen** fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="f63b0-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Screenshot des Dialog Felds "neuen GrpC-Dienst erstellen"](media/create-project/create-new-grpc-service-v2.png)

<span data-ttu-id="f63b0-119">Derzeit haben Sie eingeschränkte Optionen für die Dienst Erstellung.</span><span class="sxs-lookup"><span data-stu-id="f63b0-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="f63b0-120">Docker wird später eingeführt, lassen Sie diese Option vorerst deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f63b0-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="f63b0-121">Wählen Sie einfach **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f63b0-121">Just select **Create**.</span></span> <span data-ttu-id="f63b0-122">Ihr erstes ASP.net Core 5,0-GrpC-Projekt wird generiert und der Projekt Mappe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f63b0-122">Your first ASP.NET Core 5.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="f63b0-123">Wenn Sie nicht wissen möchten, wie Sie mit arbeiten, fahren Sie mit `dotnet CLI` dem Abschnitt [Bereinigen des Beispielcodes](#clean-up-the-example-code) fort.</span><span class="sxs-lookup"><span data-stu-id="f63b0-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-cli"></a><span data-ttu-id="f63b0-124">Erstellen des Projekts mithilfe der .net-CLI</span><span class="sxs-lookup"><span data-stu-id="f63b0-124">Create the project by using the .NET CLI</span></span>

<span data-ttu-id="f63b0-125">In diesem Abschnitt wird die Erstellung von Projektmappen und Projekten von der Befehlszeile aus behandelt.</span><span class="sxs-lookup"><span data-stu-id="f63b0-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="f63b0-126">Erstellen Sie die Projekt Mappe, wie im folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f63b0-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="f63b0-127">Das `-o` Flag (oder `--output` ) gibt das Ausgabeverzeichnis an, das im aktuellen Verzeichnis erstellt wird, wenn es nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f63b0-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="f63b0-128">Die Lösung weist den gleichen Namen wie das Verzeichnis auf: `TraderSys.sln` .</span><span class="sxs-lookup"><span data-stu-id="f63b0-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="f63b0-129">Sie können einen anderen Namen angeben, indem Sie das- `-n` Flag (oder `--name` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f63b0-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="f63b0-130">In ASP.net Core 5,0 ist eine CLI-Vorlage für GrpC-Dienste verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f63b0-130">ASP.NET Core 5.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="f63b0-131">Erstellen Sie das neue Projekt mithilfe dieser Vorlage, und platzieren Sie es in einem `src` Unterverzeichnis, das für ASP.net Core Projekte konventionell ist.</span><span class="sxs-lookup"><span data-stu-id="f63b0-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="f63b0-132">Das Projekt wird nach dem Verzeichnis ( `TraderSys.Portfolios.csproj` ) benannt, es sei denn, Sie geben einen anderen Namen mit dem- `-n` Flag an.</span><span class="sxs-lookup"><span data-stu-id="f63b0-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="f63b0-133">Fügen Sie schließlich das Projekt der Projekt Mappe hinzu, indem Sie den folgenden `dotnet sln` Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="f63b0-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="f63b0-134">Da das jeweilige Verzeichnis nur eine einzelne `.csproj` Datei enthält, können Sie nur das Verzeichnis angeben, um die Eingabe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f63b0-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="f63b0-135">Sie können diese Projekt Mappe jetzt in Visual Studio 2019, Visual Studio Code oder einem beliebigen Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="f63b0-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="f63b0-136">Bereinigen des Beispielcodes</span><span class="sxs-lookup"><span data-stu-id="f63b0-136">Clean up the example code</span></span>

<span data-ttu-id="f63b0-137">Sie haben nun einen Beispiel Dienst mithilfe der GrpC-Vorlage erstellt, die weiter oben im Buch erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="f63b0-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="f63b0-138">Dieser Code ist in unserem Aktienhandels Kontext nicht nützlich, daher bearbeiten wir die Dinge für unser erstes Projekt.</span><span class="sxs-lookup"><span data-stu-id="f63b0-138">This code isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="f63b0-139">Umbenennen und Bearbeiten der Proto-Datei</span><span class="sxs-lookup"><span data-stu-id="f63b0-139">Rename and edit the proto file</span></span>

<span data-ttu-id="f63b0-140">Benennen `Protos/greet.proto` Sie die Datei `Protos/portfolios.proto` in um, und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="f63b0-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="f63b0-141">Löschen Sie alles nach der `package` Zeile.</span><span class="sxs-lookup"><span data-stu-id="f63b0-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="f63b0-142">Ändern Sie dann `option csharp_namespace` die `package` Namen, und `service` , und entfernen Sie den Standard `SayHello` Dienst.</span><span class="sxs-lookup"><span data-stu-id="f63b0-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="f63b0-143">Der Code sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f63b0-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="f63b0-144">Die Vorlage fügt den `Protos` Namespace Teil nicht standardmäßig hinzu. durch das hinzufügen wird jedoch die von GrpC generierten Klassen und ihre eigenen Klassen leichter in Ihren Code aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="f63b0-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="f63b0-145">Wenn Sie die `greet.proto` Datei in einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio umbenennen, wird ein Verweis auf diese Datei in der Datei automatisch aktualisiert `.csproj` .</span><span class="sxs-lookup"><span data-stu-id="f63b0-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="f63b0-146">In einem anderen Editor, z. b. Visual Studio Code, wird dieser Verweis jedoch nicht automatisch aktualisiert, sodass Sie die Projektdatei manuell bearbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="f63b0-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="f63b0-147">In den GrpC-Build-Zielen gibt es ein `Protobuf` Element Element, mit dem Sie angeben können `.proto` , welche Dateien kompiliert werden sollen und welche Form der Codegenerierung erforderlich ist (d. h. "Server" oder "Client").</span><span class="sxs-lookup"><span data-stu-id="f63b0-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="f63b0-148">Umbenennen der `GreeterService` Klasse</span><span class="sxs-lookup"><span data-stu-id="f63b0-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="f63b0-149">Die `GreeterService` -Klasse befindet sich im `Services` -Ordner und erbt von `Greeter.GreeterBase` .</span><span class="sxs-lookup"><span data-stu-id="f63b0-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="f63b0-150">Benennen Sie `PortfolioService` die Klasse in um, und ändern Sie die Basisklasse in `Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="f63b0-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="f63b0-151">Löschen Sie die- `override` Methoden.</span><span class="sxs-lookup"><span data-stu-id="f63b0-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="f63b0-152">Es gab einen Verweis auf die- `GreeterService` Klasse in der- `Configure` Methode in der- `Startup` Klasse.</span><span class="sxs-lookup"><span data-stu-id="f63b0-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="f63b0-153">Wenn Sie Refactoring verwendet haben, um die Klasse umzubenennen, sollte diese Referenz automatisch aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f63b0-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="f63b0-154">Wenn dies nicht der Fall ist, müssen Sie Sie manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f63b0-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="f63b0-155">Im nächsten Abschnitt fügen wir diesem neuen Dienstfunktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="f63b0-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f63b0-156">[Zurück](migrate-wcf-to-grpc.md)
>[Weiter](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="f63b0-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
