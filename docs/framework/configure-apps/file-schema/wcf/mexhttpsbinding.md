---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 30d1aa27ce29b6aa4091c3e7be05746ad462102a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931271"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="66d44-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="66d44-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="66d44-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66d44-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="66d44-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="66d44-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="66d44-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="66d44-104">\<bindings></span></span>  
<span data-ttu-id="66d44-105">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="66d44-105">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d44-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="66d44-106">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66d44-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="66d44-107">Attributes and Elements</span></span>  
 <span data-ttu-id="66d44-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="66d44-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66d44-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="66d44-109">Attributes</span></span>  
  
|<span data-ttu-id="66d44-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="66d44-110">Attribute</span></span>|<span data-ttu-id="66d44-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66d44-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="66d44-112">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="66d44-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="66d44-113">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="66d44-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d44-114">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="66d44-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="66d44-115">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="66d44-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="66d44-116">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66d44-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="66d44-117">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66d44-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="66d44-118">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="66d44-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="66d44-119">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="66d44-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="66d44-120">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="66d44-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="66d44-121">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="66d44-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="66d44-122">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="66d44-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d44-123">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="66d44-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="66d44-124">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="66d44-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="66d44-125">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="66d44-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d44-126">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="66d44-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="66d44-127">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="66d44-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="66d44-128">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="66d44-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d44-129">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="66d44-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66d44-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66d44-130">Child Elements</span></span>  
 <span data-ttu-id="66d44-131">Keine</span><span class="sxs-lookup"><span data-stu-id="66d44-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66d44-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66d44-132">Parent Elements</span></span>  
  
|<span data-ttu-id="66d44-133">Element</span><span class="sxs-lookup"><span data-stu-id="66d44-133">Element</span></span>|<span data-ttu-id="66d44-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66d44-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66d44-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="66d44-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="66d44-136">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="66d44-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66d44-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66d44-137">Remarks</span></span>  
 <span data-ttu-id="66d44-138">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung, die mit Zertifikaten Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66d44-138">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="66d44-139">Weitere Informationen zum Konfigurieren und Verwenden eines solchen Metadatenendpunkts finden [Sie unter Gewusst wie: Konfigurieren einer benutzerdefinierten WS-Metadatenaustausch [-Bindung](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), Vorgehensweise: Rufen Sie Metadaten über eine nicht-MEX](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)-Bindung und den [benutzerdefinierten Beispiel Endpunkt für sichere Metadaten](../../../wcf/samples/custom-secure-metadata-endpoint.md)ab.</span><span class="sxs-lookup"><span data-stu-id="66d44-139">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d44-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66d44-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="66d44-141">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="66d44-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="66d44-142">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="66d44-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="66d44-143">Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange Bindung</span><span class="sxs-lookup"><span data-stu-id="66d44-143">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="66d44-144">Vorgehensweise: Abrufen von Metadaten über eine nicht-MEX-Bindung</span><span class="sxs-lookup"><span data-stu-id="66d44-144">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="66d44-145">Benutzerdefinierter sicherer Metadatenendpunkt</span><span class="sxs-lookup"><span data-stu-id="66d44-145">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="66d44-146">Metadaten</span><span class="sxs-lookup"><span data-stu-id="66d44-146">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="66d44-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="66d44-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66d44-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="66d44-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="66d44-149">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="66d44-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="66d44-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="66d44-150">\<binding></span></span>](../../../misc/binding.md)
