---
title: Protokollpuffer-GrpC für WCF-Entwickler
description: Einführung in das Protokollpuffer-Wire-Format, das für GrpC-Netzwerke verwendet wird.
ms.date: 09/09/2019
ms.openlocfilehash: dbe8cb43475cfeec19051daf68452ef86269372f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967296"
---
# <a name="protocol-buffers"></a>Protokollpuffer

GrpC-Dienste senden und empfangen Daten als *Protokollpuffer (protobuf)-Nachrichten*, ähnlich den WCF-Daten Verträgen. Protobuf ist ein effizientes Verfahren zum Serialisieren strukturierter Daten für Computer, die gelesen und geschrieben werden können, ohne den mehr Aufwand, den die menschenlesbaren Formate wie XML oder JSON verursachen.

In diesem Kapitel wird erläutert, wie protobuf funktioniert und wie Sie Ihre eigenen protobuf-Nachrichten definieren.

## <a name="how-protobuf-works"></a>Funktionsweise von protobuf

Die meisten .net-objektserialisierungstechnologien, einschließlich der Datenverträge von WCF, funktionieren mithilfe von Reflektion, um die Objektstruktur zur Laufzeit zu analysieren. Im Gegensatz dazu erfordern die meisten protobuf-Bibliotheken, dass Sie die Struktur im Vordergrund mithilfe einer dedizierten Sprache (*Protokollpuffer Sprache*) in einer `.proto` Datei definieren. Diese Datei wird dann von einem Compiler verwendet, um Code für eine der unterstützten Plattformen zu generieren, einschließlich .net, JavaC++, C/, JavaScript und viele mehr. Der protobuf-compiler (`protoc`) wird von Google verwaltet, obwohl alternative Implementierungen verfügbar sind. Der generierte Code ist effizient und optimiert für die schnelle Serialisierung und Deserialisierung von Daten.

Das protobuf-Wire-Format selbst ist eine binäre Codierung, die einige clevere Tricks verwendet, um die Anzahl von Bytes zu minimieren, die zum Darstellen von Nachrichten verwendet werden. Das binäre Codierungsformat ist für die Verwendung von protobuf nicht erforderlich. Wenn Sie jedoch interessiert sind, können Sie auf [der Website "Protokollpuffer](https://developers.google.com/protocol-buffers/docs/encoding)" mehr darüber erfahren.

>[!div class="step-by-step"]
>[Zurück](why-grpc.md)
>[Weiter](protobuf-messages.md)
