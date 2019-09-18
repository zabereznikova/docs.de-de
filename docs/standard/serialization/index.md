---
title: 'Serialisierung: .net'
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053349"
---
# <a name="serialization-in-net"></a><span data-ttu-id="5932c-102">Serialisierung in .NET</span><span class="sxs-lookup"><span data-stu-id="5932c-102">Serialization in .NET</span></span>

<span data-ttu-id="5932c-103">Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5932c-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="5932c-104">Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5932c-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="5932c-105">Diese Prozesse ermöglichen es Ihnen, Daten zu speichern und zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="5932c-105">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="5932c-106">.Net bietet die folgenden Serialisierungstechnologien:</span><span class="sxs-lookup"><span data-stu-id="5932c-106">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="5932c-107">Die [binäre Serialisierung](binary-serialization.md) behält die Typtreue bei, was für die Beibehaltung des Zustands eines Objekts zwischen verschiedenen Aufrufen einer Anwendung nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="5932c-107">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="5932c-108">So können Sie z.&#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren.</span><span class="sxs-lookup"><span data-stu-id="5932c-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="5932c-109">Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren.</span><span class="sxs-lookup"><span data-stu-id="5932c-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="5932c-110">Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="5932c-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="5932c-111">Die [XML-und SOAP-Serialisierung](xml-and-soap-serialization.md) serialisiert nur öffentliche Eigenschaften und Felder und bewahrt die Typtreue nicht.</span><span class="sxs-lookup"><span data-stu-id="5932c-111">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="5932c-112">Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="5932c-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="5932c-113">Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar.</span><span class="sxs-lookup"><span data-stu-id="5932c-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="5932c-114">Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.</span><span class="sxs-lookup"><span data-stu-id="5932c-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="5932c-115">Bei der [JSON-Serialisierung](system-text-json-overview.md) werden nur öffentliche Eigenschaften serialisiert, und die Typtreue wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5932c-115">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="5932c-116">JSON ist ein offener Standard, der für die gemeinsame Nutzung von Daten im Internet geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5932c-116">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="5932c-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="5932c-117">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="5932c-118">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="5932c-118">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="5932c-119">Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5932c-119">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="5932c-120">Enthält Klassen, die zum Serialisieren von Objekten in Dokumente oder Streams im JSON-Format verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5932c-120">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
