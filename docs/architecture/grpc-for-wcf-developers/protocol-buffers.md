---
title: Protokollpuffer - gRPC für WCF-Entwickler
description: Einführung in das Protokollpufferdrahtformat, das für gRPC-Netzwerke verwendet wird.
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147931"
---
# <a name="protocol-buffers"></a><span data-ttu-id="038e9-103">Protokollpuffer</span><span class="sxs-lookup"><span data-stu-id="038e9-103">Protocol buffers</span></span>

<span data-ttu-id="038e9-104">gRPC-Dienste senden und empfangen Daten als *Protobuf-Nachrichten (Protocol Buffer),* ähnlich wie Datenverträge in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="038e9-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="038e9-105">Protobuf ist eine effiziente Möglichkeit, strukturierte Daten für Maschinen zum Lesen und Schreiben zu serialisieren, ohne den Overhead, den menschenlesbare Formate wie XML oder JSON verursachen.</span><span class="sxs-lookup"><span data-stu-id="038e9-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="038e9-106">In diesem Kapitel wird erläutert, wie Protobuf funktioniert und wie Sie Ihre eigenen Protobuf-Nachrichten definieren.</span><span class="sxs-lookup"><span data-stu-id="038e9-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="038e9-107">Wie Protobuf funktioniert</span><span class="sxs-lookup"><span data-stu-id="038e9-107">How Protobuf works</span></span>

<span data-ttu-id="038e9-108">Die meisten .NET-Objektserialisierungstechniken, einschließlich der WCF-Datenverträge, verwenden Reflektion, um die Objektstruktur zur Laufzeit zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="038e9-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="038e9-109">Im Gegensatz dazu müssen Sie in den meisten Protobuf-Bibliotheken die Struktur im `.proto` Voraus definieren, indem Sie eine dedizierte Sprache (*Protokollpuffersprache*) in einer Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="038e9-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="038e9-110">Ein Compiler verwendet diese Datei dann, um Code für eine der unterstützten Plattformen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="038e9-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="038e9-111">Zu den unterstützten Plattformen gehören .NET, Java, C/C++, JavaScript und viele mehr.</span><span class="sxs-lookup"><span data-stu-id="038e9-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span>

<span data-ttu-id="038e9-112">Der Protobuf-Compiler `protoc`, wird von Google verwaltet, obwohl alternative Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="038e9-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="038e9-113">Der generierte Code ist effizient und optimiert für eine schnelle Serialisierung und Deserialisierung von Daten.</span><span class="sxs-lookup"><span data-stu-id="038e9-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="038e9-114">Das Protobuf-Drahtformat ist eine binäre Codierung.</span><span class="sxs-lookup"><span data-stu-id="038e9-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="038e9-115">Es verwendet einige clevere Tricks, um die Anzahl der Bytes zu minimieren, die verwendet werden, um Nachrichten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="038e9-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="038e9-116">Kenntnisse des binären Codierungsformats sind nicht erforderlich, um Protobuf zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="038e9-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="038e9-117">Aber wenn Sie interessiert sind, können Sie mehr darüber auf [der Protocol Buffers Website](https://developers.google.com/protocol-buffers/docs/encoding)erfahren.</span><span class="sxs-lookup"><span data-stu-id="038e9-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="038e9-118">[VorherigeS](why-grpc.md)
>[Weiter](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="038e9-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
