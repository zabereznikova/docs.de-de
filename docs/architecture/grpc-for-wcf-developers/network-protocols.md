---
title: 'Netzwerkprotokolle: GrpC für WCF-Entwickler'
description: Eine Übersicht über die GrpC-Netzwerkprotokolle.
ms.date: 09/02/2019
ms.openlocfilehash: 1ceb140f7b7ac7e796a87612ebb9d21e28d33968
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628487"
---
# <a name="network-protocols"></a>Netzwerkprotokolle

Im Gegensatz zu Windows Communication Foundation (WCF) verwendet GrpC http/2 als Basis für das Netzwerk. Dies bietet gegenüber WCF und SOAP bedeutende Vorteile, die nur mit HTTP/1.1 funktionieren. Für Entwickler, die GrpC verwenden möchten, da es keine Alternative zu http/2 gibt, wäre es der ideale Moment, um http/2 ausführlicher zu untersuchen und zusätzliche Vorteile der Verwendung von GrpC zu erkennen.

HTTP/2, von der Internet Engineering Task Force in 2015 veröffentlicht, wurde vom experimentellen SPDY-Protokoll abgeleitet, das bereits von Google verwendet wurde. Sie wurde speziell für eine effizientere, schnellere und sicherere Sicherheit als HTTP/1.1 entwickelt.

## <a name="key-features-of-http2"></a>Wichtige Features von http/2

Diese Liste zeigt einige der wichtigsten Features und Vorteile von http/2:

### <a name="binary-protocol"></a>Binäres Protokoll

Anforderungs-/Antwort-Zyklen benötigen keine Textbefehle mehr. Dadurch wird die Implementierung von Befehlen vereinfacht und beschleunigt. Insbesondere ist die Datenverarbeitung schneller und beansprucht weniger Arbeitsspeicher, die Netzwerk Latenz wird mit offensichtlichen, zusammenhängenden Verbesserungen der Geschwindigkeit verringert, und es gibt eine allgemeine Nutzung der Netzwerkressourcen.

### <a name="streams"></a>Datenströme

Streams ermöglichen das Erstellen langlebiger Verbindungen zwischen Absender und Empfänger, über die mehrere Nachrichten oder Frames asynchron gesendet werden können. Mehrere Datenströme können über eine einzelne HTTP/2-Verbindung unabhängig voneinander betrieben werden.

### <a name="request-multiplexing-over-a-single-tcp-connection"></a>Anfordern von Multiplexing über eine einzelne TCP-Verbindung

Diese Funktion ist eine der wichtigsten Innovationen von http/2. Da es mehrere parallele Datenanforderungen zulässt, ist es jetzt möglich, Webdateien gleichzeitig von einem einzelnen Server herunterzuladen. Websites werden schneller geladen, und der Optimierungsbedarf wird reduziert. Eine Kopfzeile (SOF-Line, Hol), in der Antworten, die bereit sind, bis zum Abschluss einer früheren Anforderung gewartet werden müssen, ebenfalls verringert werden (auch wenn eine Hol-Blockierung auf der TCP-Transport Ebene auftreten kann).

### <a name="nettcp-like-performance-cross-platform"></a>NET. TCP-ähnliche Leistung, plattformübergreifend

Grundsätzlich bietet die Kombination aus GrpC und http/2 Entwicklern mindestens die entsprechende Geschwindigkeit und Effizienz von net. TCP-Bindungen für WCF, und in einigen Fällen ist dies noch schneller und effizienter. Aber im Gegensatz zu net. TCP ist GrpC über http/2 nicht auf .NET-Anwendungen beschränkt.

>[!div class="step-by-step"]
>[Zurück](interface-definition-language.md)
>[Weiter](why-grpc.md)
