---
title: Protobuf-Enumerationen - gRPC für WCF-Entwickler
description: Erfahren Sie, wie Sie Enumerationen in Protobuf deklarieren und verwenden.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148074"
---
# <a name="protobuf-enumerations"></a>Protobuf-Enumerationen

Protobuf unterstützt Enumerationstypen. Diese Unterstützung wurde im vorherigen Abschnitt angezeigt, in dem eine `Oneof` Enumerat verwendet wurde, um den Typ eines Felds zu bestimmen. Sie können eigene Enumerationstypen definieren, und Protobuf kompiliert sie in C-Enum-Typen.

Da Sie Protobuf in verschiedenen Sprachen verwenden können, unterscheiden sich die Namenskonventionen für Enumerationen von den C-Konventionen. Der Codegenerator konvertiert jedoch die Namen in den traditionellen C-Fall. Wenn das Pascal-Case-Äquivalent des Feldnamens mit dem Enumerationsnamen beginnt, wird es entfernt.

In der folgenden Protobuf-Enumeration werden den Feldern `ACCOUNT_STATUS`beispielsweise vorangestellt. Dieses Präfix entspricht dem Pascal-case-Enumnamen . `AccountStatus`

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Der Generator erstellt eine C-Enumere, die dem folgenden Code entspricht:

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

Protobuf-Enumerationsdefinitionen *müssen* als erstes Feld eine Nullkonstante haben. Wie in C- können Sie mehrere Felder mit demselben Wert deklarieren. Sie müssen diese Option jedoch `allow_alias` explizit aktivieren, indem Sie die Option in der Enumerat verwenden:

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

Sie können Enumerationen auf der `.proto` obersten Ebene in einer Datei oder in einer Nachrichtendefinition verschachtelt deklarieren. Verschachtelte Enumerationen werden – wie geschachtelte Nachrichten – innerhalb der `.Types` statischen Klasse in der generierten Nachrichtenklasse deklariert.

Es gibt keine Möglichkeit, das [[Flags]-Attribut](xref:System.FlagsAttribute) auf eine protobuf-generierte Enumerat anzuwenden, und Protobuf versteht bitweise Enumeronkombinationen nicht. Sehen Sie sich das folgende Beispiel an:

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

Wenn Sie `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`auf festlegen, wird er als Ganzzahlwert `3`serialisiert. Wenn ein Client oder Server versucht, den Wert zu deserialisieren, findet `3`er keine Übereinstimmung in der Enumeratdefinition für . Das Ergebnis `Region.None`ist .

Die beste Möglichkeit, mit mehreren Enumerumwerten in `repeated` Protobuf zu arbeiten, besteht darin, ein Feld des Enumerumtyps zu verwenden.

>[!div class="step-by-step"]
>[VorherigeS](protobuf-any-oneof.md)
>[Weiter](protobuf-maps.md)
