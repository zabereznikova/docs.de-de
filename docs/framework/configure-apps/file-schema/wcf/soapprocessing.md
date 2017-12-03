---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e83bfc0f868526ad5366032f08956a6c14a1056
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltsoapprocessinggt"></a><span data-ttu-id="618c8-102">&lt;soapProcessing&gt;</span><span class="sxs-lookup"><span data-stu-id="618c8-102">&lt;soapProcessing&gt;</span></span>

<span data-ttu-id="618c8-103">Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="618c8-103">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="618c8-104">**\<System. ServiceModel >** </span><span class="sxs-lookup"><span data-stu-id="618c8-104">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="618c8-105">&nbsp;&nbsp;**\<Verhalten >** </span><span class="sxs-lookup"><span data-stu-id="618c8-105">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="618c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<EndpointBehaviors >** </span><span class="sxs-lookup"><span data-stu-id="618c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="618c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Verhalten >** </span><span class="sxs-lookup"><span data-stu-id="618c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="618c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<SoapProcessing >**</span><span class="sxs-lookup"><span data-stu-id="618c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="618c8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="618c8-109">Syntax</span></span>

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="618c8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="618c8-110">Attributes and elements</span></span>

<span data-ttu-id="618c8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="618c8-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="618c8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="618c8-112">Attributes</span></span>

|                   | <span data-ttu-id="618c8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="618c8-113">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="618c8-114">Ein boolescher Wert, der angibt, ob Nachrichten zwischen SOAP-Nachrichtenversionen gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="618c8-114">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="618c8-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="618c8-115">Child elements</span></span>

<span data-ttu-id="618c8-116">Keine</span><span class="sxs-lookup"><span data-stu-id="618c8-116">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="618c8-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="618c8-117">Parent elements</span></span>

|     | <span data-ttu-id="618c8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="618c8-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="618c8-119">**\<Verhalten >**</span><span class="sxs-lookup"><span data-stu-id="618c8-119">**\<behavior>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | <span data-ttu-id="618c8-120">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="618c8-120">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="618c8-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="618c8-121">Remarks</span></span>

<span data-ttu-id="618c8-122">SOAP-Verarbeitung ist der Prozess, bei dem Nachrichten zwischen Nachrichtenversionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="618c8-122">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="618c8-123">Der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Routingdienst kann Nachrichten von einem Protokoll in ein anderes konvertieren.</span><span class="sxs-lookup"><span data-stu-id="618c8-123">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="618c8-124">Wenn die Versionen eingehender und ausgehender Nachrichten unterschiedlich sind, wird eine neue Nachricht mit der richtigen Version erstellt.</span><span class="sxs-lookup"><span data-stu-id="618c8-124">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="618c8-125">Verarbeiten von Nachrichten von einem <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` in eine andere erreicht, indem Sie eine neue [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Nachricht, die den Textteil und relevante Header der eingehenden enthält [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Nachricht.</span><span class="sxs-lookup"><span data-stu-id="618c8-125">Processing messages from one <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion`  to another is accomplished by constructing a new [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message that contains the body part and relevant headers from the incoming [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message.</span></span> <span data-ttu-id="618c8-126">Header, die adressierungsspezifisch sind oder auf Routerebene verstanden werden, werden während der Erstellung der neuen WCF-Nachricht nicht verwendet, da diese Header entweder eine andere Version haben (im Fall von Adressierungsheadern) oder als Teil der Kommunikation zwischen dem Client und dem Router verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="618c8-126">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="618c8-127">Ob ein Header in der ausgehenden Nachricht eingefügt wird, wird dadurch bestimmt, ob er als verstanden markiert wurde, als er die eingehende Channelebene durchlief.</span><span class="sxs-lookup"><span data-stu-id="618c8-127">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="618c8-128">Nicht akzeptierte Header (z. B. benutzerdefinierte Header) werden nicht entfernt und durchlaufen den Routingdienst, indem sie in die ausgehende Nachricht kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="618c8-128">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="618c8-129">Der Nachrichtentext wird in die ausgehende Nachricht kopiert.</span><span class="sxs-lookup"><span data-stu-id="618c8-129">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="618c8-130">Die Nachricht wird dann über den Kanal für ausgehende Nachrichten gesendet. Zu diesem Zeitpunkt werden alle relevanten Header und anderen für das Kommunikationsprotokoll/den Transport relevanten Umschlagdaten erstellt und hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="618c8-130">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="618c8-131">Diese Verarbeitungsschritte erfolgen, wenn das SOAP-Verarbeitungsverhalten angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="618c8-131">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="618c8-132">Dies [ \<SoapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) Verhalten ist ein Endpunktverhalten, die auf allen (ausgehend) Clientendpunkten angewendet wird, wenn der Routingdienst startet.</span><span class="sxs-lookup"><span data-stu-id="618c8-132">This [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="618c8-133">in der Standardeinstellung die [ \<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) Verhalten erstellt und fügt ein neues [ \<SoapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) Verhalten bei `processMessages` festgelegt `true` für jede Clientendpunkt.</span><span class="sxs-lookup"><span data-stu-id="618c8-133">default, the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="618c8-134">Wenn Sie ein Protokoll haben, das vom Routingdienst nicht akzeptiert wird, oder das Standardverarbeitungsverhalten überschreiben möchten, können Sie die SOAP-Verarbeitung entweder für den gesamten Routingdienst oder für bestimmte Endpunkte deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="618c8-134">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="618c8-135">Wenn um SOAP-Verarbeitung für den gesamten Routingdienst auf alle Endpunkte zu deaktivieren, legen Sie die `soapProcessing` Attribut des der [ \<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) Verhalten `false`.</span><span class="sxs-lookup"><span data-stu-id="618c8-135">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="618c8-136">Um die SOAP-Verarbeitung für einen bestimmten Endpunkt zu deaktivieren, verwenden Sie dieses Verhalten und legen Sie das `processMessages`-Attribut dieses Verhaltens auf `false` fest. Fügen Sie das Verhalten dann an den Endpunkt an, für den Sie den Standardverarbeitungscode deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="618c8-136">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="618c8-137">Wenn die [ \<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) Verhalten richtet den Routingdienst, überspringt das Endpunktverhalten neu, da bereits eine vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="618c8-137">When the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
