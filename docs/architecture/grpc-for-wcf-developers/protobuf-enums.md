---
title: Protobuf-Enumerationen-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie Enumerationen in protobuf deklarieren und verwenden.
ms.date: 09/09/2019
ms.openlocfilehash: 4ea4d03bede2a9ebfd1f2c3ee56f299e918800e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971575"
---
# <a name="protobuf-enumerations"></a>Protobuf-Enumerationen

Protobuf unterstützt Enumerationstypen, wie im vorherigen Abschnitt gezeigt, in dem eine Enumeration verwendet wurde, um den Typ eines `oneof` Felds zu bestimmen. Sie können eigene Enumerationstypen definieren, und protobuf kompiliert Sie C# in Enumerationstypen. Da protobuf mit verschiedenen Sprachen verwendet werden kann, unterscheiden sich die Benennungs Konventionen für Enumerationen C# von den Konventionen. Der Code-Generator ist jedoch clever und konvertiert die Namen in den herkömmlichen C# Fall. Wenn die Pascal-Case-Entsprechung des Feldnamens mit dem Enumerationsnamen beginnt, wird Sie entfernt.

In dieser protobuf-Enumeration werden den Feldern z. b. `ACCOUNT_STATUS`vorangestellt, was dem Namen der Pascal-fallenumeration entspricht: `AccountStatus`.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Daher erstellt der Generator eine C# Aufzählung, die dem folgenden Code entspricht:

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

Protobuf-Enumerationsdefinitionen **müssen** als erstes Feld eine Konstante von 0 (null) aufweisen. Wie in C#können Sie mehrere Felder mit demselben Wert deklarieren. Sie müssen diese Option jedoch explizit mithilfe der Option `allow_alias` in der Enumeration aktivieren:

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

Sie können Enumerationen auf der obersten Ebene in einer `.proto` Datei deklarieren oder innerhalb einer Nachrichten Definition geschachtelt. Geschachtelte Enumerationen – wie geschachtelte Nachrichten – werden innerhalb der statischen Klasse `.Types` in der generierten Message-Klasse deklariert.

Es gibt keine Möglichkeit, das [[Flags]](xref:System.FlagsAttribute) -Attribut auf eine protobuf-generierte Enumeration anzuwenden, und protobuf versteht keine bitweisen Enumeration-Kombinationen. Sehen Sie sich das folgende Beispiel an:

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

Wenn Sie `product.AvailableIn` auf `Region.NorthAmerica | Region.SouthAmerica`festlegen, wird es als ganzzahliger Wert `3`serialisiert. Wenn ein Client oder Server versucht, den Wert zu deserialisieren, findet keine Entsprechung in der Enumerationsdefinition für `3`, und das Ergebnis wird `Region.None`.

Die beste Möglichkeit zum Arbeiten mit mehreren Enumerationswerten in protobuf ist die Verwendung eines `repeated` Felds des Enumerationstyps.

>[!div class="step-by-step"]
>[Zurück](protobuf-any-oneof.md)
>[Weiter](protobuf-maps.md)
