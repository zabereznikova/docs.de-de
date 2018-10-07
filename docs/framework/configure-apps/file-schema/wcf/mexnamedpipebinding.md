---
title: '&lt;mexNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 85b92fc193d66a97c75eae096117f32a36d413a9
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837572"
---
# <a name="ltmexnamedpipebindinggt"></a><span data-ttu-id="703d7-102">&lt;mexNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="703d7-102">&lt;mexNamedPipeBinding&gt;</span></span>
<span data-ttu-id="703d7-103">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über eine benannte Pipe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="703d7-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="703d7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="703d7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="703d7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="703d7-105">\<bindings></span></span>  
<span data-ttu-id="703d7-106">\<MexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="703d7-106">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="703d7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="703d7-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="703d7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="703d7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="703d7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="703d7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="703d7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="703d7-110">Attributes</span></span>  
  
|<span data-ttu-id="703d7-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="703d7-111">Attribute</span></span>|<span data-ttu-id="703d7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="703d7-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="703d7-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="703d7-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="703d7-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="703d7-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="703d7-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="703d7-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="703d7-116">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="703d7-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="703d7-117">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="703d7-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="703d7-118">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="703d7-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="703d7-119">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="703d7-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="703d7-120">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="703d7-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="703d7-121">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="703d7-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="703d7-122">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="703d7-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="703d7-123">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="703d7-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="703d7-124">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="703d7-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="703d7-125">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="703d7-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="703d7-126">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="703d7-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="703d7-127">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="703d7-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="703d7-128">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="703d7-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="703d7-129">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="703d7-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="703d7-130">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="703d7-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="703d7-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="703d7-131">Child Elements</span></span>  
 <span data-ttu-id="703d7-132">Keine</span><span class="sxs-lookup"><span data-stu-id="703d7-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="703d7-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="703d7-133">Parent Elements</span></span>  
  
|<span data-ttu-id="703d7-134">Element</span><span class="sxs-lookup"><span data-stu-id="703d7-134">Element</span></span>|<span data-ttu-id="703d7-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="703d7-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="703d7-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="703d7-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="703d7-137">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="703d7-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="703d7-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="703d7-138">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>  
 [<span data-ttu-id="703d7-139">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="703d7-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="703d7-140">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="703d7-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="703d7-141">Metadaten</span><span class="sxs-lookup"><span data-stu-id="703d7-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="703d7-142">Bindungen</span><span class="sxs-lookup"><span data-stu-id="703d7-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="703d7-143">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="703d7-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="703d7-144">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="703d7-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="703d7-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="703d7-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
