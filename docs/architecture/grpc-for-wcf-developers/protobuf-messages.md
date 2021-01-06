---
title: Protobuf-Nachrichten-GrpC für WCF-Entwickler
description: Erfahren Sie, wie protobuf-Nachrichten in der IDL definiert und in c# generiert werden.
ms.date: 12/15/2020
ms.openlocfilehash: c1f2a3071d45dcbe4b98d747f19fed508bad102f
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938103"
---
# <a name="protobuf-messages"></a>Protobuf-Nachrichten

In diesem Abschnitt wird erläutert, wie Protokollpuffer (protobuf)-Nachrichten in Dateien deklariert werden `.proto` . Es werden die grundlegenden Konzepte von Feldnummern und-Typen erläutert, und es wird der c#-Code untersucht, den der `protoc` Compiler generiert.

Im restlichen Abschnitt wird ausführlicher erläutert, wie unterschiedliche Datentypen in protobuf dargestellt werden.

## <a name="declaring-a-message"></a>Deklarieren einer Nachricht

In Windows Communication Foundation (WCF) kann eine `Stock` Klasse für eine Börsenhandels Anwendung wie im folgenden Beispiel definiert werden:

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

Um die entsprechende Klasse in protobuf zu implementieren, müssen Sie Sie in der `.proto` Datei deklarieren. Der `protoc` Compiler generiert dann die .NET-Klasse als Teil des Buildprozesses.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

Die erste Zeile deklariert die verwendete Syntax Version. Version 3 der Sprache wurde in 2016 veröffentlicht. Es handelt sich um die Version, die für GrpC-Dienste empfohlen wird.

Die `option csharp_namespace` Zeile gibt den Namespace an, der für die generierten c#-Typen verwendet werden soll. Diese Option wird ignoriert, wenn die `.proto` Datei für andere Sprachen kompiliert wird. Protobuf-Dateien enthalten häufig sprachspezifische Optionen für mehrere Sprachen.

Die `Stock` Nachrichten Definition gibt vier Felder an. Jede verfügt über einen Typ, einen Namen und eine Feldnummer.

## <a name="field-numbers"></a>Feldnummern

Feldnummern sind ein wichtiger Bestandteil von protobuf. Sie werden verwendet, um Felder in den binär codierten Daten zu identifizieren, d. h., Sie können nicht von Version zu Version Ihres Dienstanbieter wechseln. Der Vorteil besteht darin, dass Abwärtskompatibilität und Vorwärtskompatibilität möglich sind. Von Clients und Diensten werden Feldnummern ignoriert, über die Sie nicht Bescheid wissen, solange fehlende Werte behandelt werden.

Im Binärformat wird die Feldzahl mit einem Typbezeichner kombiniert. Feldzahlen von 1 bis 15 können mit Ihrem Typ als einzelnes Byte codiert werden. Zahlen zwischen 16 und 2.047 nehmen 2 Bytes in Anspruch. Sie können den Wechsel erhöhen, wenn Sie mehr als 2.047 Felder für eine Nachricht aus irgendeinem Grund benötigen. Die Einzel Byte-IDs für die feldzahlen 1 bis 15 bieten eine bessere Leistung. Sie sollten Sie daher für die grundlegendsten, häufig verwendeten Felder verwenden.

## <a name="types"></a>Typen

Die Typdeklarationen verwenden die systemeigenen skalaren Datentypen von protobuf, die im [nächsten Abschnitt](protobuf-data-types.md)ausführlicher erläutert werden. Im weiteren Verlauf dieses Kapitels werden die integrierten Typen von protobuf behandelt, und es wird gezeigt, wie Sie sich auf allgemeine .NET-Typen beziehen.

> [!NOTE]
> Protobuf unterstützt einen- `decimal` Typ nicht. daher `double` wird stattdessen verwendet. Informationen zu Anwendungen, die eine vollständige Dezimal Genauigkeit erfordern, finden Sie im [Abschnitt zu dezimal](protobuf-data-types.md#decimals) stellen im nächsten Teil dieses Kapitels.

## <a name="the-generated-code"></a>Der generierte Code

Wenn Sie Ihre Anwendung erstellen, erstellt protobuf Klassen für jede Ihrer Nachrichten, wobei die systemeigenen Typen den c#-Typen entspricht. Der generierte `Stock` Typ hat die folgende Signatur:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

Der tatsächlich generierte Code ist weitaus komplizierter als dieser. Der Grund hierfür ist, dass jede Klasse den gesamten Code enthält, der zum Serialisieren und Deserialisieren in das binäre Wire-Format erforderlich ist.

### <a name="property-names"></a>Eigenschaftsnamen

Beachten Sie, dass der protobuf-compiler `PascalCase` auf die Eigenschaftsnamen angewendet hat, obwohl Sie sich `snake_case` in der `.proto` Datei befinden. Im [protobuf-Stil Handbuch](https://developers.google.com/protocol-buffers/docs/style) `snake_case` wird empfohlen, in ihren Nachrichten Definitionen zu verwenden, damit die Codegenerierung für andere Plattformen den erwarteten Fall für ihre Konventionen erzeugt.

>[!div class="step-by-step"]
>[Zurück](protocol-buffers.md)
>[Weiter](protobuf-data-types.md)
