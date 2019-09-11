---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855305"
---
# <a name="exposedmethod"></a><span data-ttu-id="3148e-101">\<exposedMethod-></span><span class="sxs-lookup"><span data-stu-id="3148e-101">\<exposedMethod></span></span>
<span data-ttu-id="3148e-102">Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3148e-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="3148e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3148e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3148e-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3148e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3148e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts->** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="3148e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="3148e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract->** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="3148e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="3148e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<exposedmethods->** ](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="3148e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="3148e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<exposedMethod->**</span><span class="sxs-lookup"><span data-stu-id="3148e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3148e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3148e-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3148e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3148e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3148e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3148e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3148e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3148e-112">Attributes</span></span>  
  
|<span data-ttu-id="3148e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3148e-113">Attribute</span></span>|<span data-ttu-id="3148e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3148e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3148e-115">NAME</span><span class="sxs-lookup"><span data-stu-id="3148e-115">name</span></span>|<span data-ttu-id="3148e-116">Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3148e-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3148e-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3148e-117">Child Elements</span></span>  
 <span data-ttu-id="3148e-118">Keine</span><span class="sxs-lookup"><span data-stu-id="3148e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3148e-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3148e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3148e-120">Element</span><span class="sxs-lookup"><span data-stu-id="3148e-120">Element</span></span>|<span data-ttu-id="3148e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3148e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3148e-122">\<exposedmethods-></span><span class="sxs-lookup"><span data-stu-id="3148e-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="3148e-123">Eine Auflistung von [ \<exposedMethod->](exposedmethod.md) Elementen.</span><span class="sxs-lookup"><span data-stu-id="3148e-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3148e-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3148e-124">Remarks</span></span>  
 <span data-ttu-id="3148e-125">Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3148e-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="3148e-126">Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3148e-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="3148e-127">Wenn Sie auch die Datei ComSvcConfig. exe ausführen, generiert Sie den folgenden Dienstvertrag, in dem die zuvor erwähnten Methoden als [ \<exposedMethod->](exposedmethod.md) Elemente aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="3148e-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="3148e-128">Bei der Dienst Initialisierung versucht die Common Language Runtime, einen Dienstvertrag zu generieren, indem reflektiert wird und nur die Methoden hinzugefügt werden, die in der Liste der [ \<exposedMethod->](exposedmethod.md) Elemente enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3148e-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="3148e-129">Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3148e-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3148e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3148e-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="3148e-131">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="3148e-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="3148e-132">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3148e-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="3148e-133">Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen</span><span class="sxs-lookup"><span data-stu-id="3148e-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
