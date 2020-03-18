---
title: Protobuf-Meldungen - gRPC für WCF-Entwickler
description: Erfahren Sie, wie Protobuf-Nachrichten in der IDL definiert und in C-Code generiert werden.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147983"
---
# <a name="protobuf-messages"></a>Protobuf-Nachrichten

In diesem Abschnitt wird erläutert, wie Protokollpuffernachrichten `.proto` (Protobuf) in Dateien deklariert werden. Es werden die grundlegenden Konzepte von Feldnummern und -typen erläutert, und es wird der vom `protoc` Compiler generierte C-Code untersucht.

Im weiteren Verlauf des Kapitels wird näher erläutert, wie verschiedene Datentypen in Protobuf dargestellt werden.

## <a name="declaring-a-message"></a>Deklarieren einer Nachricht

In Windows Communication Foundation (WCF) kann eine `Stock` Klasse für eine Börsenhandelsanwendung wie im folgenden Beispiel definiert werden:

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

Um die entsprechende Klasse in Protobuf zu `.proto` implementieren, müssen Sie sie in der Datei deklarieren. Der `protoc` Compiler generiert dann die .NET-Klasse als Teil des Buildprozesses.

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

Die erste Zeile deklariert die syntaxe Version, die verwendet wird. Version 3 der Sprache wurde 2016 veröffentlicht. Es ist die Version, die wir für gRPC-Dienste empfehlen.

Die `option csharp_namespace` Zeile gibt den Namespace an, der für die generierten C-Typen verwendet werden soll. Diese Option wird ignoriert, wenn die `.proto` Datei für andere Sprachen kompiliert wird. Protobuf-Dateien enthalten oft sprachspezifische Optionen für mehrere Sprachen.

Die `Stock` Nachrichtendefinition gibt vier Felder an. Jeder hat einen Typ, einen Namen und eine Feldnummer.

## <a name="field-numbers"></a>Feldnummern

Feldnummern sind ein wichtiger Teil von Protobuf. Sie werden verwendet, um Felder in den binärcodierten Daten zu identifizieren, was bedeutet, dass sie nicht von Version zu Version Ihres Dienstes wechseln können. Der Vorteil ist, dass Abwärtskompatibilität und Vorwärtskompatibilität möglich sind. Clients und Dienste ignorieren feldnummern, von denen sie nichts wissen, solange die Möglichkeit fehlender Werte behandelt wird.

Im Binärformat wird die Feldnummer mit einem Typbezeichner kombiniert. Feldnummern von 1 bis 15 können mit ihrem Typ als einzelnes Byte kodiert werden. Zahlen von 16 bis 2.047 nehmen 2 Bytes. Sie können höher gehen, wenn Sie mehr als 2.047 Felder für eine Nachricht aus irgendeinem Grund benötigen. Die einzelnen Byte-IDs für die Feldnummern 1 bis 15 bieten eine bessere Leistung, daher sollten Sie sie für die einfachsten, häufig verwendeten Felder verwenden.

## <a name="types"></a>Typen

Die Typdeklarationen verwenden die systemeigenen skalaren Datentypen von Protobuf, die im [nächsten Abschnitt](protobuf-data-types.md)ausführlicher behandelt werden. Der Rest dieses Kapitels behandelt die integrierten Typen von Protobuf und zeigt, wie sie sich auf gängige .NET-Typen beziehen.

> [!NOTE]
> Protobuf unterstützt keinen `decimal` Typ nativ, `double` wird daher verwendet. Anwendungen, die eine vollständige Dezimalgenauigkeit erfordern, finden Sie im Abschnitt über Dezimalstellen im nächsten Teil dieses [Kapitels.](protobuf-data-types.md#decimals)

## <a name="the-generated-code"></a>Der generierte Code

Wenn Sie Ihre Anwendung erstellen, erstellt Protobuf Klassen für jede Ihrer Nachrichten und ordnet deren systemeigene Typen den C-Typen zu. Der `Stock` generierte Typ hätte die folgende Signatur:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

Der tatsächlich generierte Code ist viel komplizierter als dieser. Der Grund dafür ist, dass jede Klasse den gesamten Code enthält, der zum Serialisieren und Deserialisieren in das binäre Drahtformat erforderlich ist.

### <a name="property-names"></a>Eigenschaftsnamen

Beachten Sie, dass der `PascalCase` Protobuf-Compiler auf `snake_case` die `.proto` Eigenschaftsnamen angewendet wurde, obwohl sie sich in der Datei befanden. Im [Protobuf-Stilhandbuch](https://developers.google.com/protocol-buffers/docs/style) wird empfohlen, in Ihren Nachrichtendefinitionen so zu verwenden, `snake_case` dass die Codegenerierung für andere Plattformen den erwarteten Fall für ihre Konventionen erzeugt.

>[!div class="step-by-step"]
>[VorherigeS](protocol-buffers.md)
>[Weiter](protobuf-data-types.md)
