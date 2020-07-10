---
title: gRPC
description: Erfahren Sie mehr über GrpC, seine Rolle in Cloud native-Anwendungen und die Unterschiede zwischen der http-Rest-Kommunikation.
author: robvet
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 05/13/2020
ms.openlocfilehash: 6b41363008405032f4233448f134a8a602dbd26a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173158"
---
# <a name="grpc"></a>gRPC

Bisher haben wir uns in diesem Buch auf die [Rest-basierte](https://docs.microsoft.com/azure/architecture/best-practices/api-design) Kommunikation konzentriert. Wir haben gesehen, dass Rest ein flexibler Architekturstil ist, der CRUD-basierte Vorgänge für Entitäts Ressourcen definiert. Clients interagieren mit Ressourcen über HTTP mit einem Anforderungs-/Antwort-Kommunikationsmodell. Auch wenn Rest weit verbreitet ist, hat eine neuere Kommunikationstechnologie (GrpC) in der Cloud-Native Community enorme Dynamik erzielt.

## <a name="what-is-grpc"></a>Was ist GrpC?

GrpC ist ein modernes Hochleistungs Framework, das das alte RPC-Protokoll [(Remote Procedure callage)](https://en.wikipedia.org/wiki/Remote_procedure_call) weiterentwickelt. Auf Anwendungsebene optimiert GrpC das Messaging zwischen Clients und Back-End-Diensten. GrpC stammt von Google und ist Open Source und Bestandteil des Ökosystems der Cloud [native Computing Foundation (cncf)](https://www.cncf.io/) der cloudbasierten Angebote. Cncf betrachtet GrpC als [Projekt](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc), das ein Projekt umfasst. Das Auffüllen bedeutet, dass Endbenutzer die Technologie in Produktionsanwendungen verwenden und dass das Projekt eine fehlerfreie Anzahl von Mitwirkenden hat.

Eine typische GrpC-Client-App macht eine lokale, in-Process-Funktion verfügbar, die einen Geschäftsvorgang implementiert. Im Untertitel ruft diese lokale Funktion eine andere Funktion auf einem Remote Computer auf. Was als lokaler-Befehl erscheint, wird im Wesentlichen zu einem transparenten Prozess internen Aufrufe eines Remote Dienstanbieter. Die RPC-Grundlagen abstrahiert die Punkt-zu-Punkt-Netzwerkkommunikation,-Serialisierung und-Ausführung zwischen Computern.

In Cloud-native Anwendungen arbeiten Entwickler häufig über Programmiersprachen, Frameworks und Technologien hinweg. Diese *Interoperabilität* erschwert Nachrichten Verträge und die für die plattformübergreifende Kommunikation erforderliche Grundlagen.  GrpC bietet eine "einheitliche horizontale Schicht", die diese Probleme abstrahiert. Entwickler Programmieren in ihrer nativen Plattform den Schwerpunkt auf Geschäftsfunktionen, während GrpC die Kommunikationsabläufe übernimmt.

GrpC bietet umfassende Unterstützung für die beliebtesten Entwicklungs Stapel, einschließlich Java, JavaScript, c#, go, SWIFT und nodejs.

## <a name="grpc-benefits"></a>GrpC-Vorteile

GrpC verwendet http/2 für das Transportprotokoll. Obwohl http/2 mit HTTP 1,1 kompatibel ist, bietet es viele erweiterte Funktionen:

- Ein binäres Protokoll für den Datentransport-im Gegensatz zu HTTP 1,1, bei dem Daten als Klartext gesendet werden.
- Multiplexing-Unterstützung für das Senden mehrerer paralleler Anforderungen über dieselbe Verbindung-http 1,1 beschränkt die Verarbeitung auf eine Anforderungs-/Antwort-Nachricht gleichzeitig.
- Bidirektionale Vollduplex Kommunikation für das gleichzeitige Senden von Client Anforderungen und Server Antworten.
- Integriertes Streaming, das Anforderungen und Antworten zum asynchronen streamen großer Datasets ermöglicht.

GrpC ist einfach und leistungsstark. Es kann bis zu 8-mal schneller als die JSON-Serialisierung mit Nachrichten von 60-80% kleiner sein. In der Microsoft [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) -Sprache überschreitet die GrpC-Leistung die Geschwindigkeit und Effizienz der stark optimierten [NetTcp-Bindungen](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8). Anders als NetTcp, das den Microsoft Stack bevorzugt, ist GrpC plattformübergreifend.

## <a name="protocol-buffers"></a>Protokollpuffer

GrpC umfasst eine Open Source-Technologie namens [Protokollpuffer](https://developers.google.com/protocol-buffers/docs/overview). Sie bieten ein sehr effizientes und Platt Form neutrales Serialisierungsformat zum Serialisieren strukturierter Nachrichten, die von Diensten an einander gesendet werden. Mithilfe einer plattformübergreifenden Schnittstellen Definitions Sprache (IDL) definieren Entwickler einen Dienstvertrag für jeden einzelnen mikroservice. Der als textbasierte Datei implementierte Vertrag `.proto` beschreibt die Methoden, Eingaben und Ausgaben für jeden Dienst. Die gleiche Vertrags Datei kann für GrpC-Clients und-Dienste verwendet werden, die auf unterschiedlichen Entwicklungsplattformen erstellt wurden.

Wenn Sie die Datei "proto" verwenden, generiert der protobuf-compiler `protoc` sowohl Client-als auch Dienst Code für die Zielplattform. Der Code enthält die folgenden Komponenten:

- Stark typisierte-Objekte, die vom Client und Dienst gemeinsam verwendet werden und die Dienst Vorgänge und Datenelemente für eine Nachricht darstellen.
- Eine stark typisierte Basisklasse mit der erforderlichen Netzwerk Versorgung, die vom Remote-GrpC-Dienst geerbt und erweitert werden kann.
- Ein Clientstub, der die erforderlichen Grundlagen zum Aufrufen des Remote-GrpC-Dienstanbieter enthält.

Zur Laufzeit wird jede Nachricht als standardmäßige protobuf-Darstellung serialisiert und zwischen dem Client und dem Remote Dienst ausgetauscht. Im Gegensatz zu JSON oder XML werden protobuf-Nachrichten als kompilierte Binär Bytes serialisiert.

Das Buch, [GrpC für WCF-Entwickler](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/), das auf der Microsoft-Architektur Website verfügbar ist, bietet eine ausführliche Abdeckung der GrpC-und Protokollpuffer.

## <a name="grpc-support-in-net"></a>GrpC-Unterstützung in .net

GrpC ist in .net Core 3,0 SDK und höher integriert. Die folgenden Tools unterstützen diese:

- Visual Studio 2019, Version 16,3 oder höher, mit installierter Webentwicklungs-Arbeitsauslastung.
- Visual Studio Code
- die dotnet-CLI

Das SDK enthält Tools für das Endpunkt Routing, das integrierte IOC und die Protokollierung. Der Open-Source-Kestrel-Webserver unterstützt HTTP/2-Verbindungen. In Abbildung 4-20 wird eine Visual Studio 2019-Vorlage gezeigt, die ein Gerüst Projekt für einen GrpC-Dienst gerükt. Beachten Sie, dass .net Core Windows, Linux und macOS vollständig unterstützt.

![GrpC-Unterstützung in Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Abbildung 4-20:** GrpC-Unterstützung in Visual Studio 2019
  
In Abbildung 4-21 wird der Skeleton GrpC-Dienst gezeigt, der aus dem integrierten Gerüstbau in Visual Studio 2019 generiert wurde.  

![GrpC-Projekt in Visual Studio 2019](./media/grpc-project.png  )

**Abbildung 4-21:** GrpC-Projekt in Visual Studio 2019

Beachten Sie in der obigen Abbildung die Datei mit den Proto-Beschreibungen und den Dienst Code. Wie Sie sehen, generiert Visual Studio eine zusätzliche Konfiguration in der Startklasse und der zugrunde liegenden Projektdatei.

## <a name="grpc-usage"></a>GrpC-Nutzung

Bevorzugen Sie GrpC für die folgenden Szenarien:

- Synchrone Kommunikation zwischen dem Zwischenspeicher und dem mikrodienst, bei der eine sofortige Antwort erforderlich ist, um die Verarbeitung fortzusetzen.
- Polyglot-Umgebungen, die gemischte Programmier Plattformen unterstützen müssen.
- Kommunikation mit niedriger Latenz und hohem Durchsatz, bei der die Leistung kritisch ist.
- Point-to-Point-Echtzeitkommunikation: der GrpC kann Nachrichten in Echtzeit ohne Abruf per Push Übertragung und bietet hervorragende Unterstützung für bidirektionales Streaming.
- Eingeschränkte Netzwerkumgebungen – binäre GrpC-Nachrichten sind immer kleiner als eine entsprechende textbasierte JSON-Nachricht.

Zum Zeitpunkt der Erstellung dieses Dokuments wird GrpC hauptsächlich mit Back-End-Diensten verwendet. Die meisten modernen Browser können das für die Unterstützung eines Front-End-GrpC-Clients erforderliche Maß an http/2-Kontrolle nicht bereitstellen. Das heißt, es gibt eine [frühe Initiative](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) , die die GrpC-Kommunikation mit browserbasierten Apps ermöglicht, die mit JavaScript oder Technologien erstellt wurden Blazor WebAssembly . Mit dem [GrpC-Web für .net](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) kann eine ASP.net Core GrpC-App GrpC-Features in Browser-apps unterstützen:

- Stark typisierte, Code generierte Clients
- Compact protobuf-Meldungen
- Serverstreaming

## <a name="grpc-implementation"></a>GrpC-Implementierung

Die microservice Reference Architecture, [eShop on Containers](https://github.com/dotnet-architecture/eShopOnContainers), von Microsoft, zeigt, wie Sie GrpC-Dienste in .net Core-Anwendungen implementieren. In Abbildung 4-22 wird die Back-End-Architektur dargestellt.

![Back-End-Architektur für den eShop in Containern](./media/eshop-with-aggregators.png)

**Abbildung 4-22.** Back-End-Architektur für den eShop in Containern

Beachten Sie in der obigen Abbildung, wie der eShop das Back-End [für Front](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) -End-Muster (BFF) durch Bereitstellen mehrerer API-Gateways einnimmt. Wir haben das BFF-Muster bereits weiter oben in diesem Kapitel erläutert. Achten Sie auf den Aggregator-mikroservice (grau), der zwischen dem Web-Shopping-API-Gateway und den Back-End-Einkaufs-Webdiensten liegt. Der Aggregator empfängt eine einzelne Anforderung von einem Client, verteilt ihn an verschiedene mikrodienste, aggregiert die Ergebnisse und sendet Sie an den anfordernden Client zurück. Diese Vorgänge erfordern in der Regel eine synchrone Kommunikation, die eine sofortige Antwort erzeugt. Im eShop werden Back-End-Aufrufe vom Aggregator mithilfe von GrpC ausgeführt, wie in Abbildung 4-23 dargestellt.

![GrpC in eShop in Containern](./media/grpc-implementation.png)

**Abbildung 4-23.** GrpC in eShop in Containern

die GrpC-Kommunikation erfordert Client-und Serverkomponenten. Beachten Sie in der obigen Abbildung, wie der Einkaufs Aggregator einen GrpC-Client implementiert. Der Client führt synchrone GrpC-Aufrufe (in rot) für Back-End-Dienste aus, von denen jeder einen GrpC-Server implementiert. Sowohl der Client als auch der Server nutzen die integrierten GrpC-Anlagen aus der .net Core SDK. Client seitige *stubdas* bietet die Grundlagen zum Aufrufen von Remote-GrpC-aufrufen. Server seitige Komponenten bieten eine GrpC-Bereitstellung, die von benutzerdefinierten Dienst Klassen geerbt und genutzt werden kann.

Für Mikro Dienste, die sowohl eine Rest-API als auch eine GrpC-Kommunikation verfügbar machen, sind mehrere Endpunkte erforderlich, um den Öffnen Sie einen Endpunkt, der HTTP-Datenverkehr für die Rest-Aufrufe und einen weiteren für GrpC-Aufrufe abhört. Der GrpC-Endpunkt muss für das http/2-Protokoll konfiguriert werden, das für die GrpC-Kommunikation erforderlich ist.

Während wir uns bemühen, die subdienste mit asynchronen Kommunikationsmustern zu entkoppeln, sind für einige Vorgänge direkte Aufrufe erforderlich. GrpC sollte die primäre Wahl für die direkte synchrone Kommunikation zwischen den-Diensten sein. Das leistungsstarke Kommunikationsprotokoll, das auf http/2-und Protokoll Puffern basiert, ist eine perfekte Wahl.

## <a name="looking-ahead"></a>Im voraus

Wenn Sie sich im Vorfeld befinden, wird der GrpC weiterhin für cloudnative Systeme verwendet. Die Leistungsvorteile und die einfache Entwicklung sind von nutzen. Rest wird jedoch wahrscheinlich über einen längeren Zeitraum herumlaufen. Dies ist für öffentlich verfügbar gemachte APIs und aus Gründen der Abwärtskompatibilität hervorragend.

>[!div class="step-by-step"]
>[Zurück](service-to-service-communication.md)
>[Weiter](service-mesh-communication-infrastructure.md)
