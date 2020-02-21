---
title: Protokollpuffer-GrpC für WCF-Entwickler
description: Einführung in das Protokollpuffer-Wire-Format, das für GrpC-Netzwerke verwendet wird.
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503455"
---
# <a name="protocol-buffers"></a><span data-ttu-id="0e3a5-103">Protokollpuffer</span><span class="sxs-lookup"><span data-stu-id="0e3a5-103">Protocol buffers</span></span>

<span data-ttu-id="0e3a5-104">GrpC-Dienste senden und empfangen Daten als *Protokollpuffer (protobuf)-Nachrichten*, ähnlich wie Datenverträge in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0e3a5-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="0e3a5-105">Protobuf ist ein effizientes Verfahren zum Serialisieren strukturierter Daten für Computer, die gelesen und geschrieben werden können, ohne den mehr Aufwand, den die menschenlesbaren Formate wie XML oder JSON verursachen.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="0e3a5-106">In diesem Kapitel wird erläutert, wie protobuf funktioniert und wie Sie Ihre eigenen protobuf-Nachrichten definieren.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="0e3a5-107">Funktionsweise von protobuf</span><span class="sxs-lookup"><span data-stu-id="0e3a5-107">How Protobuf works</span></span>

<span data-ttu-id="0e3a5-108">Die meisten .net-objektserialisierungstechnologien, einschließlich der Datenverträge von WCF, funktionieren mithilfe von Reflektion zur Analyse der Objektstruktur zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="0e3a5-109">Im Gegensatz dazu erfordern die meisten protobuf-Bibliotheken, dass Sie die Struktur im Vordergrund definieren, indem Sie eine dedizierte Sprache (*Protokollpuffer Sprache*) in einer `.proto` Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="0e3a5-110">Ein Compiler verwendet diese Datei dann, um Code für jede der unterstützten Plattformen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="0e3a5-111">Zu den unterstützten Plattformen zählen .net,C++Java, C/, JavaScript und viele mehr.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span> 

<span data-ttu-id="0e3a5-112">Der protobuf-compiler (`protoc`) wird von Google verwaltet, obwohl alternative Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="0e3a5-113">Der generierte Code ist effizient und optimiert für die schnelle Serialisierung und Deserialisierung von Daten.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="0e3a5-114">Das protobuf-Wire-Format ist eine binäre Codierung.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="0e3a5-115">Es werden einige clevere Tricks verwendet, um die Anzahl der Bytes zu minimieren, die für die Darstellung von Nachrichten</span><span class="sxs-lookup"><span data-stu-id="0e3a5-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="0e3a5-116">Die Verwendung von protobuf ist nicht erforderlich, um das binäre Codierungsformat zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="0e3a5-117">Wenn Sie allerdings interessiert sind, können Sie auf [der Website für Protokollpuffer](https://developers.google.com/protocol-buffers/docs/encoding)mehr darüber erfahren.</span><span class="sxs-lookup"><span data-stu-id="0e3a5-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0e3a5-118">[Zurück](why-grpc.md)
>[Weiter](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="0e3a5-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
