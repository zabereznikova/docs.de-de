---
title: In Docker gehostete Microservices | C#
description: "Erfahren Sie, wie Sie ASP.NET Core-Dienste erstellen, die in Docker-Containern ausgeführt werden."
keywords: .NET, .NET Core, Docker, C#, ASP.NET, Microservice
author: BillWagner
ms.author: wiwagn
ms.date: 02/03/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: csharp
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.translationtype: Human Translation
ms.sourcegitcommit: ed747cf589e1f4731d78af7cc206ff3674d666b2
ms.openlocfilehash: b2ce10b3c079ff2c881f6dbe297ead33b8254476
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---

# <a name="microservices-hosted-in-docker"></a>In Docker gehostete Microservices

##<a name="introduction"></a>Einführung

In diesem Tutorial werden die erforderlichen Aufgaben zum Erstellen und Bereitstellen eines ASP.NET Core-Microservice in einem Docker-Container erläutert. Im Verlauf dieses Tutorials lernen Sie Folgendes:

* Generieren einer ASP.NET Core-Anwendung mit Yeoman
* Erstellen einer Docker-Entwicklungsumgebung
* Erstellen eines Docker-Images basierend auf einem vorhandenen Image
* Bereitstellen Ihres Diensts in einem Docker-Container

Dabei lernen Sie auch einige C#-Sprachfunktionen kennen:

* Konvertieren von C#-Objekten in JSON-Nutzlasten
* Erstellen unveränderlicher Datenübertragungsobjekte
* Verarbeiten eingehender HTTP-Anforderungen und Generieren der HTTP-Antwort
* Arbeiten mit Nullable-Werttypen

Sie können die Beispiel-App für diese Thema [anzeigen oder herunterladen](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="why-docker"></a>Warum Docker?

Docker erleichtert das Erstellen von standardmäßigen Computerimages zum Hosten Ihrer Dienste in einem Rechenzentrum oder der öffentlichen Cloud. Mit Docker können Sie das Image konfigurieren und nach Bedarf replizieren, um die Installation der Anwendung zu skalieren.

Der gesamte Code in diesem Tutorial ist in einer beliebigen .NET Core-Umgebung einsetzbar.
Die zusätzlichen Aufgaben für eine Docker-Installation funktionieren in Verbindung mit einer ASP.NET Core-Anwendung. 

## <a name="prerequisites"></a>Erforderliche Komponenten
Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).
Sie können diese Anwendung unter Windows, Ubuntu Linux, macOS oder in einem Docker-Container ausführen. Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

Sie müssen auch das Docker-Modul installieren. Anweisungen für Ihre Plattform finden Sie auf der [Docker-Installationsseite](http://www.docker.com/products/docker).
Docker kann in vielen Linux-Distributionen, unter macOS oder Windows installiert werden. Die oben erwähnte Seite enthält Abschnitte zu jeder verfügbaren Installation.

Die meisten zu installierenden Komponenten sind einem Paket-Manager zugeordnet. Wenn Sie den Node.js-Paket-Manager `npm` installiert haben, können Sie diesen Schritt überspringen. Installieren Sie andernfalls das aktuelle NodeJS von [nodejs.org](https://nodejs.org), sodass der npm-Paket-Manager installiert wird. 

An diesem Punkt müssen Sie eine Reihe von Befehlszeilentools installieren, die die ASP.NET Core-Entwicklung unterstützen. Die Befehlszeilenvorlagen verwenden Yeoman, Bower, Grunt und Gulp. Sie haben sie bereits installiert? Hervorragend – geben Sie andernfalls Folgendes in Ihre bevorzugte Shell ein:

`npm install -g yo bower grunt-cli gulp`

Die `-g`-Option gibt an, dass dies eine globale Installation ist, und diese Tools im gesamten System verfügbar sind. (Eine lokale Installation beschränkt das Paket auf ein einzelnes Projekt). Nachdem Sie diese wesentlichen Tools installiert haben, müssen Sie die Yeoman-ASP.NET-Vorlagengeneratoren installieren:

`npm install -g generator-aspnet`

## <a name="create-the-application"></a>Erstellen der Anwendung

Jetzt haben Sie alle Tools installiert und können eine neue ASP.NET Core-Anwendung erstellen. Um den Befehlszeilengenerator zu verwenden, führen Sie den folgenden Yeoman-Befehl in Ihrer bevorzugten Shell aus:

`yo aspnet`

Dieser Befehl fordert Sie auf, auszuwählen, welchen Anwendungstyp Sie erstellen möchten. Für diesen Microservice sollten Sie die unkomplizierteste Webanwendung wählen, also wählen Sie „Leere Web-Anwendung“ aus. Die Vorlage fordert Sie zur Eingabe eines Namens auf. Wählen Sie „WeatherMicroservice“. 

Die Vorlage erstellt acht Dateien für Sie:

* Eine für ASP.NET Core-Anwendungen angepasste .gitignore-Datei.
* Eine Startup.cs-Datei. Diese enthält die Grundlage für die Anwendung.
* Eine Program.cs-Datei. Diese enthält den Einstiegspunkt für die Anwendung.
* Eine WeatherMicroservice.csproj-Datei. Dies ist die Build-Datei für die Anwendung.
* Die Docker-Datei. Dieses Skript erstellt ein Docker-Image für die Anwendung.
* Eine README.md-Datei. Diese enthält Links zu anderen ASP.NET Core-Ressourcen.
* Eine web.config-Datei. Diese enthält grundlegende Konfigurationsinformationen.
* Eine runtimeconfig.template.json-Datei. Diese enthält von IDEs verwendete Debugeinstellungen.

Jetzt können Sie die von der Vorlage generierte Anwendung ausführen. Dies geschieht mithilfe einer Reihe von Tools von der Befehlszeile aus. Der `dotnet`-Befehl führt die erforderlichen Tools für die .NET-Entwicklung aus. Jedes Verb führt einen anderen Befehl aus.

Der erste Schritt besteht im Wiederherstellen aller Abhängigkeiten:

```console
dotnet restore
```

Die Dotnet-Wiederherstellung verwendet den NuGet-Paket-Manager, um alle erforderlichen Pakete im Verzeichnis der Anwendung zu installieren. Sie generiert außerdem eine project.json.lock-Datei. Diese Datei enthält Informationen zu jedem Paket, auf das verwiesen wird. Nach der Wiederherstellung alle Abhängigkeiten erstellen Sie die Anwendung:

```console
dotnet build
```

Sobald Sie die Anwendung erstellen, führen Sie sie über die Befehlszeile aus:

```console
dotnet run
```

Die Standardkonfiguration lauscht auf http://localhost:5000. Wenn Sie den Browser öffnen und zu dieser Seite navigieren, sehen Sie ein „Hello World!“. Vorgang nicht gefunden werden konnte.

### <a name="anatomy-of-an-aspnet-core-application"></a>Anatomie einer ASP.NET Core-Anwendung

Da Sie jetzt die Anwendung erstellt haben, können wir nun die Implementierung dieser Funktionalität betrachten. Zwei der generierten Dateien sind hier besonders interessant: „project.json“ und „Startup.cs“. 

„project.json“ enthält Informationen zum Projekt. Sie werden häufig mit den beiden Knoten „Abhängigkeiten“ und „Frameworks“ arbeiten. Der Abhängigkeiten-Knoten listet alle Pakete auf, die für diese Anwendung erforderlich sind.
Im Moment ist dies ein kleiner Knoten, der nur die Pakete benötigt, die den Webserver ausführen.

Der frameworks-Knoten gibt die Versionen und Konfigurationen des .NET Framework an, das diese Anwendung ausführen wird.

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

### <a name="parsing-the-query-string"></a>Analyse der Abfragezeichenfolge.

Sie beginnen mit der Analyse der Abfragezeichenfolge. Der Dienst nimmt die Argumente „lat“ und „long“ in der Abfragezeichenfolge in diesem Formular entgegen:

`http://localhost:5000/?lat=-35.55&long=-12.35`  

Alle Änderungen, die Sie vornehmen müssen, sind in dem Lambdaausdruck enthalten, der in Ihrer Startklasse als Argument für `app.Run` definiert ist.

Das Argument des Lambdaausdrucks ist der `HttpContext` für die Anforderung. Eine seiner Eigenschaften ist das `Request`-Objekt. Das `Request`-Objekt verfügt über eine `Query`-Eigenschaft, die ein Wörterbuch aller Werte in der Abfragezeichenfolge für die Anforderung enthält. Die erste Addition besteht darin, die Werte für Breiten- und Längengrad zu finden:

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "Lesen von Variablen aus der Abfragezeichenfolge")]

Die Abfrage-Wörterbuchwerte sind vom Typ `StringValue`. Dieser Typ kann eine Auflistung von Zeichenfolgen enthalten. Für Ihren Wetterdienst ist jeder Wert eine einzelne Zeichenfolge. Daher erfolgt der Aufruf von `FirstOrDefault()` im obigen Code. 

Als Nächstes müssen Sie die Zeichenfolgen in Double-Werte konvertieren. Die Methode, mit der Sie die Zeichenfolge in einen Double-Wert konvertieren, ist `double.TryParse()`:

```csharp
bool TryParse(string s, out double result);
```

Diese Methode nutzt C#-out-Parameter, um anzugeben, ob die Eingabezeichenfolge in einen Double-Wert konvertiert werden kann. Wenn die Zeichenfolge einen gültigen Double-Wert darstellt, gibt die Methode „true“ zurück, und das `result`-Argument enthält den Wert. Wenn die Zeichenfolge keinen gültigen Double-Wert darstellt, gibt die Methode „false“ zurück.

Sie können diese API mithilfe einer *Erweiterungsmethode* anpassen, die einen *Nullable-Double-Wert*  zurückgibt. Ein *Nullable-Werttyp* ist ein Typ, der einen Werttyp darstellt und auch einen fehlenden, d.h. NULL-Wert enthalten kann. Ein Nullable-Typ wird durch Anhängen des `?`-Zeichens an die Typdeklaration dargestellt. 

Erweiterungsmethoden sind als statische Methoden definierte Methoden, können aber durch Hinzufügen des `this`-Modifizierers zum ersten Parameter so aufgerufen werden, als ob sie Member dieser Klasse sind. Erweiterungsmethoden können nur in statischen Klassen definiert werden. Hier ist die Definition der Klasse, die die Erweiterungsmethode für die Analyse enthält:

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "Versuch der Analyse in einen Nullable-Wert")]

Der `default(double?)`-Ausdruck gibt den Standardwert für den `double?`-Typ zurück. Dieser Standardwert ist der NULL-Wert (oder nicht vorhandener Wert).

Sie können diese Erweiterungsmethode verwenden, um die Abfragezeichenfolgen-Argumente in den Double-Typ zu konvertieren:

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Verwenden der TryParse-Erweiterungsmethode")]

Um den Analysecode mühelos zu testen, aktualisieren Sie die Antwort so, dass sie die Werte der Argumente enthält:

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Schreiben der Ausgabeantwort")]

An diesem Punkt können Sie die Webanwendung ausführen und prüfen, ob Ihr Analysecode funktioniert. Fügen Sie der Webanforderung in einem Browser Werte hinzu, und Sie sollten die aktualisierten Ergebnisse sehen.

### <a name="build-a-random-weather-forecast"></a>Erstellen einer zufälligen Wettervorhersage

Ihre nächste Aufgabe ist das Erstellen einer zufälligen Wettervorhersage. Wir beginnen mit einem Datencontainer, der die Werte enthält, die Sie für einen Wetterbericht wünschen:

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

Als Nächstes erstellen Sie einen Konstruktor, der diese Werte nach dem Zufallsprinzip festlegt. Dieser Konstruktor verwendet die Werte für den Breiten- und Längengrad, um den Zufallszahlengenerator zu starten. Das bedeutet, dass die Vorhersage für den gleichen Ort identisch ist. Wenn Sie die Argumente für den Breiten- und Längengrad ändern, erhalten Sie eine andere Vorhersage (weil Sie mit einem anderen Startwert beginnen.)

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Wetterberichtkonstruktor")]

Sie können jetzt die 5-Tage-Wettervorhersage in Ihrer Antwortmethode generieren:

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generieren eines zufälligen Wetterberichts")]

### <a name="build-the-json-response"></a>Erstellen Sie die JSON-Antwort.

Die letzte Codierungsaufgabe auf dem Server ist, das WeatherReport-Array in ein JSON-Paket zu konvertieren und dieses an den Client zurückzusenden. Wir erstellen zunächst das JSON-Paket. Sie fügen das NewtonSoft JSON-Serialisierungsprogramm der Liste der Abhängigkeiten hinzu. Verwenden Sie hierzu die `dotnet`-CLI:

```
dotnet add package Newtonsoft.Json
```

Anschließend können Sie das Objekt mithilfe der `JsonConvert`-Klasse in eine Zeichenfolge schreiben:

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Konvertieren von Objekten in JSON")]

Der obige Code konvertiert das Vorhersageobjekt (eine Liste der `WeatherForecast`-Objekte) in ein JSON-Paket. Nachdem Sie das Antwortpaket erstellt haben, legen Sie den Inhaltstyp auf `application/json` fest, und schreiben Sie die Zeichenfolge.

Die Anwendung wird jetzt ausgeführt und gibt zufällige Vorhersagen zurück.

## <a name="build-a-docker-image"></a>Erstellen eines Docker-Images

Unsere letzte Aufgabe ist das Ausführen der Anwendung in Docker. Wir erstellen einen Docker-Container, der ein Docker-Image ausführt, das die Anwendung darstellt.

Ein ***Docker-Image*** ist eine Datei, die die Umgebung für die Ausführung der Anwendung definiert.

Ein ***Docker-Container*** stellt eine ausgeführte Instanz eines Docker-Images dar.

Entsprechend können Sie sich das *Docker-Image* als eine *Klasse* und den *Docker-Container* als ein Objekt oder eine Instanz dieser Klasse vorstellen.  

Die von der ASP.NET-Vorlage erstellte Docker-Datei ist für unsere Zwecke geeignet. Betrachten wir ihren Inhalt.

Die erste Zeile gibt das Quellimage an:

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

Mit Docker können Sie ein Computerimage auf Basis einer Quellvorlage konfigurieren. Das bedeutet, Sie müssen beim Start nicht alle Computerparameter, sondern nur Änderungen angeben. Hier dienen die Änderungen dazu, unsere Anwendung einzubeziehen.

In diesem ersten Beispiel verwenden wir die `1.1-sdk-msbuild`-Version des Dotnet-Images. Dies ist die einfachste Möglichkeit zum Erstellen einer funktionierenden Docker-Umgebung. Dieses Image enthält die Dotnet Core-Laufzeit und das Dotnet SDK. Dies vereinfacht den Einstieg und das Erstellen, erstellt aber kein größeres Image.

Die nächsten fünf Zeilen richten die Anwendung ein und erstellen sie:

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

Hiermit wird die Projektdatei aus dem aktuellen Verzeichnis in die Docker-VM kopiert und werden alle Pakete wiederhergestellt. Die Verwendung der Dotnet-CLI bedeutet, dass das Docker-Image das .NET Core-SDK einbeziehen muss. Danach wird der Rest der Anwendung kopiert, und der Dotnet-publish-Befehl erstellt Ihre Anwendung und macht daraus ein Paket.

Die letzte Zeile der Datei führt die Anwendung aus:

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

Auf diesen konfigurierten Port wird im `--server.urls`-Argument für `dotnet` in der letzten Zeile der Docker-Datei verwiesen. Die `ENTRYPOINT`-Befehl teilt Docker mit, welcher Befehl und welche Befehlszeilenoptionen den Dienst starten. 

## <a name="building-and-running-the-image-in-a-container"></a>Erstellen und Ausführen des Images in einem Container

Wir erstellen ein Image und führen den Dienst in einem Docker-Container aus. Nicht alle Dateien in Ihrem lokalen Verzeichnis sollen in das Image kopiert werden. Stattdessen erstellen Sie die Anwendung im Container. Sie erstellen eine `.dockerignore`-Datei, um die Verzeichnisse festzulegen, die nicht in das Image kopiert werden. Kein Buildobjekt soll kopiert werden. Geben Sie die Verzeichnisse für Build und Veröffentlichung in der `.dockerignore`-Datei an:

```
bin/*
obj/*
out/*
```

Sie erstellen das Image mithilfe des Docker-build-Befehls. Führen Sie den folgenden Befehl in dem Verzeichnis aus, das Ihren Code enthält.

```console
docker build -t weather-microservice .
```

Dieser Befehl erstellt das Containerimage basierend auf allen Informationen in Ihrer Docker-Datei. Das `-t`-Argument liefert ein Tag, d.h. einen Namen, für dieses Containerimage. In der Befehlszeile oben wird das Tag `weather-microservice` für den Docker-Container verwendet. Nach Abschluss dieses Befehls verfügen Sie über einen Container, in dem Sie den neuen Dienst ausführen können. 

Führen Sie den folgenden Befehl zum Starten des Containers aus, und starten Sie Ihren Dienst:

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

Die `-d`-Option bedeutet, den Container unabhängig vom aktuellen Terminal auszuführen. Dies bedeutet, dass die Ausgabe des Befehls nicht auf Ihrem Terminal angezeigt wird. Die `-p`-Option gibt die Portzuordnung zwischen dem Dienst und dem Host an. Hier gibt sie an, dass jede an Port 80 eingehende Anforderung an Port 5000 im Container weitergeleitet werden soll. 5000 entspricht dem Port, auf den der Dienst über die Befehlszeilenargumente lauscht, die in der oben genannten Docker-Datei angegeben sind. Das `--name`-Argument benennt den ausgeführten Container. Es ist ein praktischer Name, den Sie zum Arbeiten mit dem betreffenden Container verwenden können. 

Sie können sehen, ob das Image ausgeführt wird, indem Sie den Befehl überprüfen:

```console
docker ps
```

Wenn der Container ausgeführt wird, sehen Sie eine Zeile, in der er als ausgeführter Prozess aufgelistet wird. (Vielleicht ist er der einzige).

Sie können Ihren Dienst testen, indem Sie einen Browser öffnen, zu „localhost“ navigieren und einen Breiten- und Längengrad angeben:

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a>Anfügen an einen ausgeführten Container

Bei der Ausführung Ihres Diensts in einem Befehlsfenster konnten Sie sehen, dass für jede Anforderung Diagnoseinformationen ausgegeben wurden. Diese Informationen werden nicht angezeigt, wenn der Container im getrennten Modus ausgeführt wird. Der Docker-attach-Befehl ermöglicht Ihnen das Anfügen an einen ausgeführten Container, sodass Sie die Protokollinformationen sehen können.  Führen Sie diesen Befehl in einem Befehlsfenster aus:

```console
docker attach --sig-proxy=false hello-docker
```

Das `--sig-proxy=false`-Argument bedeutet, dass `Ctrl-C`-Befehle nicht an den Containerprozess gesendet werden, aber stattdessen den `docker attach`-Befehl beenden. Das letzte Argument ist der Name, den der Container im `docker run`-Befehl erhält. 

> [!NOTE]
> Sie können auch die Docker zugewiesene Container-ID verwenden, um auf einen Container zu verweisen. Wenn Sie in `docker run` keinen Namen für den Container angegeben haben, müssen Sie die Container-ID verwenden.

Öffnen Sie einen Browser, und navigieren Sie zu Ihrem Dienst. Sie sehen die Diagnosemeldungen des angefügten ausgeführten Containers in den Befehlsfenstern.

Drücken Sie `Ctrl-C`, um den Anfügungsprozess zu beenden.

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

## <a name="conclusion"></a>Schlussfolgerung 

In diesem Tutorial haben Sie einen ASP.NET Core-Microservice erstellt und einige einfache Funktionen hinzugefügt.

Sie haben ein Docker-Containerimage für diesen Dienst erstellt und diesen Container auf dem Computer ausgeführt. Sie haben dem Dienst ein Terminalfenster angefügt und die Diagnosemeldungen Ihres Diensts gesehen.

Nebenbei haben Sie verschiedene Features der C#-Sprache in Aktion gesehen.

