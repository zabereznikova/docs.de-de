---
title: In Docker gehostete Microservices – C#
description: Erfahren Sie, wie Sie ASP.NET Core-Dienste erstellen, die in Docker-Containern ausgeführt werden.
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 1f4b38243beb1210b1374bd701fac66b2fa72cc5
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106349"
---
# <a name="microservices-hosted-in-docker"></a>In Docker gehostete Microservices

In diesem Tutorial werden die erforderlichen Aufgaben zum Erstellen und Bereitstellen eines ASP.NET Core-Microservice in einem Docker-Container erläutert. Im Verlauf dieses Tutorials lernen Sie Folgendes:

* Erstellen einer ASP.NET Core-Anwendung
* Erstellen einer Docker-Entwicklungsumgebung
* Erstellen eines Docker-Images basierend auf einem vorhandenen Image
* Bereitstellen Ihres Diensts in einem Docker-Container

Dabei lernen Sie auch einige C#-Sprachfunktionen kennen:

* Konvertieren von C#-Objekten in JSON-Nutzlasten
* Erstellen unveränderlicher Datenübertragungsobjekte
* Verarbeiten eingehender HTTP-Anforderungen und Erstellen der HTTP-Antwort
* Arbeiten mit Nullable-Werttypen

Sie können die Beispiel-App für dieses Thema [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="why-docker"></a>Warum Docker?

Docker erleichtert das Erstellen von standardmäßigen Computerimages zum Hosten Ihrer Dienste in einem Rechenzentrum oder der öffentlichen Cloud. Mit Docker können Sie das Image konfigurieren und nach Bedarf replizieren, um die Installation der Anwendung zu skalieren.

Der gesamte Code in diesem Tutorial ist in einer beliebigen .NET Core-Umgebung einsetzbar.
Die zusätzlichen Aufgaben für eine Docker-Installation funktionieren in Verbindung mit einer ASP.NET Core-Anwendung. 

## <a name="prerequisites"></a>Erforderliche Komponenten

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).
Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.
Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

Sie müssen auch die Docker-Engine installieren. Anweisungen für Ihre Plattform finden Sie auf der [Docker-Installationsseite](http://www.docker.com/products/docker).
Docker kann in vielen Linux-Distributionen, unter macOS oder Windows installiert werden. Die oben erwähnte Seite enthält Abschnitte zu jeder verfügbaren Installation.

## <a name="create-the-application"></a>Erstellen der Anwendung

Da Sie nun alle Tools installiert haben, erstellen Sie eine neue ASP.NET Core-Anwendung in einem Verzeichnis namens „WeatherMicroservice“, indem Sie den folgenden Befehl in Ihrer bevorzugten Shell ausführen:

```console
dotnet new web -o WeatherMicroservice
```

Der `dotnet`-Befehl führt die erforderlichen Tools für die .NET-Entwicklung aus. Jedes Verb führt einen anderen Befehl aus.

Mit dem `dotnet new`-Befehl werden .NET Core-Projekte erstellt.

Die Option `-o WeatherMicroservice` nach dem Befehl `dotnet new` wird verwendet, um den Speicherort für die Erstellung der ASP.NET Core-Anwendung anzugeben.

Da für diesen Microservice eine möglichst einfache und kompakte Webanwendung zum Einsatz kommen soll, wurde die Vorlage „ASP.NET Core leer“ durch Angabe des Kurznamens `web` verwendet.

Die Vorlage erstellt vier Dateien:

* Eine Startup.cs-Datei. Diese enthält die Grundlage für die Anwendung.
* Eine Program.cs-Datei. Diese enthält den Einstiegspunkt für die Anwendung.
* Eine WeatherMicroservice.csproj-Datei. Dies ist die Build-Datei für die Anwendung.
* Die Datei „launchSettings.json“ im Ordner „Properties“. Diese enthält von IDEs verwendete Debugeinstellungen.

Jetzt können Sie die von der Vorlage generierte Anwendung ausführen:

```console
dotnet run
```

Durch diesen Befehl werden zuerst die Abhängigkeiten wiederhergestellt, die zur Erstellung der Anwendung benötigt werden. Anschließend wird die Anwendung erstellt.

Die Standardkonfiguration lauscht auf `http://localhost:5000`. Wenn Sie den Browser öffnen und zu dieser Seite navigieren, sehen Sie ein „Hello World!“. Vorgang nicht gefunden werden konnte.

Abschließend können Sie die Anwendung beenden, indem Sie <kbd>STRG</kbd>+<kbd>C</kbd> drücken.

### <a name="anatomy-of-an-aspnet-core-application"></a>Anatomie einer ASP.NET Core-Anwendung

Da Sie jetzt die Anwendung erstellt haben, können wir nun die Implementierung dieser Funktionalität betrachten. Zwei der generierten Dateien sind hier besonders interessant: „WeatherMicroservice.csproj“ und „Startup.cs“. 

Die CSPROJ-Datei enthält Informationen zum Projekt.
Besonders interessant sind die beiden Knoten `<TargetFramework>` und `<PackageReference>`.

Im Knoten `<TargetFramework>` wird die Version von .NET festgelegt, unter der diese Anwendung ausgeführt wird.

Mit den `<PackageReference>`-Knoten werden Pakete angegeben, die für diese Anwendung erforderlich sind.

Die Anwendung wird in „Startup.cs“ implementiert. Diese Datei enthält die Startklasse.

Die beiden Methoden werden von der ASP.NET Core-Infrastruktur zum Konfigurieren und Ausführen der Anwendung aufgerufen. Die `ConfigureServices`-Methode beschreibt die Dienste, die für diese Anwendung erforderlich sind. Sie erstellen einen einfachen Microservice, sodass keine Abhängigkeiten konfiguriert werden müssen. Die `Configure`-Methode konfiguriert die Handler für eingehende HTTP-Anforderungen. Die Vorlage erstellt einen einfachen Handler, der auf jede Anforderung mit dem Text „Hello World!“ reagiert.

## <a name="build-a-microservice"></a>Erstellen eines Microservice

Sie werden einen Dienst erstellen, der Wetterberichte aus aller Welt bereitstellt. In einer Produktionsanwendung würden Sie einen Dienst aufrufen, um Wetterdaten abzurufen. In diesem Beispiel generieren wir einen zufälligen Wetterbericht. 

Sie müssen eine Reihe von Aufgaben ausführen, um unseren zufälligen Wetterdienst zu implementieren:

* Analysieren der eingehenden Anforderung, um den Breiten- und Längengrad zu lesen.
* Generieren einiger zufälliger Vorhersagedaten.
* Konvertieren dieser zufälligen Vorhersagedaten von C#-Objekten in JSON-Pakete.
* Festlegen des Antwortheaders, um anzugeben, dass Ihr Dienst JSON-Daten zurücksendet.
* Schreiben der Antwort.

In den nächsten Abschnitten werden diese Schritte erläutert.

### <a name="parsing-the-query-string"></a>Analysieren der Abfragezeichenfolge

Sie beginnen mit der Analyse der Abfragezeichenfolge. Der Dienst nimmt die Argumente „lat“ und „long“ in der Abfragezeichenfolge in diesem Formular entgegen:

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

Alle Änderungen, die Sie vornehmen müssen, sind in dem Lambdaausdruck enthalten, der in Ihrer Startklasse als Argument für `app.Run` definiert ist.

Das Argument des Lambdaausdrucks ist der `HttpContext` für die Anforderung. Eine seiner Eigenschaften ist das `Request`-Objekt. Das `Request`-Objekt verfügt über eine `Query`-Eigenschaft, die ein Wörterbuch aller Werte in der Abfragezeichenfolge für die Anforderung enthält. Die erste Addition besteht darin, die Werte für Breiten- und Längengrad zu finden:

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

Die `Query`-Wörterbuchwerte sind vom Typ `StringValue`. Dieser Typ kann eine Auflistung von Zeichenfolgen enthalten. Für Ihren Wetterdienst ist jeder Wert eine einzelne Zeichenfolge. Daher erfolgt der Aufruf von `FirstOrDefault()` im obigen Code. 

Als Nächstes müssen Sie die Zeichenfolgen in Double-Werte konvertieren. Die Methode, mit der Sie die Zeichenfolge in einen Double-Wert konvertieren, ist `double.TryParse()`:

```csharp
bool TryParse(string s, out double result);
```

Diese Methode nutzt C#-out-Parameter, um anzugeben, ob die Eingabezeichenfolge in einen Double-Wert konvertiert werden kann. Wenn die Zeichenfolge einen gültigen Double-Wert darstellt, gibt die Methode „true“ zurück, und das `result`-Argument enthält den Wert. Wenn die Zeichenfolge keinen gültigen Double-Wert darstellt, gibt die Methode „false“ zurück.

Sie können diese API mithilfe einer *Erweiterungsmethode* anpassen, die einen *Nullable-Double-Wert*  zurückgibt. Ein *Nullable-Werttyp* ist ein Typ, der einen Werttyp darstellt und auch einen fehlenden, d.h. NULL-Wert enthalten kann. Ein Nullable-Typ wird durch Anhängen des `?`-Zeichens an die Typdeklaration dargestellt. 

Erweiterungsmethoden sind als statische Methoden definierte Methoden, können aber durch Hinzufügen des `this`-Modifizierers zum ersten Parameter so aufgerufen werden, als ob sie Member dieser Klasse sind. Erweiterungsmethoden können nur in statischen Klassen definiert werden. Hier ist die Definition der Klasse, die die Erweiterungsmethode für die Analyse enthält:

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

Ändern Sie vor dem Aufruf der Erweiterungsmethode die aktuelle Kultur in eine invariante Kultur:

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

Dadurch wird sichergestellt, dass Ihre Anwendung Zahlen auf einem beliebigen Server unabhängig von der Standardkultur immer gleich analysiert.

Sie können die Erweiterungsmethode nun verwenden, um die Abfragezeichenfolgen-Argumente in den Double-Typ zu konvertieren:

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

Um den Analysecode mühelos zu testen, aktualisieren Sie die Antwort so, dass sie die Werte der Argumente enthält:

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

An diesem Punkt können Sie die Webanwendung ausführen und prüfen, ob Ihr Analysecode funktioniert. Fügen Sie der Webanforderung in einem Browser Werte hinzu, und Sie sollten die aktualisierten Ergebnisse sehen.

### <a name="build-a-random-weather-forecast"></a>Erstellen einer zufälligen Wettervorhersage

Ihre nächste Aufgabe ist das Erstellen einer zufälligen Wettervorhersage. Wir beginnen mit einem Datencontainer, der die Werte enthält, die Sie für einen Wetterbericht wünschen:

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

Als Nächstes erstellen Sie einen Konstruktor, der diese Werte nach dem Zufallsprinzip festlegt. Dieser Konstruktor verwendet die Werte für den Breiten- und Längengrad, um den Zufallszahlengenerator `Random` mit einem Startwert zu initialisieren. Das bedeutet, dass die Vorhersage für den gleichen Ort identisch ist. Wenn Sie die Argumente für den Breiten- und Längengrad ändern, erhalten Sie eine andere Vorhersage, weil Sie mit einem anderen Startwert beginnen.

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

Sie können jetzt die 5-Tage-Wettervorhersage in Ihrer Antwortmethode generieren:

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a>Erstellen der JSON-Antwort

Die letzte Codeaufgabe auf dem Server besteht darin, die `WeatherReport`-Liste in ein JSON-Dokument zu konvertieren und dieses an den Client zurückzusenden. Zunächst erstellen Sie ein JSON-Dokument. Fügen Sie das Newtonsoft-JSON-Serialisierungsmodul der Liste der Abhängigkeiten hinzu. Hierzu können Sie den Befehl `dotnet` verwenden:

```console
dotnet add package Newtonsoft.Json
```

Anschließend können Sie das Objekt mithilfe der `JsonConvert`-Klasse in eine Zeichenfolge schreiben:

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

Der obige Code konvertiert das Vorhersageobjekt (eine Liste der `WeatherForecast`-Objekte) in ein JSON-Dokument. Nachdem Sie das Antwortdokument erstellt haben, legen Sie den Inhaltstyp auf `application/json` fest und schreiben die Zeichenfolge.

Die Anwendung wird jetzt ausgeführt und gibt zufällige Vorhersagen zurück.

## <a name="build-a-docker-image"></a>Erstellen eines Docker-Images

Unsere letzte Aufgabe ist das Ausführen der Anwendung in Docker. Wir erstellen einen Docker-Container, der ein Docker-Image ausführt, das die Anwendung darstellt.

Ein ***Docker-Image*** ist eine Datei, die die Umgebung für die Ausführung der Anwendung definiert.

Ein ***Docker-Container*** stellt eine ausgeführte Instanz eines Docker-Images dar.

Entsprechend können Sie sich das *Docker-Image* als eine *Klasse* und den *Docker-Container* als ein Objekt oder eine Instanz dieser Klasse vorstellen.  

Die folgende Docker-Datei ist für Ihre Anforderungen ausreichend:

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

Betrachten wir ihren Inhalt.

In der ersten Zeile wird das Quellimage angegeben, mit dem die Anwendung erstellt wird:

```
FROM microsoft/dotnet:2.1-sdk AS build
```

Mit Docker können Sie ein Computerimage auf Basis einer Quellvorlage konfigurieren. Das bedeutet, Sie müssen beim Start nicht alle Computerparameter, sondern nur Änderungen angeben. Hier dienen die Änderungen dazu, unsere Anwendung einzubeziehen.

In diesem Beispiel wird die `2.1-sdk`-Version des `dotnet`-Images verwendet. Dies ist die einfachste Möglichkeit zum Erstellen einer funktionierenden Docker-Umgebung. Dieses Image enthält die .NET Core-Runtime und das .NET Core SDK.
Dies erleichtert die ersten Schritte mit dem Image und dessen Erstellung. Das Image ist jedoch größer, weshalb dieses Image zur Erstellung der Anwendung und ein anderes Image für dessen Ausführung verwendet wird.

Mit den folgenden Zeilen wird die Anwendung eingerichtet und erstellt:

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

Dadurch wird die Projektdatei aus dem aktuellen Verzeichnis in die Docker-VM kopiert, und alle Pakete werden wiederhergestellt. Die Verwendung der Dotnet-CLI bedeutet, dass das Docker-Image das .NET Core-SDK einbeziehen muss. Danach werden die verbleibenden Anwendungsteile kopiert, und der `dotnet
publish`-Befehl erstellt Ihre Anwendung und erzeugt daraus ein Paket.

Abschließend erstellen Sie ein zweites Docker-Image, mit dem die Anwendung ausgeführt wird:

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

Für dieses Image wird die `2.1-aspnetcore-runtime`-Version des `dotnet`-Images verwendet, das alle erforderlichen Inhalte zum Ausführen von ASP.NET Core Anwendungen enthält, jedoch nicht das .NET Core SDK beinhaltet. Dieses Image kann daher nicht zum Erstellen von .NET Core-Anwendungen verwendet werden. Gleichzeitig wird das endgültige Image dadurch allerdings kleiner.

Kopieren Sie zum Ausführen des Vorgangs die erstellte Anwendung aus dem ersten Image, und fügen Sie es in das zweite ein.

Durch den `ENTRYPOINT`-Befehl wird Docker darüber informiert, mit welchem Befehl der Dienst gestartet wird.

## <a name="building-and-running-the-image-in-a-container"></a>Erstellen und Ausführen des Images in einem Container

Wir erstellen ein Image und führen den Dienst in einem Docker-Container aus. Nicht alle Dateien in Ihrem lokalen Verzeichnis sollen in das Image kopiert werden. Stattdessen erstellen Sie die Anwendung im Container. Sie erstellen eine `.dockerignore`-Datei, um die Verzeichnisse festzulegen, die nicht in das Image kopiert werden. Kein Buildobjekt soll kopiert werden. Geben Sie die Verzeichnisse für Build und Veröffentlichung in der `.dockerignore`-Datei an:

```
bin/*
obj/*
out/*
```

Sie erstellen das Image mithilfe des `docker build`-Befehls. Führen Sie den folgenden Befehl in dem Verzeichnis aus, das Ihren Code enthält.

```console
docker build -t weather-microservice .
```

Dieser Befehl erstellt das Containerimage basierend auf allen Informationen in Ihrer Docker-Datei. Das `-t`-Argument liefert ein Tag, d.h. einen Namen, für dieses Containerimage. In der Befehlszeile oben wird das Tag `weather-microservice` für den Docker-Container verwendet. Nach Abschluss dieses Befehls verfügen Sie über einen Container, in dem Sie den neuen Dienst ausführen können. 

Führen Sie den folgenden Befehl zum Starten des Containers aus, und starten Sie Ihren Dienst:

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

Die `-d`-Option bedeutet, den Container unabhängig vom aktuellen Terminal auszuführen. Dies bedeutet, dass die Ausgabe des Befehls nicht auf Ihrem Terminal angezeigt wird. Die `-p`-Option gibt die Portzuordnung zwischen dem Dienst und dem Host an. In diesem Fall wird angegeben, dass jede an Port 80 eingehende Anforderung an Port 80 im Container weitergeleitet werden soll. Port 80 ist der Port, auf dem Ihre Anwendung lauscht. Hierbei handelt es sich um den Standardport für Produktionsanwendungen. Das `--name`-Argument benennt den ausgeführten Container. Es ist ein praktischer Name, den Sie zum Arbeiten mit dem betreffenden Container verwenden können.

Sie können sehen, ob das Image ausgeführt wird, indem Sie den Befehl überprüfen:

```console
docker ps
```

Wenn der Container ausgeführt wird, sehen Sie eine Zeile, in der er als ausgeführter Prozess aufgelistet wird. Möglicherweise wird dort nur ein Prozess angezeigt.

Sie können Ihren Dienst testen, indem Sie einen Browser öffnen, zu „localhost“ navigieren und einen Breiten- und Längengrad angeben:

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a>Anfügen an einen ausgeführten Container

Bei der Ausführung des Diensts in einem Befehlsfenster wurden für jede Anforderung Diagnoseinformationen ausgegeben. Diese Informationen werden nicht angezeigt, wenn der Container im getrennten Modus ausgeführt wird. Der Docker-attach-Befehl ermöglicht Ihnen das Anfügen an einen ausgeführten Container, sodass Sie die Protokollinformationen sehen können.  Führen Sie diesen Befehl in einem Befehlsfenster aus:

```console
docker attach --sig-proxy=false hello-docker
```

Durch das `--sig-proxy=false`-Argument wird festgelegt, dass <kbd>STRG</kbd>+<kbd>C</kbd>-Befehle nicht an den Containerprozess gesendet werden, sondern stattdessen den `docker attach`-Befehl beenden. Das letzte Argument ist der Name, den der Container im `docker run`-Befehl erhält. 

> [!NOTE]
> Sie können auch die von Docker zugewiesene Container-ID verwenden, um auf einen Container zu verweisen. Wenn Sie in `docker run` keinen Namen für den Container angegeben haben, müssen Sie die Container-ID verwenden.

Öffnen Sie einen Browser, und navigieren Sie zu Ihrem Dienst. Sie sehen die Diagnosemeldungen des angefügten ausgeführten Containers in den Befehlsfenstern.

Drücken Sie <kbd>STRG</kbd>+<kbd>C</kbd>, um den Anfügungsprozess zu beenden.

Wenn Sie die Arbeit mit Ihrem Container abgeschlossen haben, können Sie ihn stoppen:

```console
docker stop hello-docker
```

Container und Image stehen weiterhin für einen Neustart zur Verfügung.  Wenn Sie den Container von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:

```console
docker rm hello-docker
```

Wenn Sie nicht benutzte Images von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a>Schlussbemerkung 

In diesem Tutorial haben Sie einen ASP.NET Core-Microservice erstellt und einige einfache Features hinzugefügt.

Sie haben ein Docker-Containerimage für diesen Dienst erstellt und diesen Container auf dem Computer ausgeführt. Sie haben dem Dienst ein Terminalfenster angefügt und die Diagnosemeldungen Ihres Diensts gesehen.

Nebenbei haben Sie verschiedene Features der C#-Sprache in Aktion gesehen.
