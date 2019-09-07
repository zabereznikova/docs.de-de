---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399411"
---
# <a name="transactedbatching"></a><span data-ttu-id="c771e-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="c771e-101">\<transactedBatching></span></span>

<span data-ttu-id="c771e-102">Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c771e-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="c771e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c771e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c771e-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c771e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c771e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c771e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c771e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c771e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="c771e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c771e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="c771e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactedbatching->**</span><span class="sxs-lookup"><span data-stu-id="c771e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c771e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c771e-109">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c771e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c771e-110">Attributes and Elements</span></span>

<span data-ttu-id="c771e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c771e-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c771e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c771e-112">Attributes</span></span>

|<span data-ttu-id="c771e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c771e-113">Attribute</span></span>|<span data-ttu-id="c771e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c771e-114">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="c771e-115">Eine ganze Zahl, die die maximale Anzahl an Empfangsvorgängen angibt, die in einer Transaktion zusammengefasst werden können.</span><span class="sxs-lookup"><span data-stu-id="c771e-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="c771e-116">Die Standardeinstellung ist 0.</span><span class="sxs-lookup"><span data-stu-id="c771e-116">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c771e-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c771e-117">Child Elements</span></span>

<span data-ttu-id="c771e-118">Keine</span><span class="sxs-lookup"><span data-stu-id="c771e-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c771e-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c771e-119">Parent Elements</span></span>

|<span data-ttu-id="c771e-120">Element</span><span class="sxs-lookup"><span data-stu-id="c771e-120">Element</span></span>|<span data-ttu-id="c771e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c771e-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c771e-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c771e-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c771e-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="c771e-123">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c771e-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c771e-124">Remarks</span></span>

<span data-ttu-id="c771e-125">Ein Transport, der für Transaktionsbatchingversuche konfiguriert ist, um verschiedene Empfangsvorgänge in einer Transaktion zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="c771e-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="c771e-126">Dadurch wird der relativ große Aufwand für das Erstellen und Übergeben einer Transaktion bei jedem Empfangsvorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="c771e-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="c771e-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c771e-127">Example</span></span>

<span data-ttu-id="c771e-128">Im folgenden Beispiel wird gezeigt, wie einem Dienst das transaktive Batchverarbeitungsverhalten in einer Konfigurationsdatei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c771e-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a><span data-ttu-id="c771e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c771e-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
