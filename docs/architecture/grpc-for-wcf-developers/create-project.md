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
# <a name="create-a-new-aspnet-core-grpc-project"></a>Erstellen eines neuen ASP.NET Core gRPC-Projekts

Das .NET SDK verfügt über ein leistungsfähiges CLI-Tool, `dotnet` das es Ihnen ermöglicht, Projekte und Projektmappen über die Befehlszeile zu erstellen und zu verwalten. Das SDK ist eng in Visual Studio integriert, sodass alles auch über die vertraute grafische Benutzeroberfläche verfügbar ist. Dieses Kapitel zeigt beide Möglichkeiten zum Erstellen eines neuen ASP.net Core GrpC-Projekts.

## <a name="create-the-project-by-using-visual-studio"></a>Erstellen des Projekts mithilfe von Visual Studio

> [!IMPORTANT]
> Zum Entwickeln einer ASP.net Core 5,0-App benötigen Sie Visual Studio 2019 Version 16,3 oder höher mit installierter **ASP.net-und Webentwicklungs-** Arbeitsauslastung.

Erstellen Sie eine leere Projekt Mappe mit dem Namen **tradersys** aus der Vorlage *leere* Projekt Mappe. Fügen Sie einen Lösungs Ordner mit dem Namen hinzu `src` . Klicken Sie dann mit der rechten Maustaste auf den Ordner , und wählen Sie  >  **Neues Projekt** hinzufügen aus. Geben `grpc` Sie im Feld für die Vorlagen Suche ein, und Sie sollten eine Projektvorlage mit dem Namen sehen `gRPC Service` .

![Screenshot des Dialog Felds "Neues Projekt hinzufügen"](media/create-project/new-grpc-project.png)

Wählen **Sie weiter aus** , um mit dem Dialogfeld **Neues Projekt konfigurieren** fortzufahren. Benennen Sie das Projekt `TraderSys.Portfolios` , und fügen Sie `src` dem **Speicherort** ein Unterverzeichnis hinzu.

![Screenshot des Dialog Felds "Neues Projekt konfigurieren"](media/create-project/configure-project.png)

Wählen **Sie weiter aus** , um mit dem Dialogfeld **neuen GrpC-Dienst erstellen** fortzufahren.

![Screenshot des Dialog Felds "neuen GrpC-Dienst erstellen"](media/create-project/create-new-grpc-service-v2.png)

Derzeit haben Sie eingeschränkte Optionen für die Dienst Erstellung. Docker wird später eingeführt, lassen Sie diese Option vorerst deaktiviert. Wählen Sie einfach **Erstellen** aus. Ihr erstes ASP.net Core 5,0-GrpC-Projekt wird generiert und der Projekt Mappe hinzugefügt. Wenn Sie nicht wissen möchten, wie Sie mit arbeiten, fahren Sie mit `dotnet CLI` dem Abschnitt [Bereinigen des Beispielcodes](#clean-up-the-example-code) fort.

## <a name="create-the-project-by-using-the-net-cli"></a>Erstellen des Projekts mithilfe der .net-CLI

In diesem Abschnitt wird die Erstellung von Projektmappen und Projekten von der Befehlszeile aus behandelt.

Erstellen Sie die Projekt Mappe, wie im folgenden Befehl gezeigt. Das `-o` Flag (oder `--output` ) gibt das Ausgabeverzeichnis an, das im aktuellen Verzeichnis erstellt wird, wenn es nicht bereits vorhanden ist. Die Lösung weist den gleichen Namen wie das Verzeichnis auf: `TraderSys.sln` . Sie können einen anderen Namen angeben, indem Sie das- `-n` Flag (oder `--name` ) verwenden.

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

In ASP.net Core 5,0 ist eine CLI-Vorlage für GrpC-Dienste verfügbar. Erstellen Sie das neue Projekt mithilfe dieser Vorlage, und platzieren Sie es in einem `src` Unterverzeichnis, das für ASP.net Core Projekte konventionell ist. Das Projekt wird nach dem Verzeichnis ( `TraderSys.Portfolios.csproj` ) benannt, es sei denn, Sie geben einen anderen Namen mit dem- `-n` Flag an.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Fügen Sie schließlich das Projekt der Projekt Mappe hinzu, indem Sie den folgenden `dotnet sln` Befehl verwenden:

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Da das jeweilige Verzeichnis nur eine einzelne `.csproj` Datei enthält, können Sie nur das Verzeichnis angeben, um die Eingabe zu speichern.

Sie können diese Projekt Mappe jetzt in Visual Studio 2019, Visual Studio Code oder einem beliebigen Editor öffnen.

## <a name="clean-up-the-example-code"></a>Bereinigen des Beispielcodes

Sie haben nun einen Beispiel Dienst mithilfe der GrpC-Vorlage erstellt, die weiter oben im Buch erläutert wurde. Dieser Code ist in unserem Aktienhandels Kontext nicht nützlich, daher bearbeiten wir die Dinge für unser erstes Projekt.

### <a name="rename-and-edit-the-proto-file"></a>Umbenennen und Bearbeiten der Proto-Datei

Benennen `Protos/greet.proto` Sie die Datei `Protos/portfolios.proto` in um, und öffnen Sie Sie im Editor. Löschen Sie alles nach der `package` Zeile. Ändern Sie dann `option csharp_namespace` die `package` Namen, und `service` , und entfernen Sie den Standard `SayHello` Dienst. Der Code sieht nun wie folgt aus:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> Die Vorlage fügt den `Protos` Namespace Teil nicht standardmäßig hinzu. durch das hinzufügen wird jedoch die von GrpC generierten Klassen und ihre eigenen Klassen leichter in Ihren Code aufgeteilt.

Wenn Sie die `greet.proto` Datei in einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio umbenennen, wird ein Verweis auf diese Datei in der Datei automatisch aktualisiert `.csproj` . In einem anderen Editor, z. b. Visual Studio Code, wird dieser Verweis jedoch nicht automatisch aktualisiert, sodass Sie die Projektdatei manuell bearbeiten müssen.

In den GrpC-Build-Zielen gibt es ein `Protobuf` Element Element, mit dem Sie angeben können `.proto` , welche Dateien kompiliert werden sollen und welche Form der Codegenerierung erforderlich ist (d. h. "Server" oder "Client").

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>Umbenennen der `GreeterService` Klasse

Die `GreeterService` -Klasse befindet sich im `Services` -Ordner und erbt von `Greeter.GreeterBase` . Benennen Sie `PortfolioService` die Klasse in um, und ändern Sie die Basisklasse in `Portfolios.PortfoliosBase` . Löschen Sie die- `override` Methoden.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

Es gab einen Verweis auf die- `GreeterService` Klasse in der- `Configure` Methode in der- `Startup` Klasse. Wenn Sie Refactoring verwendet haben, um die Klasse umzubenennen, sollte diese Referenz automatisch aktualisiert werden. Wenn dies nicht der Fall ist, müssen Sie Sie manuell bearbeiten.

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
