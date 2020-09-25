---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8c15b06e60e4de6ede4c9a683a6701140533534c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204735"
---
# \<mexHttpBinding>

<span data-ttu-id="3be0c-101">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3be0c-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="3be0c-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="3be0c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3be0c-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3be0c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3be0c-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3be0c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3be0c-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="3be0c-105">Attributes</span></span>  
  
|<span data-ttu-id="3be0c-106">attribute</span><span class="sxs-lookup"><span data-stu-id="3be0c-106">Attribute</span></span>|<span data-ttu-id="3be0c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3be0c-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3be0c-108">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3be0c-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3be0c-109">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3be0c-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3be0c-110">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3be0c-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="3be0c-111">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="3be0c-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3be0c-112">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3be0c-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3be0c-113">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="3be0c-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3be0c-114">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3be0c-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="3be0c-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3be0c-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3be0c-116">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3be0c-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3be0c-117">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3be0c-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3be0c-118">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3be0c-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3be0c-119">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3be0c-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3be0c-120">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3be0c-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="3be0c-121">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3be0c-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3be0c-122">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3be0c-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3be0c-123">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3be0c-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3be0c-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3be0c-124">Child Elements</span></span>  

 <span data-ttu-id="3be0c-125">Keine</span><span class="sxs-lookup"><span data-stu-id="3be0c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3be0c-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3be0c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3be0c-127">Element</span><span class="sxs-lookup"><span data-stu-id="3be0c-127">Element</span></span>|<span data-ttu-id="3be0c-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3be0c-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="3be0c-129">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="3be0c-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3be0c-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3be0c-130">Remarks</span></span>  

 <span data-ttu-id="3be0c-131">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung mit deaktivierter Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="3be0c-131">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="3be0c-132">Sie unterstützt die meisten Metadatenanforderungen.</span><span class="sxs-lookup"><span data-stu-id="3be0c-132">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be0c-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3be0c-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="3be0c-134">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="3be0c-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="3be0c-135">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="3be0c-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="3be0c-136">Metadaten</span><span class="sxs-lookup"><span data-stu-id="3be0c-136">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="3be0c-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3be0c-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3be0c-138">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3be0c-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3be0c-139">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3be0c-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
