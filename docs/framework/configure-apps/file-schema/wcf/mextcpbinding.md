---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430303"
---
# <a name="mextcpbinding"></a><span data-ttu-id="11760-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="11760-101">\<mexTcpBinding></span></span>
<span data-ttu-id="11760-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über TCP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11760-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="11760-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="11760-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="11760-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="11760-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="11760-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="11760-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="11760-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexTcpBinding>**</span><span class="sxs-lookup"><span data-stu-id="11760-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11760-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="11760-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11760-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11760-108">Attributes and Elements</span></span>  
 <span data-ttu-id="11760-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11760-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11760-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="11760-110">Attributes</span></span>  
  
|<span data-ttu-id="11760-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="11760-111">Attribute</span></span>|<span data-ttu-id="11760-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11760-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="11760-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="11760-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="11760-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="11760-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11760-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11760-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="11760-116">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="11760-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="11760-117">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11760-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="11760-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="11760-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="11760-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="11760-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="11760-120">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="11760-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="11760-121">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="11760-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11760-122">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11760-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="11760-123">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="11760-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="11760-124">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="11760-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11760-125">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="11760-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="11760-126">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="11760-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="11760-127">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="11760-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11760-128">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11760-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11760-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11760-129">Child Elements</span></span>  
 <span data-ttu-id="11760-130">Keine</span><span class="sxs-lookup"><span data-stu-id="11760-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11760-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11760-131">Parent Elements</span></span>  
  
|<span data-ttu-id="11760-132">Element</span><span class="sxs-lookup"><span data-stu-id="11760-132">Element</span></span>|<span data-ttu-id="11760-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11760-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11760-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="11760-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="11760-135">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="11760-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11760-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11760-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="11760-137">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="11760-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="11760-138">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="11760-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="11760-139">Metadaten</span><span class="sxs-lookup"><span data-stu-id="11760-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="11760-140">Bindungen</span><span class="sxs-lookup"><span data-stu-id="11760-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="11760-141">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="11760-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="11760-142">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="11760-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="11760-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="11760-143">\<binding></span></span>](bindings.md)
