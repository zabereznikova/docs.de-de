---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 48d26bfa9074fd605e3545579f0bdc2744dfc7d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267858"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="213f7-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="213f7-102">MsmqBindingElementBase</span></span>

<span data-ttu-id="213f7-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="213f7-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="213f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="213f7-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="213f7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="213f7-105">Methods</span></span>  

 <span data-ttu-id="213f7-106">Die Klasse MsmqBindingElementBase definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="213f7-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="213f7-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="213f7-107">Properties</span></span>  

 <span data-ttu-id="213f7-108">Die Klasse MsmqBindingElementBase verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="213f7-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="213f7-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="213f7-109">CustomDeadLetterQueue</span></span>  

 <span data-ttu-id="213f7-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="213f7-110">Data type: string</span></span>  
  
 <span data-ttu-id="213f7-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-112">Ein URI, der den Speicherort der Warteschlange für unzustellbare Nachrichten für jede Anwendung enthält, in der Nachrichten platziert werden, die abgelaufen sind oder für die die Übertragung oder Zustellung fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="213f7-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="213f7-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="213f7-113">DeadLetterQueue</span></span>  

 <span data-ttu-id="213f7-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="213f7-114">Data type: string</span></span>  
  
 <span data-ttu-id="213f7-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-116">Ein Enumerationswert, der den Typ der zu verwendenden Warteschlange für unzustellbare Meldungen angibt.</span><span class="sxs-lookup"><span data-stu-id="213f7-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="213f7-117">Durable</span><span class="sxs-lookup"><span data-stu-id="213f7-117">Durable</span></span>  

 <span data-ttu-id="213f7-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="213f7-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="213f7-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-120">Ein Wert, der angibt, ob die von dieser Bindung verarbeiteten Nachrichten permanent oder flüchtig sind.</span><span class="sxs-lookup"><span data-stu-id="213f7-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="213f7-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="213f7-121">ExactlyOnce</span></span>  

 <span data-ttu-id="213f7-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="213f7-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="213f7-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-124">Ein boolescher Wert, der angibt, ob die von dieser Bindung verarbeiteten Nachrichten genau einmal empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="213f7-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="213f7-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="213f7-125">MaxRetryCycles</span></span>  

 <span data-ttu-id="213f7-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="213f7-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="213f7-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-128">Die maximale Anzahl der Neuversuche für die Zustellung von Nachrichten an die empfangende Anwendung.</span><span class="sxs-lookup"><span data-stu-id="213f7-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="213f7-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="213f7-129">ReceiveErrorHandling</span></span>  

 <span data-ttu-id="213f7-130">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="213f7-130">Data type: string</span></span>  
  
 <span data-ttu-id="213f7-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-132">Die Einstellungen für die Warteschlange für potenziell schädliche Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="213f7-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="213f7-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="213f7-133">ReceiveRetryCount</span></span>  

 <span data-ttu-id="213f7-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="213f7-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="213f7-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-136">Die maximale Anzahl von unmittelbaren Wiederholungsversuchen auf einer Nachricht, die aus der Anwendungswarteschlange gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="213f7-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="213f7-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="213f7-137">RetryCycleDelay</span></span>  

 <span data-ttu-id="213f7-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="213f7-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="213f7-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-140">Ein Wert, der die Zeitverzögerung zwischen den Wiederholungszyklen beim Versuch, eine Nachricht zuzustellen, die nicht sofort zugestellt werden konnte, angibt.</span><span class="sxs-lookup"><span data-stu-id="213f7-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="213f7-141">timeToLive</span><span class="sxs-lookup"><span data-stu-id="213f7-141">TimeToLive</span></span>  

 <span data-ttu-id="213f7-142">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="213f7-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="213f7-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-144">Das Zeitintervall, das angibt, wie lange die von dieser Bindung verarbeiteten Nachrichten in der Warteschlange bleiben können, bevor sie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="213f7-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="213f7-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="213f7-145">UseMsmqTracing</span></span>  

 <span data-ttu-id="213f7-146">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="213f7-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="213f7-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-148">Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichten nachverfolgt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="213f7-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="213f7-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="213f7-149">UseSourceJournal</span></span>  

 <span data-ttu-id="213f7-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="213f7-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="213f7-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="213f7-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213f7-152">Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichtenkopien in der Quelljournalwarteschlange gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="213f7-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="213f7-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="213f7-153">Requirements</span></span>  
  
|<span data-ttu-id="213f7-154">MOF</span><span class="sxs-lookup"><span data-stu-id="213f7-154">MOF</span></span>|<span data-ttu-id="213f7-155">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="213f7-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="213f7-156">Namespace</span><span class="sxs-lookup"><span data-stu-id="213f7-156">Namespace</span></span>|<span data-ttu-id="213f7-157">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="213f7-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="213f7-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="213f7-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
