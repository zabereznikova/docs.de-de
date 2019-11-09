---
title: 'Netzwerkprotokolle: GrpC für WCF-Entwickler'
description: Eine Übersicht über die GrpC-Netzwerkprotokolle.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: cf99b2608d576765856c992679b93b6f21e796cf
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841462"
---
# <a name="network-protocols"></a>Netzwerkprotokolle

Im Gegensatz zu WCF verwendet GrpC http/2 als Basis für das Netzwerk. Dies bietet gegenüber WCF und SOAP bedeutende Vorteile, die nur mit HTTP/1.1 funktionieren. Für Entwickler, die GrpC verwenden möchten, weil es keine Alternative zu http/2 gibt, wäre es der ideale Moment, um http/2 ausführlicher zu untersuchen und zusätzliche Vorteile bei der Verwendung von GrpC zu erkennen.

HTTP/2, von der Internet Engineering Task Force in 2015 veröffentlicht, wurde vom experimentellen SPDY-Protokoll abgeleitet, das bereits von Google verwendet wurde. Sie wurde speziell für eine effizientere, schnellere und sicherere Sicherheit als HTTP/1.1 entwickelt.

## <a name="key-features-of-http2"></a>Wichtige Features von http/2

In der folgenden Liste sind einige der wichtigsten Features und Vorteile von http/2 aufgeführt:

### <a name="binary-protocol"></a>Binäres Protokoll

Anforderungs-/Antwort-Zyklen benötigen keine Textbefehle mehr. Dadurch wird die Implementierung von Befehlen vereinfacht und beschleunigt. Insbesondere ist die Datenverarbeitung schneller und beansprucht weniger Arbeitsspeicher, die Netzwerk Latenz wird mit offensichtlichen, zusammenhängenden Verbesserungen der Geschwindigkeit verringert, und es gibt eine allgemeine Nutzung der Netzwerkressourcen.

### <a name="streams"></a>Streams

Streams ermöglichen die Erstellung langlebiger Verbindungen zwischen Absender und Empfänger, über die mehrere Nachrichten oder Frames asynchron gesendet werden können. Mehrere Datenströme können über eine einzelne HTTP/2-Verbindung unabhängig voneinander betrieben werden.

### <a name="request-multiplexing-over-a-single-tcp-connection"></a>Anfordern von Multiplexing über eine einzelne TCP-Verbindung

Diese Funktion ist eine der wichtigsten Innovationen von http/2. Durch das Zulassen mehrerer paralleler Datenanforderungen ist es jetzt möglich, Webdateien gleichzeitig von einem einzelnen Server herunterzuladen. Websites werden schneller geladen, und der Optimierungsbedarf wird reduziert. Eine Kopfzeile (Head-of-Line, Hol), in der Antworten, die bereit sind, bis zum Abschluss einer früheren Anforderung bis zum Abschluss einer früheren Anforderung gesendet zu werden, ebenfalls verringert werden (auch wenn eine Hol-Blockierung auf der TCP-Transport Ebene auftreten kann).

### <a name="nettcp-like-performance-cross-platform"></a>Nettcp-ähnliche Leistung, plattformübergreifend

Die Kombination aus GrpC und http/2 bietet Entwicklern zumindest die gleiche Geschwindigkeit und Effizienz von NetTcp-Bindungen für WCF, und in einigen Fällen ist dies noch schneller und effizienter. Im Gegensatz zu NetTcp ist GrpC über http/2 jedoch nicht auf .NET-Anwendungen beschränkt.

>[!div class="step-by-step"]
>[Zurück](interface-definition-language.md)
>[Weiter](why-grpc.md)
