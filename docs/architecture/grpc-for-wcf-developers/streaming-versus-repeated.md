---
title: 'Streaming Services im Vergleich zu wiederholten Feldern: GrpC für WCF-Entwickler'
description: Vergleichen Sie wiederholte Felder mit Streamingdiensten als Methoden zum Übergeben von Datensammlungen mithilfe von GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: 0e717df57ba2bb52d63a063072d8a45bf0f7e395
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503372"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a>GrpC-Streamingdienste im Vergleich zu wiederholten Feldern

GrpC-Dienste bieten zwei Möglichkeiten, Datasets oder Listen von Objekten zurückzugeben. Die Protokollpuffer-Nachrichten Spezifikation verwendet das `repeated`-Schlüsselwort zum Deklarieren von Listen oder Arrays von Nachrichten in einer anderen Nachricht. Die GrpC-Dienst Spezifikation verwendet das `stream`-Schlüsselwort, um eine persistente Verbindung mit langer Laufzeit zu deklarieren. Über diese Verbindung werden mehrere Nachrichten gesendet und können einzeln verarbeitet werden. 

Sie können auch das `stream` Feature für temporale Daten mit langer Laufzeit verwenden, z. b. Benachrichtigungen oder Protokollmeldungen. In diesem Kapitel wird jedoch die Verwendung für die Rückgabe eines einzelnen Datasets in Erwägung gezogen.

Welche Sie verwenden sollten, hängt von folgenden Faktoren ab:

- Die Gesamtgröße des Datasets.
- Die Zeit, die zum Erstellen des Datasets auf dem Client-oder dem Server Ende benötigt wird.
- Ob der Consumer des Datasets damit beginnen kann, darauf zu reagieren, sobald das erste Element verfügbar ist, oder das komplette DataSet benötigt, um etwas Nützliches zu tun.

## <a name="when-to-use-repeated-fields"></a>Verwendung `repeated` Felder

Für jedes Dataset, das in der Größe eingeschränkt ist und in einem kurzen Zeitraum vollständig generiert werden kann – beispielsweise unter einer Sekunde – sollten Sie ein `repeated` Feld in einer regulären protobuf-Nachricht verwenden. Beispielsweise ist in einem e-Commerce-System das Erstellen einer Liste von Elementen innerhalb einer Bestellung wahrscheinlich schnell und die Liste ist nicht sehr groß. Das Zurückgeben einer einzelnen Nachricht mit einem `repeated` Feld ist eine höhere Reihenfolge als die Verwendung `stream` und verursacht weniger Netzwerk Mehraufwand.

Wenn der Client alle Daten benötigt, bevor er mit der Verarbeitung beginnt, und das DataSet klein genug ist, um im Arbeitsspeicher zu erstellen, sollten Sie die Verwendung eines `repeated` Felds in Erwägung gezogen. Dies ist auch dann der Fall, wenn die Erstellung des Datasets im Arbeitsspeicher auf dem Server langsamer ist.

## <a name="when-to-use-stream-methods"></a>Verwendungsmöglichkeiten von `stream` Methoden

Wenn die Nachrichten Objekte in ihren Datasets potenziell sehr groß sind, sollten Sie Sie mit Streaminganforderungen oder Antworten übertragen. Es ist effizienter, ein großes Objekt im Speicher zu erstellen, es in das Netzwerk zu schreiben und dann die Ressourcen freizugeben. Diese Vorgehensweise verbessert die Skalierbarkeit ihres Dienstanbieter.

Ebenso sollten Sie Datasets mit eingeschränkter Größe über Datenströme senden, um zu vermeiden, dass beim Erstellen der Arbeitsspeicher nicht mehr genügend Arbeitsspeicher vorhanden ist.

Bei Datasets, in denen der Consumer die einzelnen Elemente separat verarbeiten kann, sollten Sie die Verwendung eines Streams in Erwägung gezogen, wenn dies bedeutet, dass der Fortschritt für den Benutzer angezeigt werden kann. Die Verwendung eines Streams kann die Reaktionsfähigkeit einer Anwendung verbessern, Sie sollten Sie jedoch gegen die Gesamtleistung der Anwendung ausgleichen.

Ein anderes Szenario, in dem Datenströme nützlich sein können, ist die Verarbeitung einer Nachricht über mehrere Dienste hinweg. Wenn jeder Dienst in einer Kette einen Stream zurückgibt, kann der Terminaldienst (d. h. der letzte in der Kette) Nachrichten zurückgeben. Diese Nachrichten können verarbeitet und an den ursprünglichen Anforderer zurückgegeben werden. Der Anforderer kann entweder einen Stream zurückgeben oder die Ergebnisse in einer einzelnen Antwortnachricht aggregieren. Diese Vorgehensweise eignet sich gut für Muster wie MapReduce.

>[!div class="step-by-step"]
>[Zurück](migrate-duplex-services.md)
>[Weiter](client-libraries.md)
