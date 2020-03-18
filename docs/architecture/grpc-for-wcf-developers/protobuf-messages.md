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
# <a name="protobuf-messages"></a><span data-ttu-id="444b9-103">Protobuf-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="444b9-103">Protobuf messages</span></span>

<span data-ttu-id="444b9-104">In diesem Abschnitt wird erläutert, wie Protokollpuffernachrichten `.proto` (Protobuf) in Dateien deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="444b9-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="444b9-105">Es werden die grundlegenden Konzepte von Feldnummern und -typen erläutert, und es wird der vom `protoc` Compiler generierte C-Code untersucht.</span><span class="sxs-lookup"><span data-stu-id="444b9-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="444b9-106">Im weiteren Verlauf des Kapitels wird näher erläutert, wie verschiedene Datentypen in Protobuf dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="444b9-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="444b9-107">Deklarieren einer Nachricht</span><span class="sxs-lookup"><span data-stu-id="444b9-107">Declaring a message</span></span>

<span data-ttu-id="444b9-108">In Windows Communication Foundation (WCF) kann eine `Stock` Klasse für eine Börsenhandelsanwendung wie im folgenden Beispiel definiert werden:</span><span class="sxs-lookup"><span data-stu-id="444b9-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

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

<span data-ttu-id="444b9-109">Um die entsprechende Klasse in Protobuf zu `.proto` implementieren, müssen Sie sie in der Datei deklarieren.</span><span class="sxs-lookup"><span data-stu-id="444b9-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="444b9-110">Der `protoc` Compiler generiert dann die .NET-Klasse als Teil des Buildprozesses.</span><span class="sxs-lookup"><span data-stu-id="444b9-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

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

<span data-ttu-id="444b9-111">Die erste Zeile deklariert die syntaxe Version, die verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="444b9-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="444b9-112">Version 3 der Sprache wurde 2016 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="444b9-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="444b9-113">Es ist die Version, die wir für gRPC-Dienste empfehlen.</span><span class="sxs-lookup"><span data-stu-id="444b9-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="444b9-114">Die `option csharp_namespace` Zeile gibt den Namespace an, der für die generierten C-Typen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="444b9-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="444b9-115">Diese Option wird ignoriert, wenn die `.proto` Datei für andere Sprachen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="444b9-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="444b9-116">Protobuf-Dateien enthalten oft sprachspezifische Optionen für mehrere Sprachen.</span><span class="sxs-lookup"><span data-stu-id="444b9-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="444b9-117">Die `Stock` Nachrichtendefinition gibt vier Felder an.</span><span class="sxs-lookup"><span data-stu-id="444b9-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="444b9-118">Jeder hat einen Typ, einen Namen und eine Feldnummer.</span><span class="sxs-lookup"><span data-stu-id="444b9-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="444b9-119">Feldnummern</span><span class="sxs-lookup"><span data-stu-id="444b9-119">Field numbers</span></span>

<span data-ttu-id="444b9-120">Feldnummern sind ein wichtiger Teil von Protobuf.</span><span class="sxs-lookup"><span data-stu-id="444b9-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="444b9-121">Sie werden verwendet, um Felder in den binärcodierten Daten zu identifizieren, was bedeutet, dass sie nicht von Version zu Version Ihres Dienstes wechseln können.</span><span class="sxs-lookup"><span data-stu-id="444b9-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="444b9-122">Der Vorteil ist, dass Abwärtskompatibilität und Vorwärtskompatibilität möglich sind.</span><span class="sxs-lookup"><span data-stu-id="444b9-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="444b9-123">Clients und Dienste ignorieren feldnummern, von denen sie nichts wissen, solange die Möglichkeit fehlender Werte behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="444b9-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="444b9-124">Im Binärformat wird die Feldnummer mit einem Typbezeichner kombiniert.</span><span class="sxs-lookup"><span data-stu-id="444b9-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="444b9-125">Feldnummern von 1 bis 15 können mit ihrem Typ als einzelnes Byte kodiert werden.</span><span class="sxs-lookup"><span data-stu-id="444b9-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="444b9-126">Zahlen von 16 bis 2.047 nehmen 2 Bytes.</span><span class="sxs-lookup"><span data-stu-id="444b9-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="444b9-127">Sie können höher gehen, wenn Sie mehr als 2.047 Felder für eine Nachricht aus irgendeinem Grund benötigen.</span><span class="sxs-lookup"><span data-stu-id="444b9-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="444b9-128">Die einzelnen Byte-IDs für die Feldnummern 1 bis 15 bieten eine bessere Leistung, daher sollten Sie sie für die einfachsten, häufig verwendeten Felder verwenden.</span><span class="sxs-lookup"><span data-stu-id="444b9-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="444b9-129">Typen</span><span class="sxs-lookup"><span data-stu-id="444b9-129">Types</span></span>

<span data-ttu-id="444b9-130">Die Typdeklarationen verwenden die systemeigenen skalaren Datentypen von Protobuf, die im [nächsten Abschnitt](protobuf-data-types.md)ausführlicher behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="444b9-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="444b9-131">Der Rest dieses Kapitels behandelt die integrierten Typen von Protobuf und zeigt, wie sie sich auf gängige .NET-Typen beziehen.</span><span class="sxs-lookup"><span data-stu-id="444b9-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="444b9-132">Protobuf unterstützt keinen `decimal` Typ nativ, `double` wird daher verwendet.</span><span class="sxs-lookup"><span data-stu-id="444b9-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="444b9-133">Anwendungen, die eine vollständige Dezimalgenauigkeit erfordern, finden Sie im Abschnitt über Dezimalstellen im nächsten Teil dieses [Kapitels.](protobuf-data-types.md#decimals)</span><span class="sxs-lookup"><span data-stu-id="444b9-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="444b9-134">Der generierte Code</span><span class="sxs-lookup"><span data-stu-id="444b9-134">The generated code</span></span>

<span data-ttu-id="444b9-135">Wenn Sie Ihre Anwendung erstellen, erstellt Protobuf Klassen für jede Ihrer Nachrichten und ordnet deren systemeigene Typen den C-Typen zu.</span><span class="sxs-lookup"><span data-stu-id="444b9-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="444b9-136">Der `Stock` generierte Typ hätte die folgende Signatur:</span><span class="sxs-lookup"><span data-stu-id="444b9-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="444b9-137">Der tatsächlich generierte Code ist viel komplizierter als dieser.</span><span class="sxs-lookup"><span data-stu-id="444b9-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="444b9-138">Der Grund dafür ist, dass jede Klasse den gesamten Code enthält, der zum Serialisieren und Deserialisieren in das binäre Drahtformat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="444b9-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="444b9-139">Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="444b9-139">Property names</span></span>

<span data-ttu-id="444b9-140">Beachten Sie, dass der `PascalCase` Protobuf-Compiler auf `snake_case` die `.proto` Eigenschaftsnamen angewendet wurde, obwohl sie sich in der Datei befanden.</span><span class="sxs-lookup"><span data-stu-id="444b9-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="444b9-141">Im [Protobuf-Stilhandbuch](https://developers.google.com/protocol-buffers/docs/style) wird empfohlen, in Ihren Nachrichtendefinitionen so zu verwenden, `snake_case` dass die Codegenerierung für andere Plattformen den erwarteten Fall für ihre Konventionen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="444b9-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="444b9-142">[VorherigeS](protocol-buffers.md)
>[Weiter](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="444b9-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
