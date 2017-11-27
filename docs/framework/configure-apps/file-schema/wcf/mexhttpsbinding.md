---
title: '&lt;mexHttpsBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e259eec6fcbf34bf4e6f175f47a62d91f951206
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexhttpsbindinggt"></a><span data-ttu-id="ba839-102">&lt;mexHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ba839-102">&lt;mexHttpsBinding&gt;</span></span>
<span data-ttu-id="ba839-103">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba839-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="ba839-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ba839-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba839-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="ba839-105">\<bindings></span></span>  
<span data-ttu-id="ba839-106">\<MexHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="ba839-106">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba839-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba839-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba839-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba839-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ba839-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba839-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba839-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba839-110">Attributes</span></span>  
  
|<span data-ttu-id="ba839-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba839-111">Attribute</span></span>|<span data-ttu-id="ba839-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba839-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ba839-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ba839-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ba839-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ba839-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba839-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba839-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="ba839-116">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="ba839-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ba839-117">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba839-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ba839-118">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ba839-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="ba839-119">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="ba839-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="ba839-120">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ba839-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ba839-121">Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba839-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ba839-122">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ba839-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ba839-123">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ba839-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba839-124">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba839-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ba839-125">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ba839-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ba839-126">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ba839-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba839-127">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ba839-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ba839-128">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ba839-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ba839-129">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ba839-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba839-130">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba839-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba839-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba839-131">Child Elements</span></span>  
 <span data-ttu-id="ba839-132">Keine</span><span class="sxs-lookup"><span data-stu-id="ba839-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba839-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba839-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ba839-134">Element</span><span class="sxs-lookup"><span data-stu-id="ba839-134">Element</span></span>|<span data-ttu-id="ba839-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba839-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba839-136">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="ba839-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="ba839-137">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="ba839-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba839-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba839-138">Remarks</span></span>  
 <span data-ttu-id="ba839-139">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung, die mit Zertifikaten Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba839-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="ba839-140">Weitere Informationen zum Konfigurieren und Verwenden eines metadatenendpunkts finden Sie unter [Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindungen](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [Vorgehensweise: Metadaten Abrufen über eine nicht - MEX-Bindung](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), und die Beispiel [benutzerdefinierter sicherer Metadatenendpunkt](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="ba839-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba839-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba839-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [<span data-ttu-id="ba839-142">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ba839-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="ba839-143">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="ba839-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="ba839-144">Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung</span><span class="sxs-lookup"><span data-stu-id="ba839-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [<span data-ttu-id="ba839-145">Vorgehensweise: Abrufen von Metadaten über eine nicht - MEX-Bindung</span><span class="sxs-lookup"><span data-stu-id="ba839-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [<span data-ttu-id="ba839-146">Benutzerdefinierter sicherer Metadatenendpunkt</span><span class="sxs-lookup"><span data-stu-id="ba839-146">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [<span data-ttu-id="ba839-147">Metadaten</span><span class="sxs-lookup"><span data-stu-id="ba839-147">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="ba839-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ba839-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ba839-149">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ba839-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ba839-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ba839-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="ba839-151">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="ba839-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
