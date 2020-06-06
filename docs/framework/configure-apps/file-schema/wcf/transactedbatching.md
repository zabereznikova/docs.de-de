---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399411"
---
# \<transactedBatching>

<span data-ttu-id="11221-101">Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="11221-101">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="11221-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="11221-102">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="11221-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11221-103">Attributes and Elements</span></span>

<span data-ttu-id="11221-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11221-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="11221-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="11221-105">Attributes</span></span>

|<span data-ttu-id="11221-106">attribute</span><span class="sxs-lookup"><span data-stu-id="11221-106">Attribute</span></span>|<span data-ttu-id="11221-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11221-107">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="11221-108">Eine ganze Zahl, die die maximale Anzahl an Empfangsvorgängen angibt, die in einer Transaktion zusammengefasst werden können.</span><span class="sxs-lookup"><span data-stu-id="11221-108">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="11221-109">Die Standardeinstellung ist 0.</span><span class="sxs-lookup"><span data-stu-id="11221-109">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="11221-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11221-110">Child Elements</span></span>

<span data-ttu-id="11221-111">Keine</span><span class="sxs-lookup"><span data-stu-id="11221-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="11221-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11221-112">Parent Elements</span></span>

|<span data-ttu-id="11221-113">Element</span><span class="sxs-lookup"><span data-stu-id="11221-113">Element</span></span>|<span data-ttu-id="11221-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11221-114">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="11221-115">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="11221-115">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="11221-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="11221-116">Remarks</span></span>

<span data-ttu-id="11221-117">Ein Transport, der für Transaktionsbatchingversuche konfiguriert ist, um verschiedene Empfangsvorgänge in einer Transaktion zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="11221-117">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="11221-118">Dadurch wird der relativ große Aufwand für das Erstellen und Übergeben einer Transaktion bei jedem Empfangsvorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="11221-118">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="11221-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11221-119">Example</span></span>

<span data-ttu-id="11221-120">Im folgenden Beispiel wird gezeigt, wie einem Dienst das transaktive Batchverarbeitungsverhalten in einer Konfigurationsdatei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="11221-120">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="11221-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11221-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
