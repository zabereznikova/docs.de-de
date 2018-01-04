---
title: 'Vorgehensweise: Segmentieren serialisierter Daten'
ms.date: 03/30/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- chunking serialized data
- data chunking
- binary serialization, chunking data
- large data set chunking
- serialization, chunking data
- serialization, examples
- binary serialization, examples
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 21d03e6f60e9df2af3b14442b14b576f0aee739e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-chunk-serialized-data"></a><span data-ttu-id="eceaf-102">Vorgehensweise: Segmentieren serialisierter Daten</span><span class="sxs-lookup"><span data-stu-id="eceaf-102">How to: chunk serialized data</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="eceaf-103">Beim Senden großer Datasätze in Webdienstnachrichten treten die zwei Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="eceaf-103">Two issues that occur when sending large data sets in Web service messages are:</span></span>  
  
1.  <span data-ttu-id="eceaf-104">Ein großes Workingset (Arbeitsspeicher) aufgrund der Pufferung durch das Serialisierungsmodul</span><span class="sxs-lookup"><span data-stu-id="eceaf-104">A large working set (memory) due to buffering by the serialization engine.</span></span>  
  
2.  <span data-ttu-id="eceaf-105">Unregelmäßige Bandbreitennutzung aufgrund von 33&#160;% Inflation nach der Base64-Codierung</span><span class="sxs-lookup"><span data-stu-id="eceaf-105">Inordinate bandwidth consumption due to 33 percent inflation after Base64 encoding.</span></span>  
  
 <span data-ttu-id="eceaf-106">Zur Lösung dieser Probleme implementieren Sie die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle, um die Serialisierung und Deserialisierung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="eceaf-106">To solve these problems, implement the <xref:System.Xml.Serialization.IXmlSerializable> interface to control the serialization and deserialization.</span></span> <span data-ttu-id="eceaf-107">Implementieren Sie insbesondere die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Methode und die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>-Methode, um die Daten zu segmentieren.</span><span class="sxs-lookup"><span data-stu-id="eceaf-107">Specifically, implement the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> and <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> methods to chunk the data.</span></span>  
  
### <a name="to-implement-server-side-chunking"></a><span data-ttu-id="eceaf-108">So implementieren Sie serverseitige Segmentierung:</span><span class="sxs-lookup"><span data-stu-id="eceaf-108">To implement server-side chunking</span></span>  
  
1.  <span data-ttu-id="eceaf-109">Die Webmethode muss die ASP.NET-Pufferung auf dem Servercomputer deaktivieren und einen Typ zurückgeben, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert.</span><span class="sxs-lookup"><span data-stu-id="eceaf-109">On the server machine, the Web method must turn off ASP.NET buffering and return a type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span>  
  
2.  <span data-ttu-id="eceaf-110">Der Typ, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert, segmentiert die Daten in der <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="eceaf-110">The type that implements <xref:System.Xml.Serialization.IXmlSerializable> chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
### <a name="to-implement-client-side-processing"></a><span data-ttu-id="eceaf-111">So implementieren Sie clientseitige Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="eceaf-111">To implement client-side processing</span></span>  
  
1.  <span data-ttu-id="eceaf-112">Ändern Sie die Webmethode auf dem Clientproxy so, dass der Typ zurückgegeben wird, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert.</span><span class="sxs-lookup"><span data-stu-id="eceaf-112">Alter the Web method on the client proxy to return the type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="eceaf-113">Sie können <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> verwenden, um diesen Vorgang automatisch auszuführen, aber dies wird hier nicht beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eceaf-113">You can use a <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> to do this automatically, but this isn't shown here.</span></span>  
  
2.  <span data-ttu-id="eceaf-114">Implementieren Sie die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>-Methode, um den segmentierten Datenstream zu lesen und die Bytes auf den Datenträger zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="eceaf-114">Implement the <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> method to read the chunked data stream and write the bytes to disk.</span></span> <span data-ttu-id="eceaf-115">Diese Implementierung löst auch Statusereignisse aus, die von einem grafischen Steuerelement, z.&#160;B. einer Statusleiste, verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="eceaf-115">This implementation also raises progress events that can be used by a graphic control, such as a progress bar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eceaf-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eceaf-116">Example</span></span>  
<span data-ttu-id="eceaf-117">Das folgende Codebeispiel veranschaulicht die Webmethode auf dem Client, mit der die ASP.NET-Pufferung deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="eceaf-117">The following code example shows the Web method on the client that turns off ASP.NET buffering.</span></span> <span data-ttu-id="eceaf-118">Es zeigt zudem die clientseitige Implementierung der <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle, die die Daten in der <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Methode segmentiert.</span><span class="sxs-lookup"><span data-stu-id="eceaf-118">It also shows the client-side implementation of the <xref:System.Xml.Serialization.IXmlSerializable> interface that chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eceaf-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="eceaf-119">Compiling the code</span></span>  
  
-   <span data-ttu-id="eceaf-120">In diesem Code werden die folgenden Namespaces verwendet: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization> und <xref:System.Xml.Schema>.</span><span class="sxs-lookup"><span data-stu-id="eceaf-120">The code uses the following namespaces: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, and <xref:System.Xml.Schema>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eceaf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eceaf-121">See also</span></span>  
 [<span data-ttu-id="eceaf-122">Benutzerdefinierte Serialisierung</span><span class="sxs-lookup"><span data-stu-id="eceaf-122">Custom Serialization</span></span>](custom-serialization.md)
