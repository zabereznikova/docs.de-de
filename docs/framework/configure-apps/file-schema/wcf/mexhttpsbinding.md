---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430339"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="224f0-101">\<mexhttpsbinding ></span><span class="sxs-lookup"><span data-stu-id="224f0-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="224f0-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="224f0-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="224f0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="224f0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="224f0-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="224f0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="224f0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="224f0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="224f0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexhttpsbinding >**</span><span class="sxs-lookup"><span data-stu-id="224f0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224f0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="224f0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="224f0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="224f0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="224f0-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="224f0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="224f0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="224f0-110">Attributes</span></span>  
  
|<span data-ttu-id="224f0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="224f0-111">Attribute</span></span>|<span data-ttu-id="224f0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="224f0-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="224f0-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="224f0-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="224f0-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="224f0-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="224f0-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="224f0-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="224f0-116">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="224f0-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="224f0-117">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="224f0-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="224f0-118">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="224f0-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="224f0-119">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="224f0-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="224f0-120">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="224f0-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="224f0-121">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="224f0-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="224f0-122">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="224f0-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="224f0-123">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="224f0-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="224f0-124">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="224f0-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="224f0-125">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="224f0-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="224f0-126">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="224f0-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="224f0-127">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="224f0-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="224f0-128">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="224f0-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="224f0-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="224f0-129">Child Elements</span></span>  
 <span data-ttu-id="224f0-130">None.</span><span class="sxs-lookup"><span data-stu-id="224f0-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="224f0-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="224f0-131">Parent Elements</span></span>  
  
|<span data-ttu-id="224f0-132">Element</span><span class="sxs-lookup"><span data-stu-id="224f0-132">Element</span></span>|<span data-ttu-id="224f0-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="224f0-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="224f0-134">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="224f0-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="224f0-135">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="224f0-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="224f0-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="224f0-136">Remarks</span></span>  
 <span data-ttu-id="224f0-137">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung, die mit Zertifikaten Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="224f0-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="224f0-138">Weitere Informationen zum Konfigurieren und Verwenden eines solchen Metadatenendpunkts finden Sie unter Gewusst [wie: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange Bindung](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), Gewusst [wie: Abrufen von Metadaten über eine nicht-MEX-Bindung](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)und das Beispiel für einen [benutzerdefinierten sicheren Metadatenendpunkt](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="224f0-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="224f0-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="224f0-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="224f0-140">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="224f0-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="224f0-141">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="224f0-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="224f0-142">Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung</span><span class="sxs-lookup"><span data-stu-id="224f0-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="224f0-143">Vorgehensweise: Abrufen von Metadaten über eine Nicht-MEX-Bindung</span><span class="sxs-lookup"><span data-stu-id="224f0-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="224f0-144">Benutzerdefinierter sicherer Metadatenendpunkt</span><span class="sxs-lookup"><span data-stu-id="224f0-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="224f0-145">Metadaten</span><span class="sxs-lookup"><span data-stu-id="224f0-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="224f0-146">Bindungen</span><span class="sxs-lookup"><span data-stu-id="224f0-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="224f0-147">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="224f0-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="224f0-148">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="224f0-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="224f0-149">\<Bindungs ></span><span class="sxs-lookup"><span data-stu-id="224f0-149">\<binding></span></span>](bindings.md)
