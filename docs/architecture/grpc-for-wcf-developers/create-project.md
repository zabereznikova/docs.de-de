---
title: 'Erstellen eines neuen ASP.net Core GrpC-Projekts: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie ein GrpC-Projekt mithilfe von Visual Studio oder über die Befehlszeile erstellen.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: a30d19e1e48692ad68a648406d4bf369937744d7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841660"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>Erstellen eines neuen ASP.NET Core gRPC-Projekts

.Net Core verfügt über ein leistungsfähiges CLI-Tool, `dotnet`, das es Ihnen ermöglicht, Projekte und Projektmappen über die Befehlszeile zu erstellen und zu verwalten. Das Tool ist eng in Visual Studio integriert, sodass alles auch über die vertraute GUI-Oberfläche verfügbar ist. In diesem Kapitel werden beide Methoden zum Erstellen eines neuen ASP.net Core GrpC-Projekts gezeigt: zuerst mit Visual Studio, dann mit dem .net Core-CLI.

## <a name="create-the-project-using-visual-studio"></a>Erstellen des Projekts mit Visual Studio

> [!IMPORTANT]
> Zum Entwickeln einer ASP.net Core 3,0-App benötigen Sie Visual Studio 2019,3 oder höher mit installierter **ASP.net-und Webentwicklungs-** Arbeitsauslastung.

Erstellen Sie eine leere Projekt Mappe mit dem Namen **tradersys** aus der Vorlage *leere* Projekt Mappe. Fügen Sie einen Projektmappenordner namens `src`hinzu, klicken Sie mit der rechten Maustaste auf den Ordner, und wählen Sie im Kontextmenü > **Neues Projekt** **Hinzufügen** aus. Geben Sie im Feld für die Vorlagen Suche `grpc` ein, und Sie sollten eine Projektvorlage mit dem Namen `gRPC Service`sehen.

![Dialogfeld "Neues Projekt hinzufügen" mit der Projektvorlage "GrpC](media/create-project/new-grpc-project.png)

Klicken Sie auf weiter **, um mit** dem Dialogfeld **Projekt konfigurieren** fortzufahren, benennen Sie das Projekt `TraderSys.Portfolios`, und fügen Sie dem **Speicherort**ein `src` Unterverzeichnis hinzu.

![Dialogfeld "Projekt konfigurieren](media/create-project/configure-project.png)

Klicken **Sie auf weiter** , um zum Dialogfeld **Neues GrpC-Projekt** zu klicken.

![Neues GrpC-Projekt Dialogfeld](media/create-project/create-new-grpc-service.png)

Derzeit sind für die Dienst Erstellung begrenzte Optionen verfügbar. Docker wird später im Buch eingeführt, lassen Sie das Kontrollkästchen jetzt deaktiviert, und klicken Sie auf **Erstellen**. Ihr erstes ASP.net Core 3,0-GrpC-Projekt wird generiert und der Projekt Mappe hinzugefügt. Wenn Sie nicht wissen möchten, wie Sie mit dem `dotnet CLI`arbeiten, fahren Sie mit dem Abschnitt [Bereinigen des Beispielcodes](#clean-up-the-example-code) fort.

## <a name="create-the-project-using-the-net-core-cli"></a>Erstellen Sie das Projekt mit dem .net Core-CLI

In diesem Abschnitt wird die Erstellung von Projektmappen und Projekten von der Befehlszeile aus behandelt.

Erstellen Sie die Lösung wie unten gezeigt. Das Flag `-o` (oder `--output`) gibt das Ausgabeverzeichnis an, das im aktuellen Verzeichnis erstellt wird, wenn es nicht vorhanden ist. Die Lösung erhält denselben Namen wie das Verzeichnis, d. h. `TraderSys.sln`. Mit dem `-n`-Flag (oder `--name`) können Sie einen anderen Namen angeben.

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

In ASP.net Core 3,0 ist eine CLI-Vorlage für GrpC-Dienste verfügbar. Erstellen Sie das neue Projekt mithilfe dieser Vorlage, und legen Sie es in einem `src` Unterverzeichnis ab, das der Konvention für ASP.net Core Projekte entspricht. Das Projekt wird nach dem Verzeichnis benannt (d. h. `TraderSys.Portfolios.csproj`), es sei denn, Sie geben einen anderen Namen mit dem `-n`-Flag an.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Fügen Sie schließlich das Projekt der Projekt Mappe mit dem Befehl `dotnet sln` hinzu.

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Da das angegebene Verzeichnis nur eine einzige `.csproj` Datei enthält, können Sie mit der Angabe des Verzeichnisses, in dem die Typisierung gespeichert wird, nicht nur das Verzeichnis angeben.

Sie können diese Projekt Mappe jetzt in Visual Studio 2019, Visual Studio Code oder einem beliebigen Editor öffnen.

## <a name="clean-up-the-example-code"></a>Bereinigen des Beispielcodes

Sie haben nun einen Beispiel Dienst mithilfe der GrpC-Vorlage erstellt, die weiter oben im Buch erläutert wurde. Dies ist in unserem Aktienhandels Kontext nicht nützlich, daher bearbeiten wir die Dinge für unser erstes Projekt.

### <a name="rename-and-edit-the-proto-file"></a>Umbenennen und Bearbeiten der Proto-Datei

Benennen Sie die Datei `Protos/greet.proto` in `Protos/portfolios.proto` um, und öffnen Sie Sie im Editor. Löschen Sie alles nach der `package` Zeile, ändern Sie die Namen der `option csharp_namespace`, `package` und `service`, und entfernen Sie den Standard-`SayHello` Dienst, sodass der Code wie folgt aussieht.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> Die Vorlage fügt den `Protos` Namespace-Teil nicht standardmäßig hinzu. durch das hinzufügen wird jedoch die von GrpC generierten Klassen und ihre eigenen Klassen leichter in Ihren Code aufgeteilt.

Wenn Sie die `greet.proto` Datei in einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio umbenennen, wird ein Verweis auf diese Datei in der `.csproj`-Datei automatisch aktualisiert. In einem anderen Editor, z. b. Visual Studio Code, wird dieser Verweis jedoch nicht automatisch aktualisiert, sodass Sie die Projektdatei manuell bearbeiten müssen.

In den GrpC-Build-Zielen gibt es ein `Protobuf` Item-Element, mit dem Sie angeben können, welche `.proto` Dateien kompiliert werden sollen und welche Form der Codegenerierung erforderlich ist (d. h. "Server" oder "Client").

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>Umbenennen der greeterservice-Klasse

Die `GreeterService`-Klasse befindet sich im Ordner `Services` und erbt von `Greeter.GreeterBase`. Benennen Sie es in `PortfolioService` um, und ändern Sie die Basisklasse in `Portfolios.PortfoliosBase`. Löschen Sie die `override` Methoden.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

Es gab einen Verweis auf die `GreeterService`-Klasse in der `Configure`-Methode in der `Startup`-Klasse. Wenn Sie Refactoring verwendet haben, um die Klasse umzubenennen, sollte diese Referenz automatisch aktualisiert werden. Wenn dies nicht der Fall ist, müssen Sie Sie manuell bearbeiten.

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

Im nächsten Abschnitt fügen wir diesem neuen Dienstfunktionen hinzu.

>[!div class="step-by-step"]
>[Zurück](migrate-wcf-to-grpc.md)
>[Weiter](migrate-request-reply.md)
