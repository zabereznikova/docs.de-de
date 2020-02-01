---
title: 'Erstellen eines neuen ASP.net Core GrpC-Projekts: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie ein GrpC-Projekt mithilfe von Visual Studio oder der Befehlszeile erstellen.
ms.date: 09/02/2019
ms.openlocfilehash: fbcc598cf503a5baeca941803ff8fa0d5fc99671
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919410"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>Erstellen eines neuen ASP.NET Core gRPC-Projekts

Die .net Core SDK verfügt über ein leistungsfähiges CLI-Tool `dotnet`, mit dem Sie Projekte und Projektmappen über die Befehlszeile erstellen und verwalten können. Das SDK ist eng in Visual Studio integriert, sodass alles auch über die vertraute grafische Benutzeroberfläche verfügbar ist. Dieses Kapitel zeigt beide Möglichkeiten zum Erstellen eines neuen ASP.net Core GrpC-Projekts.

## <a name="create-the-project-by-using-visual-studio"></a>Erstellen des Projekts mithilfe von Visual Studio

> [!IMPORTANT]
> Zum Entwickeln einer ASP.net Core 3,0-App benötigen Sie Visual Studio 2019 Version 16,3 oder höher mit installierter **ASP.net-und Webentwicklungs-** Arbeitsauslastung.

Erstellen Sie eine leere Projekt Mappe mit dem Namen **tradersys** aus der Vorlage *leere* Projekt Mappe. Fügen Sie einen Projektmappenordner namens `src`hinzu. Klicken Sie dann mit der rechten Maustaste auf den Ordner, und wählen Sie > **Neues Projekt** **Hinzufügen** aus. Geben Sie im Feld für die Vorlagen Suche `grpc` ein, und Sie sollten eine Projektvorlage mit dem Namen `gRPC Service`sehen.

![Screenshot des Dialog Felds "Neues Projekt hinzufügen"](media/create-project/new-grpc-project.png)

Wählen **Sie weiter aus** , um mit dem Dialogfeld **Neues Projekt konfigurieren** fortzufahren. Benennen Sie das Projekt `TraderSys.Portfolios`, und fügen Sie dem **Speicherort**ein `src` Unterverzeichnis hinzu.

![Screenshot des Dialog Felds "Neues Projekt konfigurieren"](media/create-project/configure-project.png)

Wählen **Sie weiter aus** , um mit dem Dialogfeld **neuen GrpC-Dienst erstellen** fortzufahren.

![Screenshot des Dialog Felds "neuen GrpC-Dienst erstellen"](media/create-project/create-new-grpc-service.png)

Derzeit haben Sie eingeschränkte Optionen für die Dienst Erstellung. Docker wird später eingeführt, lassen Sie diese Option vorerst deaktiviert. Wählen Sie einfach **Erstellen**aus. Ihr erstes ASP.net Core 3,0-GrpC-Projekt wird generiert und der Projekt Mappe hinzugefügt. Wenn Sie nicht wissen möchten, wie Sie mit dem `dotnet CLI`arbeiten, fahren Sie mit dem Abschnitt [Bereinigen des Beispielcodes](#clean-up-the-example-code) fort.

## <a name="create-the-project-by-using-the-net-core-cli"></a>Erstellen Sie das Projekt mithilfe des .net Core-CLI

In diesem Abschnitt wird die Erstellung von Projektmappen und Projekten von der Befehlszeile aus behandelt.

Erstellen Sie die Projekt Mappe, wie im folgenden Befehl gezeigt. Das Flag `-o` (oder `--output`) gibt das Ausgabeverzeichnis an, das im aktuellen Verzeichnis erstellt wird, wenn es nicht bereits vorhanden ist. Die Projekt Mappe hat denselben Namen wie das Verzeichnis: `TraderSys.sln`. Sie können einen anderen Namen angeben, indem Sie das Flag `-n` (oder `--name`) verwenden.

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

In ASP.net Core 3,0 ist eine CLI-Vorlage für GrpC-Dienste verfügbar. Erstellen Sie das neue Projekt mithilfe dieser Vorlage, und platzieren Sie es in einem `src` Unterverzeichnis, das für ASP.net Core Projekte konventionell ist. Das Projekt wird nach dem Verzeichnis (`TraderSys.Portfolios.csproj`) benannt, es sei denn, Sie geben einen anderen Namen mit dem `-n`-Flag an.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Fügen Sie schließlich das Projekt der Projekt Mappe hinzu, indem Sie den `dotnet sln`-Befehl verwenden:

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Da das jeweilige Verzeichnis nur eine einzige `.csproj` Datei enthält, können Sie nur das Verzeichnis angeben, um die Typisierung zu speichern.

Sie können diese Projekt Mappe jetzt in Visual Studio 2019, Visual Studio Code oder einem beliebigen Editor öffnen.

## <a name="clean-up-the-example-code"></a>Bereinigen des Beispielcodes

Sie haben nun einen Beispiel Dienst mithilfe der GrpC-Vorlage erstellt, die weiter oben im Buch erläutert wurde. Dies ist in unserem Aktienhandels Kontext nicht nützlich, daher bearbeiten wir die Dinge für unser erstes Projekt.

### <a name="rename-and-edit-the-proto-file"></a>Umbenennen und Bearbeiten der Proto-Datei

Benennen Sie die Datei `Protos/greet.proto` in `Protos/portfolios.proto`um, und öffnen Sie Sie im Editor. Löschen Sie alles nach der `package` Zeile. Ändern Sie dann die Namen der `option csharp_namespace`, `package` und `service`, und entfernen Sie den Standard `SayHello` Dienst. Der Code sieht nun wie folgt aus:

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

### <a name="rename-the-greeterservice-class"></a>Umbenennen der `GreeterService` Klasse

Die `GreeterService`-Klasse befindet sich im Ordner `Services` und erbt von `Greeter.GreeterBase`. Benennen Sie es in `PortfolioService`um, und ändern Sie die Basisklasse in `Portfolios.PortfoliosBase`. Löschen Sie die `override` Methoden.

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
