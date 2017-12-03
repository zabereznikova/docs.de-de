---
title: Serialisierung in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ab8f86b66e92ea250fbe20e8bcb27e6706302db4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="serialization-in-net"></a><span data-ttu-id="5805a-102">Serialisierung in .NET</span><span class="sxs-lookup"><span data-stu-id="5805a-102">Serialization in .NET</span></span>
<span data-ttu-id="5805a-103">Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5805a-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="5805a-104">Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5805a-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="5805a-105">Zusammen ermöglichen es diese Prozesse, dass Daten einfach gespeichert und übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="5805a-105">Together, these processes allow data to be easily stored and transferred.</span></span>  
  
<span data-ttu-id="5805a-106">Zwei Serialisierungstechnologien für .NET-Funktionen:</span><span class="sxs-lookup"><span data-stu-id="5805a-106">.NET features two serialization technologies:</span></span>  
  
-   <span data-ttu-id="5805a-107">Bei der binären Serialisierung wird die Typtreue beibehalten. Dies ist nützlich, um den Zustand eines Objekts zwischen verschiedenen Aufrufen einer Anwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5805a-107">Binary serialization preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="5805a-108">So können Sie z.&#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren.</span><span class="sxs-lookup"><span data-stu-id="5805a-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="5805a-109">Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren.</span><span class="sxs-lookup"><span data-stu-id="5805a-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="5805a-110">Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="5805a-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
-   <span data-ttu-id="5805a-111">Bei der XML-Serialisierung werden nur öffentliche Eigenschaften und Felder serialisiert, und die Typtreue wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5805a-111">XML serialization serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="5805a-112">Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="5805a-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="5805a-113">Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar.</span><span class="sxs-lookup"><span data-stu-id="5805a-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="5805a-114">Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.</span><span class="sxs-lookup"><span data-stu-id="5805a-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5805a-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5805a-115">In This Section</span></span>  
[<span data-ttu-id="5805a-116">Vorgehensweise-Themen zur Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5805a-116">Serialization How-to Topics</span></span>](../../../docs/standard/serialization/serialization-how-to-topics.md)  
<span data-ttu-id="5805a-117">Enthält Links zu Gewusst-wie-Themen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5805a-117">Lists links to How-to topics contained in this section.</span></span>
  
[<span data-ttu-id="5805a-118">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5805a-118">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
<span data-ttu-id="5805a-119">Beschreibt den binären Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5805a-119">Describes the binary serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="5805a-120">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5805a-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
<span data-ttu-id="5805a-121">Beschreibt den XML- und SOAP-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5805a-121">Describes the XML and SOAP serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="5805a-122">Serialisierungstools</span><span class="sxs-lookup"><span data-stu-id="5805a-122">Serialization Tools</span></span>](../../../docs/standard/serialization/serialization-tools.md)  
<span data-ttu-id="5805a-123">Diese Tools sind hilfreich bei der Entwicklung von Serialisierungscode.</span><span class="sxs-lookup"><span data-stu-id="5805a-123">These tools help develop serialization code.</span></span>

[<span data-ttu-id="5805a-124">Serialisierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="5805a-124">Serialization Samples</span></span>](../../../docs/standard/serialization/serialization-samples.md)  
<span data-ttu-id="5805a-125">In den Beispielen wird veranschaulicht, wie die Serialisierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="5805a-125">The samples demonstrate how to do serialization.</span></span>

## <a name="reference"></a><span data-ttu-id="5805a-126">Verweis</span><span class="sxs-lookup"><span data-stu-id="5805a-126">Reference</span></span>
<span data-ttu-id="5805a-127"><xref:System.Runtime.Serialization> Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="5805a-127"><xref:System.Runtime.Serialization> Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="5805a-128">Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5805a-128">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>