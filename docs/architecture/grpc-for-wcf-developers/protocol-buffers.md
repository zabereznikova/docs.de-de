---
title: Protokollpuffer - gRPC für WCF-Entwickler
description: Einführung in das Protokollpufferdrahtformat, das für gRPC-Netzwerke verwendet wird.
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147931"
---
# <a name="protocol-buffers"></a>Protokollpuffer

gRPC-Dienste senden und empfangen Daten als *Protobuf-Nachrichten (Protocol Buffer),* ähnlich wie Datenverträge in Windows Communication Foundation (WCF). Protobuf ist eine effiziente Möglichkeit, strukturierte Daten für Maschinen zum Lesen und Schreiben zu serialisieren, ohne den Overhead, den menschenlesbare Formate wie XML oder JSON verursachen.

In diesem Kapitel wird erläutert, wie Protobuf funktioniert und wie Sie Ihre eigenen Protobuf-Nachrichten definieren.

## <a name="how-protobuf-works"></a>Wie Protobuf funktioniert

Die meisten .NET-Objektserialisierungstechniken, einschließlich der WCF-Datenverträge, verwenden Reflektion, um die Objektstruktur zur Laufzeit zu analysieren. Im Gegensatz dazu müssen Sie in den meisten Protobuf-Bibliotheken die Struktur im `.proto` Voraus definieren, indem Sie eine dedizierte Sprache (*Protokollpuffersprache*) in einer Datei verwenden. Ein Compiler verwendet diese Datei dann, um Code für eine der unterstützten Plattformen zu generieren. Zu den unterstützten Plattformen gehören .NET, Java, C/C++, JavaScript und viele mehr.

Der Protobuf-Compiler `protoc`, wird von Google verwaltet, obwohl alternative Implementierungen verfügbar sind. Der generierte Code ist effizient und optimiert für eine schnelle Serialisierung und Deserialisierung von Daten.

Das Protobuf-Drahtformat ist eine binäre Codierung. Es verwendet einige clevere Tricks, um die Anzahl der Bytes zu minimieren, die verwendet werden, um Nachrichten darzustellen. Kenntnisse des binären Codierungsformats sind nicht erforderlich, um Protobuf zu verwenden. Aber wenn Sie interessiert sind, können Sie mehr darüber auf [der Protocol Buffers Website](https://developers.google.com/protocol-buffers/docs/encoding)erfahren.

>[!div class="step-by-step"]
>[VorherigeS](why-grpc.md)
>[Weiter](protobuf-messages.md)
