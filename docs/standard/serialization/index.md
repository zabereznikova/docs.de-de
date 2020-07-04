---
title: 'Serialisierung: .NET'
description: Dieser Artikel enthält Informationen zu .NET-Serialisierungstechnologien, einschließlich binärer Serialisierung, XML- und SOAP-Serialisierung und JSON-Serialisierung.
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "85840303"
---
# <a name="serialization-in-net"></a><span data-ttu-id="1b18b-103">Serialisierung in .NET</span><span class="sxs-lookup"><span data-stu-id="1b18b-103">Serialization in .NET</span></span>

<span data-ttu-id="1b18b-104">Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b18b-104">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="1b18b-105">Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1b18b-105">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="1b18b-106">Zusammen ermöglichen es diese Prozesse, dass Daten gespeichert und übertragen werden können.</span><span class="sxs-lookup"><span data-stu-id="1b18b-106">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="1b18b-107">.NET verwendet die folgenden Serialisierungstechnologien:</span><span class="sxs-lookup"><span data-stu-id="1b18b-107">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="1b18b-108">Bei der [binären Serialisierung](binary-serialization.md) wird die Typtreue beibehalten. Dies ist nützlich, um den Zustand eines Objekts zwischen verschiedenen Aufrufen einer Anwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1b18b-108">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="1b18b-109">So können Sie z.&#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1b18b-109">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="1b18b-110">Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1b18b-110">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="1b18b-111">Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1b18b-111">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="1b18b-112">Bei der [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md) werden nur öffentliche Eigenschaften und Felder serialisiert, und die Typtreue wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1b18b-112">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="1b18b-113">Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="1b18b-113">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="1b18b-114">Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar.</span><span class="sxs-lookup"><span data-stu-id="1b18b-114">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="1b18b-115">Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.</span><span class="sxs-lookup"><span data-stu-id="1b18b-115">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="1b18b-116">Bei der [JSON-Serialisierung](system-text-json-overview.md) werden nur öffentliche Eigenschaften serialisiert, und die Typtreue wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1b18b-116">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="1b18b-117">JSON ist ein offener Standard und stellt eine attraktive Möglichkeit für den Datenaustausch im Internet dar.</span><span class="sxs-lookup"><span data-stu-id="1b18b-117">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="1b18b-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="1b18b-118">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="1b18b-119">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1b18b-119">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="1b18b-120">Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1b18b-120">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="1b18b-121">Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im JSON-Format verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1b18b-121">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
