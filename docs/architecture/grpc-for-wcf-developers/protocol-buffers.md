---
title: Protokollpuffer-GrpC für WCF-Entwickler
description: Einführung in das Protokollpuffer-Wire-Format, das für GrpC-Netzwerke verwendet wird.
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503455"
---
# <a name="protocol-buffers"></a>Protokollpuffer

GrpC-Dienste senden und empfangen Daten als *Protokollpuffer (protobuf)-Nachrichten*, ähnlich wie Datenverträge in Windows Communication Foundation (WCF). Protobuf ist ein effizientes Verfahren zum Serialisieren strukturierter Daten für Computer, die gelesen und geschrieben werden können, ohne den mehr Aufwand, den die menschenlesbaren Formate wie XML oder JSON verursachen.

In diesem Kapitel wird erläutert, wie protobuf funktioniert und wie Sie Ihre eigenen protobuf-Nachrichten definieren.

## <a name="how-protobuf-works"></a>Funktionsweise von protobuf

Die meisten .net-objektserialisierungstechnologien, einschließlich der Datenverträge von WCF, funktionieren mithilfe von Reflektion zur Analyse der Objektstruktur zur Laufzeit. Im Gegensatz dazu erfordern die meisten protobuf-Bibliotheken, dass Sie die Struktur im Vordergrund definieren, indem Sie eine dedizierte Sprache (*Protokollpuffer Sprache*) in einer `.proto` Datei verwenden. Ein Compiler verwendet diese Datei dann, um Code für jede der unterstützten Plattformen zu generieren. Zu den unterstützten Plattformen zählen .net,C++Java, C/, JavaScript und viele mehr. 

Der protobuf-compiler (`protoc`) wird von Google verwaltet, obwohl alternative Implementierungen verfügbar sind. Der generierte Code ist effizient und optimiert für die schnelle Serialisierung und Deserialisierung von Daten.

Das protobuf-Wire-Format ist eine binäre Codierung. Es werden einige clevere Tricks verwendet, um die Anzahl der Bytes zu minimieren, die für die Darstellung von Nachrichten Die Verwendung von protobuf ist nicht erforderlich, um das binäre Codierungsformat zu verwenden. Wenn Sie allerdings interessiert sind, können Sie auf [der Website für Protokollpuffer](https://developers.google.com/protocol-buffers/docs/encoding)mehr darüber erfahren.

>[!div class="step-by-step"]
>[Zurück](why-grpc.md)
>[Weiter](protobuf-messages.md)
