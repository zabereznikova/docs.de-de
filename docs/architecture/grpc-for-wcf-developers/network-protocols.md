---
title: 'Netzwerkprotokolle: GrpC für WCF-Entwickler'
description: Eine Übersicht über die GrpC-Netzwerkprotokolle.
ms.date: 09/02/2019
ms.openlocfilehash: 801d57c95aec748e5dcf667ca480775ff945b55c
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938558"
---
# <a name="network-protocols"></a><span data-ttu-id="51306-103">Netzwerkprotokolle</span><span class="sxs-lookup"><span data-stu-id="51306-103">Network protocols</span></span>

<span data-ttu-id="51306-104">Im Gegensatz zu Windows Communication Foundation (WCF) verwendet GrpC http/2 als Basis für das Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="51306-104">Unlike Windows Communication Foundation (WCF), gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="51306-105">Dieses Protokoll bietet gegenüber WCF und SOAP bedeutende Vorteile, die nur mit HTTP/1.1 funktionieren.</span><span class="sxs-lookup"><span data-stu-id="51306-105">This protocol offers significant advantages over WCF and SOAP, which operate only on HTTP/1.1.</span></span> <span data-ttu-id="51306-106">Für Entwickler, die GrpC verwenden möchten, da es keine Alternative zu http/2 gibt, wäre es der ideale Moment, um http/2 ausführlicher zu untersuchen und zusätzliche Vorteile der Verwendung von GrpC zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="51306-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits of using gRPC.</span></span>

<span data-ttu-id="51306-107">HTTP/2, von der Internet Engineering Task Force in 2015 veröffentlicht, wurde vom experimentellen SPDY-Protokoll abgeleitet, das bereits von Google verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="51306-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="51306-108">Sie wurde speziell für eine effizientere, schnellere und sicherere Sicherheit als HTTP/1.1 entwickelt.</span><span class="sxs-lookup"><span data-stu-id="51306-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="51306-109">Wichtige Features von http/2</span><span class="sxs-lookup"><span data-stu-id="51306-109">Key features of HTTP/2</span></span>

<span data-ttu-id="51306-110">Diese Liste zeigt einige der wichtigsten Features und Vorteile von http/2:</span><span class="sxs-lookup"><span data-stu-id="51306-110">This list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="51306-111">Binäres Protokoll</span><span class="sxs-lookup"><span data-stu-id="51306-111">Binary protocol</span></span>

<span data-ttu-id="51306-112">Anforderungs-/Antwort-Zyklen benötigen keine Textbefehle mehr.</span><span class="sxs-lookup"><span data-stu-id="51306-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="51306-113">Diese Aktivität vereinfacht die Implementierung von Befehlen und beschleunigt Sie.</span><span class="sxs-lookup"><span data-stu-id="51306-113">This activity simplifies and speeds up the implementation of commands.</span></span> <span data-ttu-id="51306-114">Insbesondere ist die Datenverarbeitung schneller und beansprucht weniger Arbeitsspeicher, die Netzwerk Latenz wird mit offensichtlichen, zusammenhängenden Verbesserungen der Geschwindigkeit verringert, und es gibt eine allgemeine Nutzung der Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="51306-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="51306-115">Datenströme</span><span class="sxs-lookup"><span data-stu-id="51306-115">Streams</span></span>

<span data-ttu-id="51306-116">Streams ermöglichen das Erstellen langlebiger Verbindungen zwischen Absender und Empfänger, über die mehrere Nachrichten oder Frames asynchron gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="51306-116">Streams allow you to create long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="51306-117">Mehrere Datenströme können über eine einzelne HTTP/2-Verbindung unabhängig voneinander betrieben werden.</span><span class="sxs-lookup"><span data-stu-id="51306-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="51306-118">Anfordern von Multiplexing über eine einzelne TCP-Verbindung</span><span class="sxs-lookup"><span data-stu-id="51306-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="51306-119">Diese Funktion ist eine der wichtigsten Innovationen von http/2.</span><span class="sxs-lookup"><span data-stu-id="51306-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="51306-120">Da es mehrere parallele Datenanforderungen zulässt, ist es jetzt möglich, Webdateien gleichzeitig von einem einzelnen Server herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="51306-120">Because it allows multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="51306-121">Websites werden schneller geladen, und der Optimierungsbedarf wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="51306-121">Websites load faster, and the need for optimization is reduced.</span></span> <span data-ttu-id="51306-122">Eine Kopfzeile (SOF-Line, Hol), in der Antworten, die bereit sind, bis zum Abschluss einer früheren Anforderung gewartet werden müssen, ebenfalls verringert werden (auch wenn eine Hol-Blockierung auf der TCP-Transport Ebene auftreten kann).</span><span class="sxs-lookup"><span data-stu-id="51306-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP-transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="51306-123">NET. TCP-ähnliche Leistung, plattformübergreifend</span><span class="sxs-lookup"><span data-stu-id="51306-123">Net.TCP-like performance, cross-platform</span></span>

<span data-ttu-id="51306-124">Grundsätzlich bietet die Kombination aus GrpC und http/2 Entwicklern mindestens die entsprechende Geschwindigkeit und Effizienz von net. TCP-Bindungen für WCF, und in einigen Fällen ist dies noch schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="51306-124">Fundamentally, the combination of gRPC and HTTP/2 offers developers at least the equivalent speed and efficiency of Net.TCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="51306-125">Aber im Gegensatz zu net. TCP ist GrpC über http/2 nicht auf .NET-Anwendungen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="51306-125">But, unlike Net.TCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="51306-126">[Zurück](interface-definition-language.md)
>[Weiter](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="51306-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
