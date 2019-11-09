---
title: 'Schnittstellen Definitions Sprache: GrpC für WCF-Entwickler'
description: Einführung in die Protokollpuffer-IDL.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 00c73619c5c27003e200385d5f67d8b8b7546f9e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841564"
---
# <a name="interface-definition-language"></a>Interface Definition Language (IDL)

Mit WCF können-Dienste Beschreibungs Metadaten mithilfe der WSDL (Web Service Definition Language) verfügbar machen, die zur Laufzeit dynamisch mithilfe von .NET-Reflektion generiert wird. Entwickler können diese Metadaten zum Generieren von Clients für diese Dienste verwenden, möglicherweise in anderen Sprachen, wenn eine plattformneutrale Bindung wie SOAP über HTTP verwendet wird.

GrpC verwendet die IDL (Interface Definition Language) aus Protokoll Puffern. Die Protokollpuffer-IDL ist eine benutzerdefinierte, plattformneutrale Sprache mit einer offenen Spezifikation. Entwickler `.proto` Dateien, um Dienste zusammen mit Ihren Eingaben und Ausgaben zu beschreiben. Diese `.proto` Dateien können dann verwendet werden, um Sprach-oder plattformspezifische Stubdaten für Clients und Server zu generieren, sodass mehrere verschiedene Plattformen miteinander kommunizieren können. Durch die Freigabe von `.proto` Dateien können Teams Code generieren, um die Dienste der anderen zu verwenden, ohne eine Code Abhängigkeit zu erfordern.

Einer der Vorteile der protobuf-IDL besteht darin, dass GrpC als benutzerdefinierte Sprache vollständig Sprache und Platt Form agnostisch sein kann, ohne dass Technologie über eine andere Technologie bevorzugt werden muss.

Die protobuf-IDL ist auch für das Lesen und Schreiben von Menschen konzipiert, wohingegen WSDL als Maschinelles lesbares/beschreibbares Format vorgesehen ist. Das Ändern der WSDL eines WCF-diensdienstanbieter erfordert in der Regel das vornehmen der Änderungen am Dienst Code selbst, das Ausführen des Dienstes und das erneute Generieren der WSDL-Datei vom Server. Im Gegensatz dazu können Änderungen mit einer `.proto`-Datei mit einem Text-Editor einfach angewendet werden und werden automatisch durch den generierten Code geleitet. Visual Studio 2019 erstellt `.proto` Dateien im Hintergrund, wenn Sie gespeichert werden. bei der Verwendung von anderen Editoren, z. b. vs Code, werden die Änderungen angewendet, wenn das Projekt erstellt wird.

Im Vergleich zu XML und besonders SOAP haben Nachrichten, die mit protobuf codiert werden, viele Vorteile. Protobuf-Nachrichten sind tendenziell kleiner als die gleichen Daten, die als SOAP-XML serialisiert werden, und die Codierung, Decodierung und Übertragung über ein Netzwerk kann schneller erfolgen.

Der potenzielle Nachteil von protobuf im Vergleich zu SOAP besteht darin, dass für das Debuggen von Nachrichten Inhalten zusätzliche Tools erforderlich sind, da die Nachrichten nicht von Menschen lesbar sind.

> [!TIP]
> GrpC *unter* stützt die Server Reflektion für den dynamischen Zugriff auf Dienste ohne vorkompilierte stubweise, obwohl Sie eher für allgemeine Tools als anwendungsspezifische Clients vorgesehen ist. Weitere Informationen zur GrpC-Server Reflektion finden Sie unter [GrpC/GrpC-](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) Repository auf GitHub.

> [!NOTE]
> Das mit der NetTcp-Bindung verwendete Binärformat von WCF ist in Bezug auf die Kompaktheit und Leistung viel näher an protobuf, aber NetTcp ist nur für .NET-Clients und-Server verwendbar, während protobuf eine plattformübergreifende Lösung ist.

>[!div class="step-by-step"]
>[Zurück](approach.md)
>[Weiter](network-protocols.md)
