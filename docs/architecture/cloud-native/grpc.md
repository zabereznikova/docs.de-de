---
title: gRPC
description: Erfahren Sie mehr über gRPC, seine Rolle in Cloud-nativen Anwendungen und wie es sich von der HTTP RESTful-Kommunikation unterscheidet.
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 28a07ad5ec105d3fc5b65e4cf0ac0cd85eb16627
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524208"
---
# <a name="grpc"></a>gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Bisher haben wir uns in diesem Buch auf [REST-basierte](https://docs.microsoft.com/azure/architecture/best-practices/api-design) Kommunikation konzentriert. Wir haben gesehen, dass REST ein flexibler Architekturstil ist, der CRUD-basierte Vorgänge für Entitätsressourcen definiert. Clients interagieren mit Ressourcen über HTTP mit einem Anforderungs-/Antwortkommunikationsmodell. Während REST weithin implementiert ist, hat eine neuere Kommunikationstechnologie, gRPC, enorme Dynamik in der Cloud-nativen Community gewonnen.

## <a name="what-is-grpc"></a>Was ist gRPC?

gRPC ist ein modernes, leistungsstarkes Framework, das das uralte [RPC-Protokoll (Remote Procedure Call)](https://en.wikipedia.org/wiki/Remote_procedure_call) weiterentwickelt. Auf Anwendungsebene optimiert gRPC die Nachrichtenübermittlung zwischen Clients und Back-End-Diensten. gRPC stammt von Google und ist Open Source und Teil des [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) Ökosystems von Cloud-nativen Angeboten. CNCF betrachtet gRPC als [Inkubationsprojekt](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc). Inkubation bedeutet, dass Endbenutzer die Technologie in Produktionsanwendungen verwenden, und das Projekt hat eine gesunde Anzahl von Mitwirkenden.

Eine typische gRPC-Client-App macht eine lokale, prozessverarbeitende Funktion verfügbar, die einen Geschäftsvorgang implementiert. Unter den Abdeckungen ruft diese lokale Funktion eine andere Funktion auf einem Remotecomputer auf. Was wie ein lokaler Anruf aussieht, wird im Wesentlichen zu einem transparenten, out-of-process-Aufruf an einen Remotedienst. Das RPC-Rohr abstrahiert die Punkt-zu-Punkt-Netzwerkkommunikation, Serialisierung und Ausführung zwischen Computern.

In Cloud-nativen Anwendungen arbeiten Entwickler häufig über Programmiersprachen, Frameworks und Technologien hinweg. Diese *Interoperabilität* erschwert Nachrichtenverträge und die für die plattformübergreifende Kommunikation erforderlichen Sanitäranlagen.  gRPC bietet eine "einheitliche horizontale Ebene", die diese Bedenken abstrahiert. Entwicklercode in ihrer nativen Plattform konzentrierte sich auf Geschäftsfunktionen, während gRPC Kommunikationsinstallationen verarbeitet.

gRPC bietet umfassende Unterstützung für die meisten gängigen Entwicklungs-Stacks, einschließlich Java, JavaScript, C-, Go-, Swift- und NodeJS-Dateien.

## <a name="grpc-benefits"></a>gRPC Vorteile

gRPC verwendet HTTP/2 für sein Transportprotokoll. Obwohl HTTP/2 mit HTTP 1.1 kompatibel ist, verfügt es über viele erweiterte Funktionen:

- Ein binäres Protokoll für den Datentransport - im Gegensatz zu HTTP 1.1, das Daten als Klartext sendet.
- Multiplexing-Unterstützung für das Senden mehrerer paralleler Anforderungen über dieselbe Verbindung – HTTP 1.1 beschränkt die Verarbeitung auf jeweils eine Anforderungs-/Antwortnachricht.
- Bidirektionale Vollduplex-Kommunikation zum gleichzeitigen Senden von Clientanforderungen und Serverantworten.
- Integriertes Streaming ermöglicht Anforderungen und Antworten zum asynchronen Streamen großer Datensätze.

gRPC ist leicht und leistungsstark. Es kann bis zu 8x schneller als JSON Serialisierung mit Nachrichten 60-80% kleiner sein. In der Sprache der Microsoft [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) übertrifft die gRPC-Leistung die Geschwindigkeit und Effizienz der hochoptimierten [NetTCP-Bindungen](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8). Im Gegensatz zu NetTCP, das den Microsoft-Stack bevorzugt, ist gRPC plattformübergreifend.

## <a name="protocol-buffers"></a>Protokollpuffer

gRPC umfasst eine Open-Source-Technologie namens [Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview). Sie bieten ein hocheffizientes und plattformneutrales Serialisierungsformat für die Serialisierung strukturierter Nachrichten, die Dienste aneinander senden. Mithilfe einer plattformübergreifenden Interface Definition Language (IDL) definieren Entwickler einen Servicevertrag für jeden Microservice. Der Vertrag, der als `.proto` textbasierte Datei implementiert ist, beschreibt die Methoden, Eingaben und Ausgaben für jeden Dienst. Die gleiche Vertragsdatei kann für gRPC-Clients und -Dienste verwendet werden, die auf verschiedenen Entwicklungsplattformen basieren.

Mit der Proto-Datei generiert der `protoc`Protobuf-Compiler sowohl Client- als auch Dienstcode für Ihre Zielplattform. Der Code enthält die folgenden Komponenten:

- Stark typisierte Objekte, die vom Client und Dienst gemeinsam genutzt werden und die Dienstvorgänge und Datenelemente für eine Nachricht darstellen.
- Eine stark typisierte Basisklasse mit den erforderlichen Netzwerkinstallationen, die der Remote-gRPC-Dienst erben und erweitern kann.
- Ein Client-Stub, der die erforderlichen Installationen zum Aufrufen des Remote-gRPC-Dienstes enthält.

Zur Laufzeit wird jede Nachricht als standardmäßige Protobuf-Darstellung serialisiert und zwischen Client und Remotedienst ausgetauscht. Im Gegensatz zu JSON oder XML werden Protobuf-Nachrichten als kompilierte Binärbytes serialisiert.

Das Buch [gRPC for WCF Developers](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/), verfügbar auf der Microsoft Architecture-Website, bietet eine detaillierte Abdeckung von gRPC- und Protokollpuffern.

## <a name="grpc-support-in-net"></a>gRPC-Unterstützung in .NET

gRPC ist in .NET Core 3.0 SDK oder höher integriert. Die folgenden Tools unterstützen sie:

- Visual Studio 2019, Version 16.3 oder höher, mit installierter Webentwicklungs-Workload.
- Visual Studio Code
- die dotnet CLI

Das SDK umfasst Tools für Endpunktrouting, integriertes IoC und Protokollierung. Der Open-Source-Kestrel-Webserver unterstützt HTTP/2-Verbindungen. Abbildung 4-20 zeigt eine Visual Studio 2019-Vorlage, die ein Skelettprojekt für einen gRPC-Dienst aufbereitet. Beachten Sie, dass .NET Core Windows, Linux und macOS vollständig unterstützt.

![gRPC-Unterstützung in Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Abbildung 4-20:** gRPC-Unterstützung in Visual Studio 2019
  
Abbildung 4-21 zeigt den Skelett-gRPC-Dienst, der aus dem integrierten Gerüst generiert wurde, das in Visual Studio 2019 enthalten ist.  

![gRPC-Projekt in Visual Studio 2019](./media/grpc-project.png  )

**Abbildung 4-21:** gRPC-Projekt in Visual Studio 2019

Beachten Sie in der vorherigen Abbildung die Proto-Beschreibungsdatei und den Servicecode. Wie Sie in Kürze sehen werden, generiert Visual Studio zusätzliche Konfiguration sowohl in der Startklasse als auch in der zugrunde liegenden Projektdatei.

## <a name="grpc-usage"></a>gRPC-Nutzung

Bevorzugen Sie gRPC für die folgenden Szenarien:

- Synchrone Backend-Microservice-zu-Microservice-Kommunikation, bei der eine sofortige Reaktion erforderlich ist, um die Verarbeitung fortzusetzen.
- Polyglot-Umgebungen, die gemischte Programmierplattformen unterstützen müssen.
- Niedrige Latenz und Kommunikation mit hohem Durchsatz, bei denen die Leistung entscheidend ist.
- Punkt-zu-Punkt-Echtzeitkommunikation - gRPC kann Nachrichten in Echtzeit ohne Polling übertragen und bietet hervorragende Unterstützung für bidirektionales Streaming.
- Netzwerkeingeschränkte Umgebungen – binäre gRPC-Nachrichten sind immer kleiner als eine entsprechende textbasierte JSON-Nachricht.

Zu diesem Zeitpunkt wird gRPC hauptsächlich mit Backend-Diensten verwendet. Die meisten modernen Browser können nicht die Ebene der HTTP/2-Steuerung bereitstellen, die erforderlich ist, um einen Front-End-gRPC-Client zu unterstützen. Dennoch gibt es eine [frühe Initiative,](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) die die gRPC-Kommunikation von browserbasierten Apps ermöglicht, die mit JavaScript- oder Blazor WebAssembly-Technologien erstellt wurden. Das [gRPC-Web für .NET](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) ermöglicht es einer ASP.NET Core gRPC-App, gRPC-Funktionen in Browser-Apps zu unterstützen:

- Stark typisierte codegenerierte Clients
- Kompakte Protobuf-Meldungen
- Server-Streaming

## <a name="grpc-implementation"></a>gRPC-Implementierung

Die Microservice-Referenzarchitektur [eShop on Containers](https://github.com/dotnet-architecture/eShopOnContainers)von Microsoft zeigt, wie gRPC-Dienste in .NET Core-Anwendungen implementiert werden. Abbildung 4-22 zeigt die Back-End-Architektur.

![Backend-Architektur für eShop on Containers](./media/eshop-with-aggregators.png)

**Abbildung 4-22.** Backend-Architektur für eShop on Containers

Beachten Sie in der vorherigen Abbildung, wie eShop das [Backend for Frontends-Muster](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) (BFF) umfasst, indem mehrere API-Gateways freigelegt werden. Wir haben das BFF-Muster weiter oben in diesem Kapitel erörtert. Achten Sie genau auf den Aggregator-Mikrodienst (in grau), der sich zwischen dem Web-Shopping API Gateway und den Backend Shopping-Microservices befindet. Der Aggregator empfängt eine einzelne Anforderung von einem Client, sendet sie an verschiedene Microservices, aggregiert die Ergebnisse und sendet sie an den anfordernden Client zurück. Solche Vorgänge erfordern in der Regel eine synchrone Kommunikation, um eine sofortige Reaktion zu erzeugen. Im eShop werden Backend-Aufrufe vom Aggregator mit gRPC ausgeführt, wie in Abbildung 4-23 dargestellt.

![gRPC im eShop auf Containern](./media/grpc-implementation.png)

**Abbildung 4-23.** gRPC im eShop auf Containern

die gRPC-Kommunikation erfordert sowohl Client- als auch Serverkomponenten. Beachten Sie in der vorherigen Abbildung, wie der Shopping Aggregator einen gRPC-Client implementiert. Der Client führt synchrone gRPC-Aufrufe (rot) an Backend-Microservices durch, von denen jeder einen gRPC-Server implementiert. Sowohl der Client als auch der Server nutzen die integrierten gRPC-Installationen aus dem .NET Core 3.0 SDK. Clientseitige *Stubs* stellen die Installation zum Aufrufen von Remote-gRPC-Aufrufen bereit. Serverseitige Komponenten stellen gRPC-Installationen bereit, die benutzerdefinierte Serviceklassen erben und verbrauchen können.

Microservices, die sowohl eine RESTful API als auch eine gRPC-Kommunikation verfügbar machen, erfordern mehrere Endpunkte, um datenverkehr zu verwalten. Sie würden einen Endpunkt öffnen, der HTTP-Datenverkehr auf die RESTful-Aufrufe und einen weiteren für gRPC-Aufrufe abhört. Der gRPC-Endpunkt muss für das HTTP/2-Protokoll konfiguriert werden, das für die gRPC-Kommunikation erforderlich ist.

Während wir bestrebt sind, Microservices mit asynchronen Kommunikationsmustern zu entkoppeln, erfordern einige Vorgänge direkte Aufrufe. gRPC sollte die primäre Wahl für die direkte synchrone Kommunikation zwischen Microservices sein. Sein leistungsstarkes Kommunikationsprotokoll, das auf HTTP/2- und Protokollpuffern basiert, macht es zu einer perfekten Wahl.

## <a name="looking-ahead"></a>Blick in die Zukunft

Mit Blick auf die Zukunft wird gRPC weiterhin an Zugkraft für Cloud-native Systeme gewinnen. Die Leistungsvorteile und die einfache Entwicklung sind überzeugend. Rest wird es jedoch wahrscheinlich noch lange geben. Es zeichnet sich durch öffentlich verfügbar gemachte APIs und aus Gründen der Abwärtskompatibilität aus.

>[!div class="step-by-step"]
>[VorherigeS](service-to-service-communication.md)
>[Weiter](service-mesh-communication-infrastructure.md)
