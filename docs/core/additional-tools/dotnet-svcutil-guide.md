---
title: Übersicht zum WCF-Tool „svcutil“
description: Übersicht zum Microsoft-WCF-Tool „dotnet-svcutil“, über das Funktionen für .NET Core- und ASP.NET Core-Projekte hinzugefügt werden, z.B. das WCF-Tool „svcutil“ für .NET Framework-Projekte.
author: mlacouture
ms.date: 02/22/2019
ms.openlocfilehash: 1f500c9355112183a135c2b639807c7cd62fbbfc
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021255"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a>WCF-Tool „dotnet-svcutil“ für .NET Core

Das **dotnet-svcutil**-Tool der Windows Communication Foundation (WCF) ist ein .NET-Tool, das Metadaten von einem Webdienst aus einem Netzwerkspeicherort oder einer WSDL-Datei abruft und eine WCF-Klasse mit Clientproxymethoden generiert, die auf Webdienstvorgänge zugreifen.

Ähnlich wie das [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)-Tool für .NET Framework-Projekte ist **dotnet-svcutil** ein Befehlszeilentool zum Generieren eines Webdienstverweises, der mit .NET Core- und .NET Standard-Projekten kompatibel ist.

Das Tool **dotnet-svcutil** ist eine alternative Option zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der zuerst in Visual Studio 2017 Version15.5 enthalten war. Das .NET-Tool **dotnet-svcutil** ist plattformübergreifend für Linux, macOS und Windows verfügbar.

> [!IMPORTANT]
> Sie sollten nur auf Dienste aus einer vertrauenswürdigen Quelle verweisen. Wenn Sie Verweise aus nicht vertrauenswürdigen Quellen hinzufügen, hat das möglicherweise Auswirkungen auf die Sicherheit.

## <a name="prerequisites"></a>Voraussetzungen

<!-- markdownlint-disable MD025 -->

# <a name="dotnet-svcutil-2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

- [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen
- Ihr bevorzugter Code-Editor

# <a name="dotnet-svcutil-1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)

- [.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen
- Ihr bevorzugter Code-Editor

---

## <a name="getting-started"></a>Erste Schritte

Das folgende Beispiel führt Sie durch die erforderlichen Schritte zum Hinzufügen eines Webdienstverweises zu einem .NET Core- Webprojekt und Aufrufen des Diensts. Sie erstellen eine .NET Core-Webanwendung mit dem Namen *HelloSvcutil* und fügen einen Verweis auf einen Webdienst hinzu, der folgenden Vertrag implementiert:

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

In diesem Beispiel wird angenommen, dass der Webdienst unter folgender Adresse gehostet wird: `http://contoso.com/SayHello.svc`.

Führen Sie in einem Windows-, macOS- oder Linux-Befehlsfenster die folgenden Schritte aus:

1. Erstellen Sie ein Verzeichnis mit dem Namen _HelloSvcutil_ für das Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis, wie im folgenden Beispiel:

    ```console
    mkdir HelloSvcutil
    cd HelloSvcutil
    ```

2. Erstellen Sie mithilfe des [`dotnet new`](../tools/dotnet-new.md)-Befehls wie folgt ein neues C#-Webprojekt in diesem Verzeichnis:

    ```dotnetcli
    dotnet new web
    ```

3. Installieren Sie das [`dotnet-svcutil` NuGet-Paket](https://nuget.org/packages/dotnet-svcutil) als CLI-Tool:  <!-- markdownlint-disable MD023 -->
    # <a name="dotnet-svcutil-2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet tool install --global dotnet-svcutil
    ```

    # <a name="dotnet-svcutil-1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)
    Öffnen Sie die `HelloSvcutil.csproj`-Projektdatei im Editor, bearbeiten Sie das `Project`-Element, und fügen Sie mithilfe des folgenden Codes das [`dotnet-svcutil`NuGet-Paket](https://nuget.org/packages/dotnet-svcutil) als CLI-Toolverweis hinzu:

    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
    </ItemGroup>
    ```

    Stellen Sie dann das _dotnet-svcutil_-Paket mithilfe des [`dotnet restore`](../tools/dotnet-restore.md)-Befehls wie folgt wieder her:

    ```dotnetcli
    dotnet restore
    ```

    ---

4. Führen Sie den Befehl _dotnet-svcutil_ aus, um die Webdienstverweisdatei zu generieren:

    # <a name="dotnet-svcutil-2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet-svcutil http://contoso.com/SayHello.svc
    ```

    # <a name="dotnet-svcutil-1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)

    ```dotnetcli
    dotnet svcutil http://contoso.com/SayHello.svc
    ```

    ---

Die generierte Datei wird als _HelloSvcutil/ServiceReference/Reference.cs_ gespeichert. Das _dotnet-svcutil_-Tool fügt dem Projekt auch die entsprechenden WCF-Pakete hinzu, die der Proxycode als Paketverweise benötigt.

## <a name="using-the-service-reference"></a>Verwenden des Dienstverweisnamens

1. Stellen Sie wie folgt die WCF-Pakete mithilfe des [`dotnet restore`](../tools/dotnet-restore.md)-Befehls wieder her:

    ```dotnetcli
    dotnet restore
    ```

2. Suchen Sie den Namen der Clientklasse und den Vorgang, den Sie verwenden möchten. `Reference.cs` enthält eine Klasse, die von `System.ServiceModel.ClientBase` erbt, mit Methoden, die zum Aufrufen von Vorgängen für den Dienst verwendet werden können. In diesem Beispiel rufen Sie den Vorgang _SayHello_ des Diensts _Hello_ auf. `ServiceReference.SayHelloClient` ist der Name der Clientklasse und hat eine Methode `HelloAsync` aufgerufen, die verwendet werden kann, um den Vorgang aufzurufen.

3. Öffnen Sie die `Startup.cs`-Datei in einem Editor, und fügen Sie eine using-Anweisung für den Dienstverweisnamespace oben hinzu:

    ```csharp
    using ServiceReference;
    ```

4. Bearbeiten Sie die `Configure`-Methode zum Aufrufen des Webdiensts. Hierzu erstellen Sie eine Instanz der Klasse, die von `ClientBase` erbt, und rufen die Methode für das Clientobjekt auf:

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
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

5. Führen Sie die Anwendung wie folgt mithilfe des [`dotnet run`](../tools/dotnet-run.md)-Befehls aus:

    ```dotnetcli
    dotnet run
    ```

6. Navigieren Sie in Ihrem Webbrowser zu der URL, die in der Konsole aufgelistet ist, (z.B. `http://localhost:5000`).

Sie sollten die folgende Ausgabe erhalten: „Hello dotnet-svcutil!“

Um eine ausführliche Beschreibung der Parameter des `dotnet-svcutil`-Tools zu erhalten, rufen Sie das Tool wie folgt mit Übergabe des Hilfeparameters auf:
# <a name="dotnet-svcutil-2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

```dotnetcli
dotnet-svcutil --help
```

# <a name="dotnet-svcutil-1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)

```dotnetcli
dotnet svcutil --help
```

---

## <a name="feedback--questions"></a>Feedback und Fragen

Wenn Sie Fragen haben oder uns Feedback geben möchten, [öffnen Sie ein Problem auf GitHub](https://github.com/dotnet/wcf/issues/new). Sie können außerdem bereits vorhandene Fragen oder Probleme [im WCF-Repository auf GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) überprüfen.

## <a name="release-notes"></a>Anmerkungen zu diesem Release

- Aktualisierte Informationen zu den einzelnen Versionen, einschließlich bekannter Probleme, finden Sie in den [Anmerkungen zu den jeweiligen Versionen](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md).

## <a name="information"></a>Information

- [dotnet-svcutil-NuGet-Paket](https://nuget.org/packages/dotnet-svcutil)
