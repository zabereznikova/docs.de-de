---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399542"
---
# \<soapProcessing>

<span data-ttu-id="fa689-101">Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="fa689-101">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**
  
## <a name="syntax"></a><span data-ttu-id="fa689-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa689-102">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa689-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa689-103">Attributes and elements</span></span>  
  
<span data-ttu-id="fa689-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa689-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa689-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa689-105">Attributes</span></span>  
  
|                   | <span data-ttu-id="fa689-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa689-106">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="fa689-107">Ein boolescher Wert, der angibt, ob Nachrichten zwischen SOAP-Nachrichtenversionen gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa689-107">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="fa689-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa689-108">Child elements</span></span>

<span data-ttu-id="fa689-109">Keine</span><span class="sxs-lookup"><span data-stu-id="fa689-109">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fa689-110">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa689-110">Parent elements</span></span>

|     | <span data-ttu-id="fa689-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa689-111">Description</span></span> |
| --- | ----------- |
| [**\<behavior>**](behavior-of-endpointbehaviors.md) | <span data-ttu-id="fa689-112">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="fa689-112">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="fa689-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fa689-113">Remarks</span></span>

<span data-ttu-id="fa689-114">SOAP-Verarbeitung ist der Prozess, bei dem Nachrichten zwischen Nachrichtenversionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="fa689-114">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="fa689-115">Der Windows Communication Foundation (WCF)-Routing Dienst kann Nachrichten von einem Protokoll in ein anderes Protokoll konvertieren.</span><span class="sxs-lookup"><span data-stu-id="fa689-115">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="fa689-116">Wenn die Versionen eingehender und ausgehender Nachrichten unterschiedlich sind, wird eine neue Nachricht mit der richtigen Version erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa689-116">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="fa689-117">Meldungen werden von einer <xref:System.ServiceModel.Channels.MessageVersion> zu einer anderen verarbeitet, indem eine neue WCF-Meldung erstellt wird, die den Textteil und relevante Header von der eingehenden WCF-Meldung enthält.</span><span class="sxs-lookup"><span data-stu-id="fa689-117">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="fa689-118">Header, die adressierungsspezifisch sind oder auf Routerebene verstanden werden, werden während der Erstellung der neuen WCF-Nachricht nicht verwendet, da diese Header entweder eine andere Version haben (im Fall von Adressierungsheadern) oder als Teil der Kommunikation zwischen dem Client und dem Router verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="fa689-118">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="fa689-119">Ob ein Header in der ausgehenden Nachricht eingefügt wird, wird dadurch bestimmt, ob er als verstanden markiert wurde, als er die eingehende Channelebene durchlief.</span><span class="sxs-lookup"><span data-stu-id="fa689-119">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="fa689-120">Nicht akzeptierte Header (z. B. benutzerdefinierte Header) werden nicht entfernt und durchlaufen den Routingdienst, indem sie in die ausgehende Nachricht kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="fa689-120">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="fa689-121">Der Nachrichtentext wird in die ausgehende Nachricht kopiert.</span><span class="sxs-lookup"><span data-stu-id="fa689-121">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="fa689-122">Die Nachricht wird dann über den Kanal für ausgehende Nachrichten gesendet. Zu diesem Zeitpunkt werden alle relevanten Header und anderen für das Kommunikationsprotokoll/den Transport relevanten Umschlagdaten erstellt und hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fa689-122">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="fa689-123">Diese Verarbeitungsschritte erfolgen, wenn das SOAP-Verarbeitungsverhalten angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="fa689-123">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="fa689-124">Dieses [\<soapProcessingExtension>](soapprocessing.md) Verhalten ist ein Endpunkt Verhalten, das auf alle Client Endpunkte (ausgehend) angewendet wird, wenn der Routing Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="fa689-124">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="fa689-125">Standardmäßig wird das [\<routing>](routing-of-servicebehavior.md) Verhalten erstellt und ein neues Verhalten angefügt, [\<soapProcessingExtension>](soapprocessing.md) wobei `processMessages` `true` für jeden Client Endpunkt auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fa689-125">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="fa689-126">Wenn Sie ein Protokoll haben, das vom Routingdienst nicht akzeptiert wird, oder das Standardverarbeitungsverhalten überschreiben möchten, können Sie die SOAP-Verarbeitung entweder für den gesamten Routingdienst oder für bestimmte Endpunkte deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa689-126">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="fa689-127">Um die SOAP-Verarbeitung für den gesamten Routing Dienst auf allen Endpunkten zu deaktivieren, legen Sie das- `soapProcessing` Attribut des-Verhaltens auf fest [\<routing>](routing-of-servicebehavior.md) `false` .</span><span class="sxs-lookup"><span data-stu-id="fa689-127">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="fa689-128">Um die SOAP-Verarbeitung für einen bestimmten Endpunkt zu deaktivieren, verwenden Sie dieses Verhalten und legen Sie das `processMessages`-Attribut dieses Verhaltens auf `false` fest. Fügen Sie das Verhalten dann an den Endpunkt an, für den Sie den Standardverarbeitungscode deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fa689-128">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="fa689-129">Wenn das [\<routing>](routing-of-servicebehavior.md) Verhalten den Routing Dienst festlegt, wird das erneute Anwenden des Endpunkt Verhaltens übersprungen, da bereits eine vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fa689-129">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
