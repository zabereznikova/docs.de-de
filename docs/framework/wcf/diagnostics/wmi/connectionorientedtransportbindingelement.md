---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 04e6abc5941ec99769ff2c15d47881b60e81d2e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181570"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="b5674-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b5674-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="b5674-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b5674-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5674-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5674-104">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b5674-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b5674-105">Methods</span></span>  
 <span data-ttu-id="b5674-106">Die ConnectionOrientedTransportBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="b5674-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b5674-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b5674-107">Properties</span></span>  
 <span data-ttu-id="b5674-108">Die ConnectionOrientedTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b5674-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="b5674-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="b5674-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="b5674-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="b5674-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="b5674-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-112">Der Zeitraum, der angibt, wie viel Zeit für die Durchführung der Kanalinitialisierung aufgewendet werden kann, bevor eine Zeitüberschreitung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="b5674-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="b5674-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="b5674-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="b5674-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b5674-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b5674-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-116">Die Puffergröße, die zum Übertragen eines Teils der serialisierten Meldung vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5674-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="b5674-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="b5674-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="b5674-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b5674-118">Data type: string</span></span>  
  
 <span data-ttu-id="b5674-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-120">Ein Wert, der angibt, ob der Hostname zum Erreichen des Dienstes bei übereinstimmendem URI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5674-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="b5674-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="b5674-121">MaxBufferSize</span></span>  
 <span data-ttu-id="b5674-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b5674-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="b5674-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-124">Die maximale Größe des zu verwendenden Puffers.</span><span class="sxs-lookup"><span data-stu-id="b5674-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="b5674-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="b5674-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="b5674-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="b5674-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="b5674-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-128">Das maximale Zeitintervall, das als Teil einer Nachricht oder vollständigen Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5674-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="b5674-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="b5674-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="b5674-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b5674-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="b5674-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-132">Die maximale Anzahl ausstehender asynchroner Annahmethreads, die für die Verarbeitung eingehender Verbindungen beim Dienst zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="b5674-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="b5674-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="b5674-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="b5674-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b5674-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="b5674-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-136">Die maximale Anzahl ausstehender Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="b5674-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="b5674-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="b5674-137">TransferMode</span></span>  
 <span data-ttu-id="b5674-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b5674-138">Data type: string</span></span>  
  
 <span data-ttu-id="b5674-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b5674-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b5674-140">Ein Wert, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="b5674-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5674-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5674-141">Requirements</span></span>  
  
|<span data-ttu-id="b5674-142">MOF</span><span class="sxs-lookup"><span data-stu-id="b5674-142">MOF</span></span>|<span data-ttu-id="b5674-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b5674-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b5674-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="b5674-144">Namespace</span></span>|<span data-ttu-id="b5674-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b5674-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5674-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5674-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
