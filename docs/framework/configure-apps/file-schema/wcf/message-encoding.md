---
title: Nachrichtenverschlüsselung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3040a16b6d167c4f066b2ddbd0a542741f88d62
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="message-encoding"></a><span data-ttu-id="df008-102">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="df008-102">Message Encoding</span></span>
<span data-ttu-id="df008-103">Beim Kodieren werden Unicode-Zeichen in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="df008-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="df008-104">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="df008-104">Decoding is the reverse process.</span></span> <span data-ttu-id="df008-105">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="df008-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="df008-106">Der `binaryMessageEncoding`-Konfigurationsabschnitt gibt die Zeichenkodierung und die für binäre XML-Nachrichten verwendete Nachrichtenversionierung an.</span><span class="sxs-lookup"><span data-stu-id="df008-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="df008-107">Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat.</span><span class="sxs-lookup"><span data-stu-id="df008-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="df008-108">Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-\*-Standards basierende Interoperabilität geht aber verloren.</span><span class="sxs-lookup"><span data-stu-id="df008-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
 <span data-ttu-id="df008-109">Der `mtomMessageEncoding`-Konfigurationsabschnitt gibt die Zeichenkodierung und die für eine Nachricht mit der MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversionierung an.</span><span class="sxs-lookup"><span data-stu-id="df008-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="df008-110">MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in Windows Communication Foundation (WCF)-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="df008-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="df008-111">Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="df008-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="df008-112">Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Textkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="df008-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="df008-113">Der `textMessageEncoding`-Konfigurationsabschnitt gibt einen Textencoder an, der bei der Übertragung textbasierte Nachrichten erstellt.</span><span class="sxs-lookup"><span data-stu-id="df008-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="df008-114">Von diesem Encoder erzeugte Nachrichten sind für die WS-\*-basierte Interoperabilität geeignet.</span><span class="sxs-lookup"><span data-stu-id="df008-114">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="df008-115">Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen.</span><span class="sxs-lookup"><span data-stu-id="df008-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="df008-116">Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="df008-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df008-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df008-117">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [<span data-ttu-id="df008-118">Bindungen</span><span class="sxs-lookup"><span data-stu-id="df008-118">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="df008-119">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="df008-119">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="df008-120">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="df008-120">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="df008-121">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="df008-121">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="df008-122">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="df008-122">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
