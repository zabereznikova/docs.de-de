---
title: 'Reservierte Felder für protobuf: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über reservierte Felder für die Versions übergreifende Kompatibilität.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841390"
---
# <a name="protobuf-reserved-fields"></a>Reservierte Protobuf-Felder

Die Abwärtskompatibilität von protobuf basiert darauf, dass Feldnummern immer das gleiche Datenelement darstellen. Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden. Dies kann mit dem `reserved`-Schlüsselwort erzwungen werden. Wenn die Felder `displayName` und `marketId` aus der zuvor definierten `Stock` Meldung entfernt wurden, sollten die entsprechenden Feldnummern wie im folgenden Beispiel reserviert werden.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Das `reserved`-Schlüsselwort kann auch als Platzhalter für Felder verwendet werden, die möglicherweise in der Zukunft hinzugefügt werden. Zusammenhängende Feldnummern können mit dem `to`-Schlüsselwort als Bereich ausgedrückt werden.

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
