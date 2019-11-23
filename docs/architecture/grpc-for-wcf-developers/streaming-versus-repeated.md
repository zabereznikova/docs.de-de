---
title: 'GrpC-Streamingdienste im Vergleich zu wiederholten Feldern: GrpC für WCF-Entwickler'
description: Vergleichen von wiederholten Feldern mit Streamingdiensten als Methoden zum Übergeben von Datensammlungen mit GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: f2f13776586607ed489c45ebb324c0c5713bed99
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966925"
---
# <a name="grpc-streaming-services-versus-repeated-fields"></a>GrpC-Streamingdienste im Vergleich zu wiederholten Feldern

GrpC-Dienste bieten zwei Möglichkeiten, Datasets oder Listen von Objekten zurückzugeben. Die Protokollpuffer-Nachrichten Spezifikation verwendet das `repeated`-Schlüsselwort zum Deklarieren von Listen oder Arrays von Nachrichten in einer anderen Nachricht. Die GrpC-Dienst Spezifikation verwendet das `stream`-Schlüsselwort, um eine persistente Verbindung mit langer Laufzeit zu deklarieren, über die mehrere Nachrichten gesendet und einzeln verarbeitet werden können. Die `stream` Funktion kann auch für temporale Daten mit langer Ausführungszeit verwendet werden, wie z. b. Benachrichtigungen oder Protokollmeldungen, aber in diesem Kapitel wird die Verwendung für das Zurückgeben eines einzelnen Datasets in Erwägung gezogen.

Welche Informationen Sie verwenden sollten, hängt von verschiedenen Faktoren ab, wie z. b. der Gesamtgröße des Datasets, der Zeit, die zum Erstellen des Datasets auf dem Client-oder Server Ende benötigt wurde, und ob der Consumer des Datasets mit der Transaktion beginnen kann, sobald das erste Element verfügbar ist. oder benötigt das komplette DataSet, um etwas Nützliches auszuführen.

## <a name="when-to-use-repeated-fields"></a>Verwendung `repeated` Felder

Für jedes Dataset, das in der Größe eingeschränkt ist und in einem kurzen Zeitraum vollständig generiert werden kann – beispielsweise unter einer Sekunde – sollten Sie ein `repeated` Feld in einer regulären protobuf-Nachricht verwenden. Beispielsweise ist in einem e-Commerce-System das Erstellen einer Liste von Elementen innerhalb einer Bestellung wahrscheinlich schnell und die Liste ist nicht sehr groß. Das Zurückgeben einer einzelnen Nachricht mit einem `repeated` Feld ist eine höhere Reihenfolge als die Verwendung eines `stream` und verursacht weniger Netzwerk Mehraufwand.

Wenn der Client alle Daten benötigt, bevor er mit der Verarbeitung beginnt, und das DataSet klein genug ist, um im Arbeitsspeicher zu erstellen, sollten Sie die Verwendung eines `repeated` Felds in Erwägung gezogen, auch wenn die tatsächliche Erstellung des Datasets im Arbeitsspeicher auf dem Server langsamer ist.

## <a name="when-to-use-stream-methods"></a>Verwendungsmöglichkeiten von `stream` Methoden

Datasets, in denen die Nachrichten Objekte potenziell sehr groß sind, werden am besten mithilfe von Streaminganforderungen oder Antworten übertragen. Es ist effizienter, ein großes Objekt im Speicher zu erstellen, es in das Netzwerk zu schreiben und dann die Ressourcen freizugeben. Diese Vorgehensweise verbessert die Skalierbarkeit ihres Dienstanbieter.

Ebenso sollten Datasets mit eingeschränkter Größe über Datenströme gesendet werden, um zu vermeiden, dass beim Erstellen der Arbeitsspeicher nicht mehr genügend Arbeitsspeicher verfügbar ist.

Bei Datasets, in denen jedes einzelne Element separat vom Consumer verarbeitet werden kann, sollten Sie die Verwendung eines Streams in Erwägung gezogen, wenn dies bedeutet, dass der Fortschritt für den Endbenutzer angezeigt werden kann. Dies kann die offensichtliche Reaktionsfähigkeit einer Anwendung verbessern, obwohl dies gegen die Gesamtleistung der Anwendung ausgeglichen werden sollte.

Ein anderes Szenario, in dem Datenströme nützlich sein können, ist die Verarbeitung einer Nachricht über mehrere Dienste hinweg. Wenn jeder Dienst in einer Kette einen Stream zurückgibt, kann der Terminaldienst (d. h. der letzte in der Kette) Nachrichten zurückgeben, die verarbeitet und an den ursprünglichen Anforderer zurückgegeben werden können, wodurch entweder ein Stream zurückgegeben oder das führt zu einer einzelnen Antwortnachricht. Diese Vorgehensweise eignet sich gut für Muster wie Map/Reduce.

>[!div class="step-by-step"]
>[Zurück](migrate-duplex-services.md)
>[Weiter](client-libraries.md)
