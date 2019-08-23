---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 491597da508487c3988b284c84411123d434fe72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932536"
---
# <a name="mextcpbinding"></a><span data-ttu-id="a0e9e-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="a0e9e-101">\<mexTcpBinding></span></span>
<span data-ttu-id="a0e9e-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über TCP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="a0e9e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a0e9e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0e9e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a0e9e-104">\<bindings></span></span>  
<span data-ttu-id="a0e9e-105">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="a0e9e-105">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e9e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0e9e-106">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0e9e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0e9e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a0e9e-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0e9e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0e9e-109">Attributes</span></span>  
  
|<span data-ttu-id="a0e9e-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0e9e-110">Attribute</span></span>|<span data-ttu-id="a0e9e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a0e9e-112">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a0e9e-113">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0e9e-114">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a0e9e-115">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a0e9e-116">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a0e9e-117">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="a0e9e-118">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="a0e9e-119">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a0e9e-120">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0e9e-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a0e9e-121">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a0e9e-122">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0e9e-123">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a0e9e-124">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a0e9e-125">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0e9e-126">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a0e9e-127">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a0e9e-128">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0e9e-129">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0e9e-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0e9e-130">Child Elements</span></span>  
 <span data-ttu-id="a0e9e-131">Keine</span><span class="sxs-lookup"><span data-stu-id="a0e9e-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0e9e-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0e9e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a0e9e-133">Element</span><span class="sxs-lookup"><span data-stu-id="a0e9e-133">Element</span></span>|<span data-ttu-id="a0e9e-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0e9e-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a0e9e-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="a0e9e-136">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0e9e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0e9e-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="a0e9e-138">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a0e9e-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="a0e9e-139">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="a0e9e-140">Metadaten</span><span class="sxs-lookup"><span data-stu-id="a0e9e-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="a0e9e-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a0e9e-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a0e9e-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a0e9e-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a0e9e-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a0e9e-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a0e9e-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="a0e9e-144">\<binding></span></span>](../../../misc/binding.md)
