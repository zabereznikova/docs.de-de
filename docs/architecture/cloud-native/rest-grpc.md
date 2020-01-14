---
title: REST und gRPC
description: Erfahren Sie mehr über GrpC, seine Rolle in Cloud-native Anwendungen und die Unterschiede zwischen der http-Rest-Funktion
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: 4c829407d494a3529d1fb9953cd3f56f73e90636
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711635"
---
# <a name="rest-and-grpc"></a>REST und gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Bisher haben wir uns in diesem Buch auf die [Rest-basierte](https://docs.microsoft.com/azure/architecture/best-practices/api-design) Kommunikation konzentriert. Rest ist ein Architekturstil, der die Interoperabilität zwischen verteilten Computersystemen fördert. Dabei wird ein Anforderungs-/Antwort-Modell verwendet, bei dem jede Antwort vom Server an eine Anforderung vom Client erfolgt. Rest ist zwar weit verbreitet, aber Rest ist für jedes Problem nicht optimal geeignet. Eine neuere Kommunikationstechnologie mit dem Titel "GrpC" gewinnt schnell eine Beliebtheit und macht Sie in der Cloud-Native Welt.

## <a name="grpc"></a>gRPC

GrpC ist eine Open-Source-Kommunikation, die von Google stammt. Es basiert auf dem RPC-Modell [(Remote Procedure Callcenter)](https://en.wikipedia.org/wiki/Remote_procedure_call) , das bei der verteilten Verarbeitung beliebt ist. Nach diesem Modell stellt ein lokales Client Programm eine Prozess interne Methode zum Ausführen eines Vorgangs zur Verfügung. Dieser Aufruf wird im Hintergrund für einen Out-of-Process-mikroservice in einem verteilten Netzwerk aufgerufen. Der Entwickler codiert den Vorgang als einen lokalen Prozedur Aufruf. Die zugrunde liegende Plattform abstrahiert die Punkt-zu-Punkt-Netzwerkkommunikation,-Serialisierung und-Ausführung.

GrpC ist ein modernes RPC-Framework, das einfach und leistungsfähig ist. Für das Transportprotokoll wird http/2 verwendet. Obwohl http/2 mit HTTP 1,1 kompatibel ist, bietet es viele erweiterte Funktionen:

- Obwohl HTTP 1,1 Daten als Klartext sendet, ist http/2 ein binäres Protokoll. Sie analysiert Daten schneller mit weniger Arbeitsspeicher, verringert die Netzwerk Latenz mit den damit verbundenen Verbesserungen der Geschwindigkeit und verwaltet die Netzwerkressourcen effizienter.
- Obwohl HTTP 1,1 auf die Verarbeitung von Roundtrip-Anforderungen/-Antworten auf einmal beschränkt ist, unterstützt HTTP/2 Multiplexing oder mehrere parallele Anforderungen über dieselbe Verbindung.
- HTTP/2 unterstützt eine Vollduplex-oder bidirektionale Kommunikation, bei der sowohl der Client als auch der Server gleichzeitig miteinander kommunizieren können. Der Client kann Anforderungs Daten hochladen, wenn der Serverantwort Daten zurücksendet.
- Streaming ist in http/2 integriert, was bedeutet, dass sowohl Anforderungen als auch Antworten große Datensätze asynchron streamen können.
- Die Kombination von GrpC und http/2 steigert die Leistung erheblich. In [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) -Parametern trifft die GrpC-Leistung zu und überschreitet die Geschwindigkeit und Effizienz von [NetTcp-Bindungen](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8). Anders als C# NetTcp ist GrpC jedoch nicht auf Microsoft-Sprachen wie oder Visual Basic beschränkt.

GrpC wird auf den beliebtesten Plattformen, einschließlich Java, C#, golang und nodejs, unterstützt.

## <a name="protocol-buffers"></a>Protokollpuffer

GrpC umfasst eine andere Open Source-Technologie namens [Protokollpuffer](https://developers.google.com/protocol-buffers/docs/overview) oder protobuf-Nachrichten zum Senden und empfangen von Daten. Ähnlich wie bei einem [WCF-Datenvertrag](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-data-contracts)werden von protobuf strukturierte Daten für das Lesen und Schreiben von Systemen serialisiert. Dadurch wird der Aufwand reduziert, der von menschenlesbaren Formaten wie XML oder JSON verursacht wird.

Viele objektserialisierungstechniken reflektieren die Struktur von Datenobjekten zur Laufzeit. Protobuf erfordert, dass Sie die Struktur im Vordergrund mit einer Platt Form agnostischen Sprache (Protokollpuffer Sprache) definieren. Jede Definition wird in einer ". proto"-Datei gespeichert. Anschließend generieren Sie mithilfe des protobuf-Compilers "Proton" Client-und Servercode für jede der unterstützten Plattformen. Der generierte Code ist für die schnelle Serialisierung/Deserialisierung von Daten optimiert. Zur Laufzeit wird jede Nachricht in den stark typisierten Dienstvertrag umgeschrieben und in einer standardmäßigen protobuf-Darstellung serialisiert.

## <a name="grpc-support-in-net"></a>GrpC-Unterstützung in .net

Das Microsoft .net Core-Framework 3,0 umfasst Tools und Native Unterstützung für GrpC. In Abbildung 4-20 wird die Visual Studio 2019-Vorlage gezeigt, die ein GrpC-Skelett Projekt für einen GrpC-Dienst gerükt. Beachten Sie, dass .net Core Windows-, Linux-und macOS-Plattformen unterstützt.

![GrpC-Unterstützung in Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Abbildung 4-20:** GrpC-Unterstützung in Visual Studio 2019

.Net Core 3,0 integriert GrpC nahtlos in sein Framework, einschließlich Endpunkt Routing, integrierter IOC-Unterstützung und Protokollierung. Der Open Source-Kestrel-Webserver bietet vollständige Unterstützung für http/2-Verbindungen.

Abbildung 4-21 zeigt die Struktur eines GrpC-Dienstanbieter in Visual Studio 2019. Beachten Sie, dass die Ordnerstruktur Ordner für die Proto-Dateien und den Dienst Code enthält.

![GrpC-Projekt in Visual Studio 2019](./media/grpc-project.png  )

**Abbildung 4-21:** GrpC-Projekt in Visual Studio 2019

## <a name="grpc-usage"></a>GrpC-Nutzung

GrpC eignet sich gut für die folgenden Szenarien:

- Kommunikation mit niedriger Latenz und hohem Durchsatz. GrpC eignet sich hervorragend für Lightweight-Dienste, bei denen die Effizienz wichtig ist.
- Punkt-zu-Punkt-Echtzeitkommunikation. GrpC bietet hervorragende Unterstützung für bidirektionales Streaming. GrpC-Dienste können Nachrichten in Echtzeit ohne Abruf per Push Übertragung.
- Polyglot-Umgebungen – die GrpC-Tools unterstützen die meisten gängigen Entwicklungs Sprachen, sodass Sie für mehrsprachige Umgebungen geeignet sind.
- Eingeschränkte Netzwerkumgebungen – GrpC-Nachrichten werden mit protobuf serialisiert, einem einfachen Nachrichtenformat. Eine GrpC-Nachricht ist immer kleiner als eine entsprechende JSON-Nachricht.

Zum Zeitpunkt des Schreibens dieses Buchs haben die meisten Browser eingeschränkte Unterstützung für GrpC. GrpC verwendet häufig http/2-Features, und kein Browser bietet die erforderliche Kontrolle über Webanforderungen zur Unterstützung eines GrpC-Clients. GrpC wird in der Regel für die interne Kommunikation zwischen einem Dienst und einem mikroservice verwendet. Abbildung 4-22 zeigt ein einfaches, aber gängiges Verwendungs Muster.

![GrpC-Verwendungs Muster](./media/grpc-usage.png)

**Abbildung 4-22.** GrpC-Verwendungs Muster

Beachten Sie in der vorhergehenden Abbildung, wie der Front-End-Datenverkehr mit http aufgerufen wird, während der Back-End-Dienst für den mikrodienst GrpC verwendet.

In der Vorschau könnte GrpC eine wichtige Rolle bei der Migration der Dominanz von Rest für cloudnative Systeme spielen. Die Leistungsvorteile und die einfache Entwicklung sind zu gut zu verbessern. Es ist jedoch kein Fehler, Rest ist für einen längeren Zeitraum weiterhin erreichbar. Dies ist für öffentlich verfügbar gemachte APIs und aus Gründen der Abwärtskompatibilität weiterhin hervorragend.

>[!div class="step-by-step"]
>[Zurück](service-to-service-communication.md)
>[Weiter](service-mesh-communication-infrastructure.md)
