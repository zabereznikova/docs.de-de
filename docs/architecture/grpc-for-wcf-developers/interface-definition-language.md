---
title: 'Schnittstellen Definitions Sprache: GrpC für WCF-Entwickler'
description: Einführung in die Protokollpuffer-IDL.
ms.date: 12/15/2020
ms.openlocfilehash: 60cedd9b7c29bf54165b15f512c0b2159cb5dda9
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938077"
---
# <a name="interface-definition-language"></a>Interface Definition Language (IDL)

Mit Windows Communication Foundation (WCF) können-Dienste Beschreibungs Metadaten mithilfe von WSDL (Web Service Definition Language) verfügbar machen. WSDL wird dynamisch mithilfe der .NET-Reflektion zur Laufzeit generiert. Entwickler können diese Metadaten zum Generieren von Clients für diese Dienste verwenden, möglicherweise in anderen Sprachen, wenn Sie eine plattformneutrale Bindung wie SOAP über HTTP verwenden.

GrpC verwendet die IDL (Interface Definition Language) aus Protokoll Puffern. Die Protokollpuffer-IDL ist eine benutzerdefinierte, plattformneutrale Sprache mit einer offenen Spezifikation. Entwickler verfassen `.proto` Dateien, um Dienste zusammen mit Ihren Eingaben und Ausgaben zu beschreiben. Diese `.proto` Dateien können dann verwendet werden, um Sprach-oder plattformspezifische Stubdaten für Clients und Server zu generieren, sodass mehrere verschiedene Plattformen miteinander kommunizieren können. Durch die Freigabe von `.proto` Dateien können Teams Code generieren, um die Dienste der anderen zu verwenden, ohne eine Code Abhängigkeit zu erfordern.

Einer der Vorteile der protobuf-IDL besteht darin, dass GrpC als benutzerdefinierte Sprache vollständig Sprache und plattformunabhängig sein kann.

Die protobuf-IDL ist auch für das Lesen und Schreiben von Menschen konzipiert, wohingegen WSDL als Maschinelles lesbares/beschreibbares Format vorgesehen ist. Das Ändern der WSDL eines WCF-Dienes ist in der Regel erforderlich, um den Dienst zu ändern, den Dienst zu starten und die WSDL-Datei vom Server neu zu generieren. Im Gegensatz dazu können Änderungen mit einer `.proto` Datei einfach mit einem Text-Editor angewendet werden und werden automatisch durch den generierten Code geleitet. Visual Studio 2019 erstellt `.proto` Dateien im Hintergrund, wenn Sie gespeichert werden. Bei anderen Editoren, wie z. b. vs Code, werden die Änderungen angewendet, wenn das Projekt erstellt wird.

Im Vergleich zu XML und besonders SOAP haben Nachrichten, die mithilfe von protobuf codiert werden, viele Vorteile. Protobuf-Nachrichten sind tendenziell kleiner als die gleichen Daten, die als SOAP-XML serialisiert werden, und die Codierung, Decodierung und Übertragung über ein Netzwerk kann schneller erfolgen.

Der potenzielle Nachteil von protobuf im Vergleich zu SOAP besteht darin, dass für das Debuggen von Nachrichten Inhalten zusätzliche Tools erforderlich sind, da die Nachrichten von Menschen nicht lesbar sind.

> [!TIP]
> GrpC *unter* stützt die Server Reflektion für den dynamischen Zugriff auf Dienste ohne vorkompilierte stubweise, obwohl Sie eher für allgemeine Tools als anwendungsspezifische Clients vorgesehen ist. Weitere Informationen finden Sie unter [GrpC-Server reflektionsprotokoll](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) auf GitHub.

> [!NOTE]
> Das mit der NetTcp-Bindung verwendete Binärformat von WCF ist in Bezug auf die Kompaktheit und Leistung viel näher an protobuf. Nettcp kann jedoch nur zwischen .NET-Clients und-Servern verwendet werden, während protobuf eine plattformübergreifende Lösung ist.

>[!div class="step-by-step"]
>[Zurück](approach.md)
>[Weiter](network-protocols.md)
