---
title: 'Reservierte Felder für protobuf: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über reservierte Felder für die Versions übergreifende Kompatibilität.
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542975"
---
# <a name="protobuf-reserved-fields"></a>Reservierte Protobuf-Felder

Die Abwärtskompatibilität garantiert in Protokollpuffer (protobuf) basiert auf Feldnummern, die immer das gleiche Datenelement darstellen. Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden. Hierfür können Sie das `reserved`-Schlüsselwort verwenden. 

Wenn die Felder `displayName` und `marketId` aus der zuvor definierten `Stock` Meldung entfernt wurden, sollten die entsprechenden Feldnummern wie im folgenden Beispiel reserviert werden.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Sie können auch das `reserved`-Schlüsselwort als Platzhalter für Felder verwenden, die möglicherweise in der Zukunft hinzugefügt werden. Sie können zusammenhängende Feld Zahlen als Bereich mit dem `to`-Schlüsselwort Ausdrücken.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Zurück](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)
