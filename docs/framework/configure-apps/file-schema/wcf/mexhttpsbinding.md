---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 8025f5ed42325963aa4b695890caa5031f6bb6a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204722"
---
# \<mexHttpsBinding>

<span data-ttu-id="efbe6-101">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efbe6-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="efbe6-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="efbe6-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efbe6-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="efbe6-103">Attributes and Elements</span></span>  

 <span data-ttu-id="efbe6-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="efbe6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efbe6-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="efbe6-105">Attributes</span></span>  
  
|<span data-ttu-id="efbe6-106">attribute</span><span class="sxs-lookup"><span data-stu-id="efbe6-106">Attribute</span></span>|<span data-ttu-id="efbe6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efbe6-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="efbe6-108">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="efbe6-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="efbe6-109">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="efbe6-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="efbe6-110">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="efbe6-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="efbe6-111">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="efbe6-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="efbe6-112">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efbe6-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="efbe6-113">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="efbe6-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="efbe6-114">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="efbe6-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="efbe6-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="efbe6-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="efbe6-116">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="efbe6-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="efbe6-117">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="efbe6-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="efbe6-118">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="efbe6-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="efbe6-119">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="efbe6-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="efbe6-120">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="efbe6-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="efbe6-121">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="efbe6-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="efbe6-122">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="efbe6-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="efbe6-123">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="efbe6-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efbe6-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="efbe6-124">Child Elements</span></span>  

 <span data-ttu-id="efbe6-125">Keine</span><span class="sxs-lookup"><span data-stu-id="efbe6-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efbe6-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="efbe6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="efbe6-127">Element</span><span class="sxs-lookup"><span data-stu-id="efbe6-127">Element</span></span>|<span data-ttu-id="efbe6-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efbe6-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="efbe6-129">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="efbe6-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efbe6-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="efbe6-130">Remarks</span></span>  

 <span data-ttu-id="efbe6-131">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung, die mit Zertifikaten Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="efbe6-131">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="efbe6-132">Weitere Informationen zum Konfigurieren und Verwenden eines solchen Metadatenendpunkts finden Sie unter Gewusst [wie: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange Bindung](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), Gewusst [wie: Abrufen von Metadaten über eine nicht-MEX-Bindung](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)und das Beispiel für einen [benutzerdefinierten sicheren Metadatenendpunkt](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="efbe6-132">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efbe6-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efbe6-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="efbe6-134">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="efbe6-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="efbe6-135">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="efbe6-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="efbe6-136">Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung</span><span class="sxs-lookup"><span data-stu-id="efbe6-136">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="efbe6-137">Vorgehensweise: Aufrufen von Metadaten über eine Nicht-MEX-Bindung</span><span class="sxs-lookup"><span data-stu-id="efbe6-137">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="efbe6-138">Benutzerdefinierter sicherer Metadatenendpunkt</span><span class="sxs-lookup"><span data-stu-id="efbe6-138">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="efbe6-139">Metadaten</span><span class="sxs-lookup"><span data-stu-id="efbe6-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="efbe6-140">Bindungen</span><span class="sxs-lookup"><span data-stu-id="efbe6-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="efbe6-141">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="efbe6-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="efbe6-142">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="efbe6-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
