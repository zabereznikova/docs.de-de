---
title: Streaming-Dienste vs. wiederholte Felder - gRPC für WCF-Entwickler
description: Vergleichen Sie wiederholte Felder mit Streamingdiensten als Möglichkeiten zum Übergeben von Datensammlungen mithilfe von gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 542ebc393f9c9c1ad717d02d01fab33d85c18917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147749"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a>gRPC-Streamingdienste im Vergleich zu wiederholten Feldern

gRPC-Dienste bieten zwei Möglichkeiten zum Zurückgeben von Datasets oder Objektlisten. Die Protokollpuffer-Nachrichtenspezifikation `repeated` verwendet das Schlüsselwort zum Deklarieren von Listen oder Arrays von Nachrichten in einer anderen Nachricht. Die gRPC-Dienstspezifikation `stream` verwendet das Schlüsselwort, um eine lang andauernde persistente Verbindung zu deklarieren. Über diese Verbindung werden mehrere Nachrichten gesendet und können einzeln verarbeitet werden.

Sie können die `stream` Funktion auch für lang andauernde Zeitdaten wie Benachrichtigungen oder Protokollnachrichten verwenden. In diesem Kapitel wird jedoch die Verwendung für die Rückgabe eines einzelnen Datasets betrachtet.

Welche Sie verwenden sollten, hängt von Faktoren wie:

- Die Gesamtgröße des Datasets.
- Die Zeit, die zum Erstellen des Datasets am Client- oder Serverende erforderlich war.
- Gibt an, ob der Consumer des Datasets damit beginnen kann, darauf zu reagieren, sobald das erste Element verfügbar ist, oder ob er das vollständige Dataset benötigt, um etwas Nützliches zu tun.

## <a name="when-to-use-repeated-fields"></a>Verwendung von `repeated` Feldern

Für jedes Dataset, das in der Größe eingeschränkt ist und in kurzer Zeit vollständig generiert werden `repeated` kann ( z. B. unter einer Sekunde – sollten Sie ein Feld in einer regulären Protobuf-Nachricht verwenden. In einem E-Commerce-System ist das Erstellen einer Liste von Elementen innerhalb eines Auftrags wahrscheinlich schnell und die Liste wird nicht sehr groß sein. Das Zurückgeben einer `repeated` einzelnen Nachricht mit einem Feld `stream` ist eine Größenordnung schneller als die Verwendung und verursacht weniger Netzwerkaufwand.

Wenn der Client alle Daten benötigt, bevor er mit der Verarbeitung beginnt, und `repeated` das Dataset klein genug ist, um es im Arbeitsspeicher zu erstellen, sollten Sie ein Feld verwenden. Betrachten Sie dies auch dann, wenn die Erstellung des Datasets im Arbeitsspeicher auf dem Server langsamer ist.

## <a name="when-to-use-stream-methods"></a>Verwendung von `stream` Methoden

Wenn die Nachrichtenobjekte in Ihren Datasets potenziell sehr groß sind, ist es am besten, wenn Sie sie mithilfe von Streaminganforderungen oder Antworten übertragen. Effizienter ist es, ein großes Objekt im Arbeitsspeicher zu erstellen, es in das Netzwerk zu schreiben und dann die Ressourcen freizugeben. Dieser Ansatz verbessert die Skalierbarkeit Ihres Dienstes.

Ebenso sollten Sie Datasets von eingeschränkter Größe über Streams senden, um zu vermeiden, dass beim Erstellen nicht mehr Arbeitsspeicher zur Verfügung steht.

Bei Datasets, bei denen der Consumer jedes Element separat verarbeiten kann, sollten Sie die Verwendung eines Streams in Betracht ziehen, wenn der Fortschritt dem Benutzer angezeigt werden kann. Die Verwendung eines Streams kann die Reaktionsfähigkeit einer Anwendung verbessern, aber Sie sollten sie gegen die Gesamtleistung der Anwendung abwägen.

Ein weiteres Szenario, in dem Streams nützlich sein können, ist, wenn eine Nachricht über mehrere Dienste hinweg verarbeitet wird. Wenn jeder Dienst in einer Kette einen Stream zurückgibt, kann der Terminaldienst (d. h. der letzte in der Kette) mit der Rückgabe von Nachrichten beginnen. Diese Nachrichten können verarbeitet und entlang der Kette an den ursprünglichen Anforderer zurückgesendet werden. Der Anforderer kann entweder einen Stream zurückgeben oder die Ergebnisse in einer einzelnen Antwortnachricht aggregieren. Dieser Ansatz eignet sich gut für Muster wie MapReduce.

>[!div class="step-by-step"]
>[VorherigeS](migrate-duplex-services.md)
>[Weiter](client-libraries.md)
