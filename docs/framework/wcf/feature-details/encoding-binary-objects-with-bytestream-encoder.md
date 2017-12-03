---
title: "Codieren von binären Objekten mit dem ByteStream-Encoder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1516731181a7e60445ce19752c3bb1835cb5897
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="99e8d-102">Codieren von binären Objekten mit dem ByteStream-Encoder</span><span class="sxs-lookup"><span data-stu-id="99e8d-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="99e8d-103">Das Senden und Empfangen von unformatierten Binärdaten mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] wird mithilfe von <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="99e8d-103">Sending and receiving raw binary data with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="99e8d-104">Bytestream-Nachrichtenencoder-Architektur</span><span class="sxs-lookup"><span data-stu-id="99e8d-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="99e8d-105">Der von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendete binäre Nachrichtenencoder weist keine Funktionen zum Verarbeiten, Überprüfen oder Identifizieren der zugrunde liegenden Daten in der Nachricht auf.</span><span class="sxs-lookup"><span data-stu-id="99e8d-105">The binary message encoder used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="99e8d-106">Das Datenpaket wird in XML codiert, gesendet, empfangen und decodiert.</span><span class="sxs-lookup"><span data-stu-id="99e8d-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="99e8d-107">Der Encoder verarbeitet die Daten, nachdem diese an den Transport übergeben wurden und bevor die Nachricht an die Nachrichtenwarteschlange gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="99e8d-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="99e8d-108">Der Funktion nach schließt der binäre Encoder die Nachrichtendaten zum Senden in `<binary>`-Elemente ein und entfernt die Elemente, nachdem die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="99e8d-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="99e8d-109">Verwenden des Bytestream-Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="99e8d-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="99e8d-110">Das folgende Beispiel zeigt einen Dienstvertrag, der den Bytestream-Nachrichtenencoder implementiert.</span><span class="sxs-lookup"><span data-stu-id="99e8d-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="99e8d-111">Das folgende Beispiel zeigt, wie der Dienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="99e8d-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="99e8d-112">Falls Sie einen Dienst verwenden, der eine Nachrichteninfrastruktur implementiert (zum Beispiel ein Router), wird die Nachricht verarbeitet, ohne dass diese untersucht bzw. überprüft oder dass auf andere Art damit interagiert wird. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="99e8d-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="99e8d-113">Szenarien</span><span class="sxs-lookup"><span data-stu-id="99e8d-113">Scenarios</span></span>  
 <span data-ttu-id="99e8d-114">Der Bytestreamencoder ist in folgenden Szenarios nützlich.</span><span class="sxs-lookup"><span data-stu-id="99e8d-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
-   <span data-ttu-id="99e8d-115">Übertragen eines JPEG-Bilds zwischen Computern mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99e8d-115">Transferring a JPEG image between computers using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="99e8d-116">In diesem Szenario wird das Bild über den Transport von einer externen Quelle empfangen. Bei den gesendeten Daten handelt es sich um die unformatierten Bytes, aus denen das Bild besteht.</span><span class="sxs-lookup"><span data-stu-id="99e8d-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="99e8d-117">Ein Dienst empfängt die Binärdaten und zeigt das Bild an.</span><span class="sxs-lookup"><span data-stu-id="99e8d-117">A service will receive the binary data and display the image.</span></span>  
  
-   <span data-ttu-id="99e8d-118">Lesen von Informationen aus einer Meldungswarteschlange und Verarbeiten der Informationen.</span><span class="sxs-lookup"><span data-stu-id="99e8d-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="99e8d-119">Die Meldung wird von einem Meldungswarteschlangen-Manager gelesen und zur Verarbeitung an den Meldungswarteschlangenkanal übergeben.</span><span class="sxs-lookup"><span data-stu-id="99e8d-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="99e8d-120">Der Meldungswarteschlangenkanal fungiert im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Kanalstapel als Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="99e8d-120">The message queue channel will act as a queue manager in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack.</span></span>  
  
 <span data-ttu-id="99e8d-121">Wenn eine Meldung über einen Meldungswarteschlangenkanal gesendet wird, hat der Absender keine Kontrolle über die vom Warteschlangen-Manger empfangenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="99e8d-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="99e8d-122">Wenn im Empfängerprozess keine unformatierten Bytes gelesen werden können, wird die Meldung als falsch formatierte Meldung empfangen und nicht verarbeitet. Es wird davon ausgegangen, dass der Empfängerprozess die empfangenen Bytes in ein akzeptables Format übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="99e8d-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
