---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 0d0904c02e31def1b5264bec9f61eac0c9a8e964
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931229"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="c9b50-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c9b50-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="c9b50-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über eine benannte Pipe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9b50-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="c9b50-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9b50-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9b50-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c9b50-104">\<bindings></span></span>  
<span data-ttu-id="c9b50-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c9b50-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9b50-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9b50-106">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9b50-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c9b50-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c9b50-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9b50-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9b50-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c9b50-109">Attributes</span></span>  
  
|<span data-ttu-id="c9b50-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="c9b50-110">Attribute</span></span>|<span data-ttu-id="c9b50-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9b50-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c9b50-112">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c9b50-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c9b50-113">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c9b50-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c9b50-114">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c9b50-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="c9b50-115">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="c9b50-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c9b50-116">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9b50-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c9b50-117">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c9b50-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="c9b50-118">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="c9b50-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="c9b50-119">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c9b50-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c9b50-120">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9b50-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="c9b50-121">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c9b50-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c9b50-122">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c9b50-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c9b50-123">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c9b50-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c9b50-124">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c9b50-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c9b50-125">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c9b50-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c9b50-126">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="c9b50-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="c9b50-127">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c9b50-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c9b50-128">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c9b50-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c9b50-129">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c9b50-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9b50-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9b50-130">Child Elements</span></span>  
 <span data-ttu-id="c9b50-131">Keine</span><span class="sxs-lookup"><span data-stu-id="c9b50-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9b50-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9b50-132">Parent Elements</span></span>  
  
|<span data-ttu-id="c9b50-133">Element</span><span class="sxs-lookup"><span data-stu-id="c9b50-133">Element</span></span>|<span data-ttu-id="c9b50-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9b50-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9b50-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c9b50-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="c9b50-136">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="c9b50-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9b50-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9b50-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="c9b50-138">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c9b50-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="c9b50-139">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="c9b50-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="c9b50-140">Metadaten</span><span class="sxs-lookup"><span data-stu-id="c9b50-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="c9b50-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c9b50-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c9b50-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c9b50-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c9b50-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c9b50-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c9b50-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="c9b50-144">\<binding></span></span>](../../../misc/binding.md)
