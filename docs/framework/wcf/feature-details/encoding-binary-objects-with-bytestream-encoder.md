---
title: Codieren von binären Objekten mit dem ByteStream-Encoder
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: cc63cb8de1e245c3b58fb69819e59cb815b777d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276736"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="a9a5a-102">Codieren von binären Objekten mit dem ByteStream-Encoder</span><span class="sxs-lookup"><span data-stu-id="a9a5a-102">Encoding Binary Objects with ByteStream Encoder</span></span>

<span data-ttu-id="a9a5a-103">Das Senden und empfangen von unformatierten Binärdaten mit Windows Communication Foundation (WCF) wird mithilfe von konfiguriert <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="a9a5a-103">Sending and receiving raw binary data with Windows Communication Foundation (WCF) is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="a9a5a-104">Bytestream-Nachrichtenencoder-Architektur</span><span class="sxs-lookup"><span data-stu-id="a9a5a-104">Byte Stream Message Encoder Architecture</span></span>  

 <span data-ttu-id="a9a5a-105">Der von WCF verwendete binäre Nachrichten Encoder verfügt nicht über die Möglichkeit, die zugrunde liegenden Binärdaten in der Nachricht zu verarbeiten, zu validieren oder zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-105">The binary message encoder used by WCF has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="a9a5a-106">Das Datenpaket wird in XML codiert, gesendet, empfangen und decodiert.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="a9a5a-107">Der Encoder verarbeitet die Daten, nachdem diese an den Transport übergeben wurden und bevor die Nachricht an die Nachrichtenwarteschlange gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="a9a5a-108">Der Funktion nach schließt der binäre Encoder die Nachrichtendaten zum Senden in `<binary>`-Elemente ein und entfernt die Elemente, nachdem die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="a9a5a-109">Verwenden des Bytestream-Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="a9a5a-109">Using the Byte Stream Message Encoder</span></span>  

 <span data-ttu-id="a9a5a-110">Das folgende Beispiel zeigt einen Dienstvertrag, der den Bytestream-Nachrichtenencoder implementiert.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="a9a5a-111">Das folgende Beispiel zeigt, wie der Dienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="a9a5a-112">Falls Sie einen Dienst verwenden, der eine Nachrichteninfrastruktur implementiert (zum Beispiel ein Router), wird die Nachricht verarbeitet, ohne dass diese untersucht bzw. überprüft oder dass auf andere Art damit interagiert wird. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="a9a5a-113">Szenarien</span><span class="sxs-lookup"><span data-stu-id="a9a5a-113">Scenarios</span></span>  

 <span data-ttu-id="a9a5a-114">Der Bytestreamencoder ist in folgenden Szenarios nützlich.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
- <span data-ttu-id="a9a5a-115">Übertragen eines JPEG-Bilds zwischen Computern mithilfe von WCF.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-115">Transferring a JPEG image between computers using WCF.</span></span> <span data-ttu-id="a9a5a-116">In diesem Szenario wird das Bild über den Transport von einer externen Quelle empfangen. Bei den gesendeten Daten handelt es sich um die unformatierten Bytes, aus denen das Bild besteht.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="a9a5a-117">Ein Dienst empfängt die Binärdaten und zeigt das Bild an.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-117">A service will receive the binary data and display the image.</span></span>  
  
- <span data-ttu-id="a9a5a-118">Lesen von Informationen aus einer Meldungswarteschlange und Verarbeiten der Informationen.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="a9a5a-119">Die Meldung wird von einem Meldungswarteschlangen-Manager gelesen und zur Verarbeitung an den Meldungswarteschlangenkanal übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="a9a5a-120">Der Nachrichten Warteschlangen-Kanal fungiert als Warteschlangen-Manager im WCF-Kanal Stapel.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-120">The message queue channel will act as a queue manager in the WCF channel stack.</span></span>  
  
 <span data-ttu-id="a9a5a-121">Wenn eine Meldung über einen Meldungswarteschlangenkanal gesendet wird, hat der Absender keine Kontrolle über die vom Warteschlangen-Manger empfangenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="a9a5a-122">Wenn im Empfängerprozess keine unformatierten Bytes gelesen werden können, wird die Meldung als falsch formatierte Meldung empfangen und nicht verarbeitet. Es wird davon ausgegangen, dass der Empfängerprozess die empfangenen Bytes in ein akzeptables Format übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
