---
title: Protobuf-Nachrichten-GrpC für WCF-Entwickler
description: Erfahren Sie, wie protobuf-Nachrichten in der IDL definiert C#und in generiert werden.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 9943478698acfbb54b3e1dd0e6a856d11b9266c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841468"
---
# <a name="protobuf-messages"></a>Protobuf-Nachrichten

In diesem Abschnitt wird erläutert, wie protobuf-Nachrichten in `.proto` Dateien deklariert werden, die grundlegenden Konzepte von Feldnummern und- C# Typen erläutert werden und der Code, der vom `protoc` Compiler generiert wird, untersucht wird. Im restlichen Abschnitt wird ausführlicher erläutert, wie unterschiedliche Datentypen in protobuf dargestellt werden.

## <a name="declaring-a-message"></a>Deklarieren einer Nachricht

In WCF kann eine `Stock`-Klasse für eine Handels Anwendung im Handel wie im folgenden Beispiel definiert werden:

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

Um die entsprechende Klasse in protobuf zu implementieren, muss Sie in der `.proto`-Datei deklariert werden. Der `protoc`-Compiler generiert dann die .NET-Klasse als Teil des Buildprozesses.

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

Die erste Zeile deklariert die verwendete Syntax Version. Version 3 der Sprache wurde in 2016 veröffentlicht und ist die empfohlene Version für GrpC-Dienste.

Die `option csharp_namespace` Zeile gibt den Namespace an, der für die generierten C# Typen verwendet werden soll. Diese Option wird ignoriert, wenn die `.proto`-Datei für andere Sprachen kompiliert wird. Es kommt häufig vor, dass protobuf-Dateien sprachspezifische Optionen für mehrere Sprachen enthalten.

Die `Stock`-Nachrichten Definition gibt vier Felder mit jeweils einem Typ, einem Namen und einer Feldzahl an.

## <a name="field-numbers"></a>Feldnummern

Feldnummern sind ein wichtiger Bestandteil von protobuf. Sie werden verwendet, um Felder in den binär codierten Daten zu identifizieren, d. h., Sie können nicht von Version zu Version Ihres Dienstanbieter wechseln. Der Vorteil besteht darin, dass die abwärts-und Vorwärtskompatibilität möglich ist. Clients und Dienste ignorieren einfach Feldnummern, von denen Sie nicht wissen, solange die Möglichkeit fehlender Werte behandelt wird.

Im Binärformat wird die Feldzahl mit einem Typbezeichner kombiniert. Feldzahlen von 1 bis 15 können mit Ihrem Typ als einzelnes Byte codiert werden. Zahlen zwischen 16 und 2047 nehmen 2 Bytes in Anspruch. Sie können den Wechsel erhöhen, wenn Sie mehr als 2047 Felder für eine Nachricht aus irgendeinem Grund benötigen. Die Einzel Byte-IDs für die feldzahlen 1 bis 15 bieten eine bessere Leistung, daher sollten Sie Sie für die grundlegendsten, häufig verwendeten Felder verwenden.

## <a name="types"></a>Typen

Die Typdeklarationen verwenden die systemeigenen skalaren Datentypen von protobuf, die im [nächsten Abschnitt](protobuf-data-types.md)ausführlicher erläutert werden. Im weiteren Verlauf dieses Kapitels werden die integrierten Typen von protobuf behandelt, und es wird gezeigt, wie Sie sich auf allgemeine .NET-Typen beziehen.

> [!NOTE]
> Protobuf unterstützt nicht die systemeigene Unterstützung für einen `decimal` Typ, daher wird stattdessen "Double" verwendet. Informationen zu Anwendungen, die eine vollständige Dezimal Genauigkeit erfordern, finden Sie im [Abschnitt zu dezimal](protobuf-data-types.md#decimals) stellen im nächsten Teil dieses Kapitels.

## <a name="the-generated-code"></a>Der generierte Code

Wenn Sie Ihre Anwendung erstellen, erstellt protobuf Klassen für jede Ihrer Nachrichten, wobei die systemeigenen Typen C# zu-Typen werden. Der generierte `Stock` Typ hat die folgende Signatur:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

Der tatsächlich generierte Code ist weitaus komplizierter als dies, da jede Klasse den gesamten Code enthält, der für die Serialisierung und Deserialisierung im binären Wire-Format erforderlich ist.

### <a name="property-names"></a>Eigenschaftsnamen

Beachten Sie, dass der protobuf-compiler `PascalCase` auf die Eigenschaftsnamen angewendet hat, obwohl Sie in der `.proto` Datei `snake_case` wurden. Im [protobuf-Stil Handbuch](https://developers.google.com/protocol-buffers/docs/style) wird empfohlen, `snake_case` in ihren Nachrichten Definitionen zu verwenden, damit die Codegenerierung für andere Plattformen den erwarteten Fall für ihre Konventionen erzeugt.

>[!div class="step-by-step"]
>[Zurück](protocol-buffers.md)
>[Weiter](protobuf-data-types.md)
