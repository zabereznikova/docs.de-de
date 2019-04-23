---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 9ac2b967e33571cbe0b4ad5ee81e13b009ffddd3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111357"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="fa279-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="fa279-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="fa279-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über eine benannte Pipe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa279-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="fa279-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa279-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa279-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fa279-104">\<bindings></span></span>  
<span data-ttu-id="fa279-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="fa279-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa279-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa279-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa279-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa279-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fa279-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa279-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa279-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa279-109">Attributes</span></span>  
  
|<span data-ttu-id="fa279-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="fa279-110">Attribute</span></span>|<span data-ttu-id="fa279-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa279-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="fa279-112">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fa279-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="fa279-113">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fa279-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fa279-114">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fa279-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="fa279-115">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="fa279-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="fa279-116">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa279-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="fa279-117">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fa279-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="fa279-118">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="fa279-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="fa279-119">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fa279-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="fa279-120">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="fa279-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="fa279-121">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fa279-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="fa279-122">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fa279-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fa279-123">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fa279-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="fa279-124">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fa279-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="fa279-125">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fa279-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fa279-126">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="fa279-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="fa279-127">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fa279-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="fa279-128">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fa279-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fa279-129">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fa279-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa279-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa279-130">Child Elements</span></span>  
 <span data-ttu-id="fa279-131">Keine</span><span class="sxs-lookup"><span data-stu-id="fa279-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa279-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa279-132">Parent Elements</span></span>  
  
|<span data-ttu-id="fa279-133">Element</span><span class="sxs-lookup"><span data-stu-id="fa279-133">Element</span></span>|<span data-ttu-id="fa279-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa279-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa279-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fa279-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="fa279-136">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="fa279-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa279-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa279-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="fa279-138">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fa279-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="fa279-139">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="fa279-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="fa279-140">Metadaten</span><span class="sxs-lookup"><span data-stu-id="fa279-140">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="fa279-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa279-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fa279-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa279-142">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fa279-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fa279-143">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fa279-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa279-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
