---
title: Protobuf-Enumerationen-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie Enumerationen in protobuf deklarieren und verwenden.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543143"
---
# <a name="protobuf-enumerations"></a>Protobuf-Enumerationen

Protobuf unterstützt Enumerationstypen. Diese Unterstützung wurde im vorherigen Abschnitt erläutert, in dem eine-Auflistung verwendet wurde, um den Typ eines `Oneof` Felds zu bestimmen. Sie können eigene Enumerationstypen definieren, und protobuf kompiliert Sie in C# Enumerationstypen. 

Da Sie protobuf mit verschiedenen Sprachen verwenden können, unterscheiden sich die Benennungs Konventionen für Enumerationen C# von den Konventionen. Der Code-Generator konvertiert die Namen jedoch in den herkömmlichen C# Fall. Wenn die Pascal-Case-Entsprechung des Feldnamens mit dem Enumerationsnamen beginnt, wird Sie entfernt.

In der folgenden protobuf-Enumeration werden den Feldern z. b. `ACCOUNT_STATUS`vorangestellt. Dieses Präfix entspricht dem Namen der "Pascal-Case-Enumeration", "`AccountStatus`".

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Der Generator erstellt eine C# Aufzählung, die dem folgenden Code entspricht:

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

Protobuf-Enumerationsdefinitionen *müssen* als erstes Feld eine Konstante von 0 (null) aufweisen. Wie in C#können Sie mehrere Felder mit dem gleichen Wert deklarieren. Sie müssen diese Option jedoch explizit aktivieren, indem Sie die Option `allow_alias` in der-Aufzählung verwenden:

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

Wenn Sie `product.AvailableIn` auf `Region.NorthAmerica | Region.SouthAmerica`festlegen, wird es als ganzzahliger Wert `3`serialisiert. Wenn ein Client oder Server versucht, den Wert zu deserialisieren, findet keine Entsprechung in der Enumerationsdefinition für `3`. Das Ergebnis wird `Region.None`.

Die beste Möglichkeit zum Arbeiten mit mehreren Enumerationswerten in protobuf ist die Verwendung eines `repeated` Felds des Enumerationstyps.

>[!div class="step-by-step"]
>[Zurück](protobuf-any-oneof.md)
>[Weiter](protobuf-maps.md)
