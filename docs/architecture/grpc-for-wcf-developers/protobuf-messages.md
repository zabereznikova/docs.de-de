---
title: Protobuf-Nachrichten-GrpC für WCF-Entwickler
description: Erfahren Sie, wie protobuf-Nachrichten in der IDL definiert C#und in generiert werden.
ms.date: 09/09/2019
ms.openlocfilehash: c7375bafb7572b0eaa0458b0310a0114e3fd078c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543039"
---
# <a name="protobuf-messages"></a><span data-ttu-id="75002-103">Protobuf-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="75002-103">Protobuf messages</span></span>

<span data-ttu-id="75002-104">In diesem Abschnitt wird erläutert, wie Protokollpuffer (protobuf)-Nachrichten in `.proto` Dateien deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="75002-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="75002-105">Es werden die grundlegenden Konzepte von Feldnummern und-Typen erläutert, und der C# Code, den der `protoc` Compiler generiert, wird untersucht.</span><span class="sxs-lookup"><span data-stu-id="75002-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span> 

<span data-ttu-id="75002-106">Im restlichen Abschnitt wird ausführlicher erläutert, wie unterschiedliche Datentypen in protobuf dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75002-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="75002-107">Deklarieren einer Nachricht</span><span class="sxs-lookup"><span data-stu-id="75002-107">Declaring a message</span></span>

<span data-ttu-id="75002-108">In Windows Communication Foundation (WCF) kann eine `Stock` Klasse für eine Aktienmarkt-Handels Anwendung wie im folgenden Beispiel definiert werden:</span><span class="sxs-lookup"><span data-stu-id="75002-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

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

<span data-ttu-id="75002-109">Um die entsprechende Klasse in protobuf zu implementieren, müssen Sie Sie in der `.proto`-Datei deklarieren.</span><span class="sxs-lookup"><span data-stu-id="75002-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="75002-110">Der `protoc`-Compiler generiert dann die .NET-Klasse als Teil des Buildprozesses.</span><span class="sxs-lookup"><span data-stu-id="75002-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

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

<span data-ttu-id="75002-111">Die erste Zeile deklariert die verwendete Syntax Version.</span><span class="sxs-lookup"><span data-stu-id="75002-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="75002-112">Version 3 der Sprache wurde in 2016 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="75002-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="75002-113">Es handelt sich um die Version, die für GrpC-Dienste empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="75002-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="75002-114">Die `option csharp_namespace` Zeile gibt den Namespace an, der für die generierten C# Typen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="75002-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="75002-115">Diese Option wird ignoriert, wenn die `.proto`-Datei für andere Sprachen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="75002-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="75002-116">Protobuf-Dateien enthalten häufig sprachspezifische Optionen für mehrere Sprachen.</span><span class="sxs-lookup"><span data-stu-id="75002-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="75002-117">Die `Stock`-Nachrichten Definition gibt vier Felder an.</span><span class="sxs-lookup"><span data-stu-id="75002-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="75002-118">Jede verfügt über einen Typ, einen Namen und eine Feldnummer.</span><span class="sxs-lookup"><span data-stu-id="75002-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="75002-119">Feldnummern</span><span class="sxs-lookup"><span data-stu-id="75002-119">Field numbers</span></span>

<span data-ttu-id="75002-120">Feldnummern sind ein wichtiger Bestandteil von protobuf.</span><span class="sxs-lookup"><span data-stu-id="75002-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="75002-121">Sie werden verwendet, um Felder in den binär codierten Daten zu identifizieren, d. h., Sie können nicht von Version zu Version Ihres Dienstanbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="75002-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="75002-122">Der Vorteil besteht darin, dass Abwärtskompatibilität und Vorwärtskompatibilität möglich sind.</span><span class="sxs-lookup"><span data-stu-id="75002-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="75002-123">Von Clients und Diensten werden einfach Feldnummern ignoriert, über die Sie nicht Bescheid wissen, solange fehlende Werte behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="75002-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="75002-124">Im Binärformat wird die Feldzahl mit einem Typbezeichner kombiniert.</span><span class="sxs-lookup"><span data-stu-id="75002-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="75002-125">Feldzahlen von 1 bis 15 können mit Ihrem Typ als einzelnes Byte codiert werden.</span><span class="sxs-lookup"><span data-stu-id="75002-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="75002-126">Zahlen zwischen 16 und 2.047 nehmen 2 Bytes in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="75002-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="75002-127">Sie können den Wechsel erhöhen, wenn Sie mehr als 2.047 Felder für eine Nachricht aus irgendeinem Grund benötigen.</span><span class="sxs-lookup"><span data-stu-id="75002-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="75002-128">Die Einzel Byte-IDs für die feldzahlen 1 bis 15 bieten eine bessere Leistung, daher sollten Sie Sie für die grundlegendsten, häufig verwendeten Felder verwenden.</span><span class="sxs-lookup"><span data-stu-id="75002-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="75002-129">Typen</span><span class="sxs-lookup"><span data-stu-id="75002-129">Types</span></span>

<span data-ttu-id="75002-130">Die Typdeklarationen verwenden die systemeigenen skalaren Datentypen von protobuf, die im [nächsten Abschnitt](protobuf-data-types.md)ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="75002-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="75002-131">Im weiteren Verlauf dieses Kapitels werden die integrierten Typen von protobuf behandelt, und es wird gezeigt, wie Sie sich auf allgemeine .NET-Typen beziehen.</span><span class="sxs-lookup"><span data-stu-id="75002-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="75002-132">Protobuf unterstützt nicht die systemeigene Unterstützung eines `decimal` Typs, daher wird stattdessen `double` verwendet.</span><span class="sxs-lookup"><span data-stu-id="75002-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="75002-133">Informationen zu Anwendungen, die eine vollständige Dezimal Genauigkeit erfordern, finden Sie im [Abschnitt zu dezimal](protobuf-data-types.md#decimals) stellen im nächsten Teil dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="75002-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="75002-134">Der generierte Code</span><span class="sxs-lookup"><span data-stu-id="75002-134">The generated code</span></span>

<span data-ttu-id="75002-135">Wenn Sie Ihre Anwendung erstellen, erstellt protobuf Klassen für jede Ihrer Nachrichten, wobei die systemeigenen Typen C# zu-Typen werden.</span><span class="sxs-lookup"><span data-stu-id="75002-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="75002-136">Der generierte `Stock` Typ hat die folgende Signatur:</span><span class="sxs-lookup"><span data-stu-id="75002-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="75002-137">Der tatsächlich generierte Code ist weitaus komplizierter als dieser.</span><span class="sxs-lookup"><span data-stu-id="75002-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="75002-138">Der Grund hierfür ist, dass jede Klasse den gesamten Code enthält, der zum Serialisieren und Deserialisieren in das binäre Wire-Format erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="75002-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="75002-139">Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="75002-139">Property names</span></span>

<span data-ttu-id="75002-140">Beachten Sie, dass der protobuf-compiler `PascalCase` auf die Eigenschaftsnamen angewendet hat, obwohl Sie in der `.proto` Datei `snake_case` wurden.</span><span class="sxs-lookup"><span data-stu-id="75002-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="75002-141">Im [protobuf-Stil Handbuch](https://developers.google.com/protocol-buffers/docs/style) wird empfohlen, `snake_case` in ihren Nachrichten Definitionen zu verwenden, damit die Codegenerierung für andere Plattformen den erwarteten Fall für ihre Konventionen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="75002-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="75002-142">[Zurück](protocol-buffers.md)
>[Weiter](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="75002-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
