---
title: Übersicht zum WCF-svcutil-Tool – .NET Core
description: Übersicht zum Microsoft-WCF-Tool „dotnet-svcutil“, über das Funktionen für .NET Core- und ASP.NET Core-Projekte hinzugefügt werden, z.B. das WCF-Tool „svcutil“ für .NET Framework-Projekte.
author: mlacouture
ms.author: jralexander
ms.date: 08/20/2018
ms.custom: seodec18
ms.openlocfilehash: 7372d88a9c1d77ec0b77e9d82fe5b24ebc357a74
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126015"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a>WCF-Tool „dotnet-svcutil“ für .NET Core

Das Windows Communication Foundation-Tool (WCF) **dotnet-svcutil** ist ein .NET Core-CLI-Tool, das Metadaten von einem Webdienst aus einem Netzwerkspeicherort oder einer WSDL-Datei abruft und eine WCF-Klasse mit Clientproxymethoden generiert, die Sie verwenden können, um auf die Webdienstvorgänge zuzugreifen.

Ähnlich wie das [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)-Tool für .NET Framework-Projekte ist **dotnet-svcutil** ein Befehlszeilentool zum Generieren eines Webdienstverweises, der mit .NET Core- und .NET Standard-Projekten kompatibel ist.

Das Tool **dotnet-svcutil** ist eine alternative Option zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der zuerst in Visual Studio 2017 Version15.5 enthalten war. Das Tool **dotnet-svcutil** ist plattformübergeifend als .NET Core-CLI-Tool unter Linux, macOS und Windows verfügbar.

> [!IMPORTANT]
> Sie sollten nur auf Dienste aus einer vertrauenswürdigen Quelle verweisen. Wenn Sie Verweise aus nicht vertrauenswürdigen Quellen hinzufügen, hat das möglicherweise Auswirkungen auf die Sicherheit.

## <a name="prerequisites"></a>Erforderliche Komponenten

* [.NET Core SDK](https://dotnet.microsoft.com/download), Version 1.0.4 oder höher
* Ihr bevorzugter Code-Editor

## <a name="getting-started"></a>Erste Schritte

Das folgende Beispiel führt Sie durch die erforderlichen Schritte zum Hinzufügen eines Webdienstverweises zu einem .NET Core- Konsolenprojekt und Aufrufen des Diensts. Sie erstellen eine .NET Core-Konsolenanwendung mit dem Namen _HelloSvcutil_ und fügen einen Verweis auf einen Webdienst hinzu, der folgenden Vertrag implementiert:

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

2. Erstellen Sie mithilfe des [`dotnet new`](../tools/dotnet-new.md)-Befehls wie folgt ein neues C#-Konsolenprojekt in diesem Verzeichnis:

```console
dotnet new console
```

3. Öffnen Sie die `HelloSvcutil.csproj`-Projektdatei im Editor, bearbeiten Sie das `Project`-Element, und fügen Sie mithilfe des folgenden Codes das [`dotnet-svcutil`NuGet-Paket](https://nuget.org/packages/dotnet-svcutil) als CLI-Toolverweis hinzu:

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. Stellen Sie das _dotnet-svcutil_-Paket mithilfe des [`dotnet restore`](../tools/dotnet-restore.md)-Befehls wie folgt wieder her:

```console
dotnet restore
```

5. Führen Sie wie folgt _dotnet_ mit dem Befehl _svcutil_ aus, um die Webdienstverweisdatei zu generieren:

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
Die generierte Datei wird als _HelloSvcutil/ServiceReference1/Reference.cs_ gespeichert. Das _dotnet_svcutil_-Tool fügt dem Projekt auch die entsprechenden WCF-Pakete hinzu, die der Proxycode als Paketverweise benötigt.

6. Stellen Sie wie folgt die WCF-Pakete mithilfe des [`dotnet restore`](../tools/dotnet-restore.md)-Befehls wieder her:

```console
dotnet restore
```

7. Öffnen Sie die `Program.cs`-Datei in einem Editor, bearbeiten Sie die `Main()`-Methode, und ersetzen Sie den automatisch generierten Code durch den folgenden Code, um den Webdienst aufzurufen:

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. Führen Sie die Anwendung wie folgt mithilfe des [`dotnet run`](../tools/dotnet-run.md)-Befehls aus:

```console
dotnet run
```
Sie sollten die folgende Ausgabe erhalten: „Hello dotnet-svcutil!“

Um eine ausführliche Beschreibung der Parameter des `dotnet-svcutil`-Tools zu erhalten, rufen Sie das Tool wie folgt mit Übergabe des Hilfeparameters auf:

```console
dotnet svcutil --help
```

## <a name="next-steps"></a>Nächste Schritte

### <a name="feedback--questions"></a>Feedback und Fragen

Wenn Sie Fragen haben oder uns Feedback geben möchten, [öffnen Sie ein Problem auf GitHub](https://github.com/dotnet/wcf/issues/new). Sie können außerdem bereits vorhandene Fragen oder Probleme [im WCF-Repository auf GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) überprüfen.

### <a name="release-notes"></a>Anmerkungen zu diesem Release

* Aktualisierte Informationen zu den einzelnen Versionen, einschließlich bekannter Probleme, finden Sie in den [Anmerkungen zu den jeweiligen Versionen](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md).

### <a name="information"></a>Information

* [dotnet-svcutil-NuGet-Paket](https://nuget.org/packages/dotnet-svcutil)
