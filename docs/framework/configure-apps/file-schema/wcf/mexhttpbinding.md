---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8d5b9378bf7769754586d0b13f742659aee18f03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430908"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="5028f-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5028f-101">\<mexHttpBinding></span></span>
<span data-ttu-id="5028f-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5028f-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="5028f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5028f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5028f-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5028f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5028f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="5028f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5028f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpBinding>**</span><span class="sxs-lookup"><span data-stu-id="5028f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5028f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5028f-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5028f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5028f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5028f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5028f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5028f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5028f-110">Attributes</span></span>  
  
|<span data-ttu-id="5028f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="5028f-111">Attribute</span></span>|<span data-ttu-id="5028f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5028f-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5028f-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="5028f-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5028f-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="5028f-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5028f-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5028f-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="5028f-116">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="5028f-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5028f-117">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5028f-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5028f-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="5028f-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5028f-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5028f-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5028f-120">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="5028f-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5028f-121">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="5028f-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5028f-122">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5028f-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5028f-123">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="5028f-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5028f-124">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="5028f-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5028f-125">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="5028f-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5028f-126">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="5028f-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5028f-127">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="5028f-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5028f-128">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5028f-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5028f-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5028f-129">Child Elements</span></span>  
 <span data-ttu-id="5028f-130">Keine</span><span class="sxs-lookup"><span data-stu-id="5028f-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5028f-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5028f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="5028f-132">Element</span><span class="sxs-lookup"><span data-stu-id="5028f-132">Element</span></span>|<span data-ttu-id="5028f-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5028f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5028f-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5028f-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="5028f-135">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="5028f-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5028f-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5028f-136">Remarks</span></span>  
 <span data-ttu-id="5028f-137">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung mit deaktivierter Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="5028f-137">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="5028f-138">Sie unterstützt die meisten Metadatenanforderungen.</span><span class="sxs-lookup"><span data-stu-id="5028f-138">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5028f-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5028f-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="5028f-140">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="5028f-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="5028f-141">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="5028f-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="5028f-142">Metadaten</span><span class="sxs-lookup"><span data-stu-id="5028f-142">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="5028f-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5028f-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5028f-144">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5028f-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5028f-145">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5028f-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5028f-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="5028f-146">\<binding></span></span>](bindings.md)
