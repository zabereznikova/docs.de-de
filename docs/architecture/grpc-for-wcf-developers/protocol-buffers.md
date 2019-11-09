---
title: Protokollpuffer-GrpC für WCF-Entwickler
description: Einführung in das Protokollpuffer-Wire-Format, das für GrpC-Netzwerke verwendet wird.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 6b47c7f3576134d8ee44f79e329cc4879661e6c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841384"
---
# <a name="protocol-buffers"></a><span data-ttu-id="561ed-103">Protokollpuffer</span><span class="sxs-lookup"><span data-stu-id="561ed-103">Protocol buffers</span></span>

<span data-ttu-id="561ed-104">GrpC-Dienste senden und empfangen Daten als *Protokollpuffer (protobuf)-Nachrichten*, ähnlich den WCF-Daten Verträgen.</span><span class="sxs-lookup"><span data-stu-id="561ed-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="561ed-105">Protobuf ist ein effizientes Verfahren zum Serialisieren strukturierter Daten für Computer, die gelesen und geschrieben werden können, ohne den mehr Aufwand, den die menschenlesbaren Formate wie XML oder JSON verursachen.</span><span class="sxs-lookup"><span data-stu-id="561ed-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="561ed-106">In diesem Kapitel wird erläutert, wie protobuf funktioniert und wie Sie Ihre eigenen protobuf-Nachrichten definieren.</span><span class="sxs-lookup"><span data-stu-id="561ed-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="561ed-107">Funktionsweise von protobuf</span><span class="sxs-lookup"><span data-stu-id="561ed-107">How Protobuf works</span></span>

<span data-ttu-id="561ed-108">Die meisten .net-objektserialisierungstechnologien, einschließlich der Datenverträge von WCF, funktionieren mithilfe von Reflektion, um die Objektstruktur zur Laufzeit zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="561ed-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="561ed-109">Im Gegensatz dazu erfordern die meisten protobuf-Bibliotheken, dass Sie die Struktur im Vordergrund mithilfe einer dedizierten Sprache (*Protokollpuffer Sprache*) in einer `.proto` Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="561ed-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="561ed-110">Diese Datei wird dann von einem Compiler verwendet, um Code für eine der unterstützten Plattformen zu generieren, einschließlich .net, JavaC++, C/, JavaScript und viele mehr.</span><span class="sxs-lookup"><span data-stu-id="561ed-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="561ed-111">Der protobuf-compiler (`protoc`) wird von Google verwaltet, obwohl alternative Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="561ed-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="561ed-112">Der generierte Code ist effizient und optimiert für die schnelle Serialisierung und Deserialisierung von Daten.</span><span class="sxs-lookup"><span data-stu-id="561ed-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="561ed-113">Das protobuf-Wire-Format selbst ist eine binäre Codierung, die einige clevere Tricks verwendet, um die Anzahl von Bytes zu minimieren, die zum Darstellen von Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="561ed-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="561ed-114">Das binäre Codierungsformat ist für die Verwendung von protobuf nicht erforderlich. Wenn Sie jedoch interessiert sind, können Sie auf [der Website "Protokollpuffer](https://developers.google.com/protocol-buffers/docs/encoding)" mehr darüber erfahren.</span><span class="sxs-lookup"><span data-stu-id="561ed-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="561ed-115">[Zurück](why-grpc.md)
>[Weiter](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="561ed-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
