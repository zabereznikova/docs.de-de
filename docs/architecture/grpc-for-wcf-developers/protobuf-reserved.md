---
title: Protobuf reservierte Felder - gRPC für WCF-Entwickler
description: Erfahren Sie mehr über reservierte Felder für die versionsübergreifende Kompatibilität.
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111035"
---
# <a name="protobuf-reserved-fields"></a>Reservierte Protobuf-Felder

Die Abwärtskompatibilitätsgarantien in Protocol Buffer (Protobuf) basieren auf Feldnummern, die immer dasselbe Datenelement darstellen. Wenn ein Feld aus einer Nachricht in einer neuen Version des Dienstes entfernt wird, sollte diese Feldnummer niemals wiederverwendet werden. Sie können dies `reserved` erzwingen, indem Sie das Schlüsselwort verwenden.

Wenn `displayName` die `marketId` felder aus `Stock` der zuvor definierten Nachricht entfernt wurden, sollten ihre Feldnummern wie im folgenden Beispiel reserviert werden.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Sie können das `reserved` Schlüsselwort auch als Platzhalter für Felder verwenden, die in Zukunft hinzugefügt werden könnten. Sie können zusammenhängende Feldnummern als Bereich `to` ausdrücken, indem Sie das Schlüsselwort verwenden.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[VorherigeS](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)
