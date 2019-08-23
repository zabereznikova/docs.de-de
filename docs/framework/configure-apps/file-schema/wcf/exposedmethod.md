---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 032139b714aa11079c7ee8610c332e404b3981ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919003"
---
# <a name="exposedmethod"></a><span data-ttu-id="02a7c-101">\<exposedMethod-></span><span class="sxs-lookup"><span data-stu-id="02a7c-101">\<exposedMethod></span></span>
<span data-ttu-id="02a7c-102">Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="02a7c-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="02a7c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="02a7c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="02a7c-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="02a7c-104">\<comContracts></span></span>  
<span data-ttu-id="02a7c-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="02a7c-105">\<comContract></span></span>  
<span data-ttu-id="02a7c-106">\<Methoden ></span><span class="sxs-lookup"><span data-stu-id="02a7c-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a7c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="02a7c-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02a7c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02a7c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02a7c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02a7c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02a7c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="02a7c-110">Attributes</span></span>  
  
|<span data-ttu-id="02a7c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="02a7c-111">Attribute</span></span>|<span data-ttu-id="02a7c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02a7c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02a7c-113">Name</span><span class="sxs-lookup"><span data-stu-id="02a7c-113">name</span></span>|<span data-ttu-id="02a7c-114">Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="02a7c-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02a7c-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02a7c-115">Child Elements</span></span>  
 <span data-ttu-id="02a7c-116">Keine</span><span class="sxs-lookup"><span data-stu-id="02a7c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02a7c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02a7c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="02a7c-118">Element</span><span class="sxs-lookup"><span data-stu-id="02a7c-118">Element</span></span>|<span data-ttu-id="02a7c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02a7c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02a7c-120">\<exposedmethods-></span><span class="sxs-lookup"><span data-stu-id="02a7c-120">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="02a7c-121">Eine Auflistung von [ \<exposedMethod->](exposedmethod.md) Elementen.</span><span class="sxs-lookup"><span data-stu-id="02a7c-121">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02a7c-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02a7c-122">Remarks</span></span>  
 <span data-ttu-id="02a7c-123">Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="02a7c-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="02a7c-124">Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="02a7c-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="02a7c-125">Wenn Sie auch die Datei ComSvcConfig. exe ausführen, generiert Sie den folgenden Dienstvertrag, in dem die zuvor erwähnten Methoden als [ \<exposedMethod->](exposedmethod.md) Elemente aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="02a7c-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="02a7c-126">Bei der Dienst Initialisierung versucht die Common Language Runtime, einen Dienstvertrag zu generieren, indem reflektiert wird und nur die Methoden hinzugefügt werden, die in der Liste der [ \<exposedMethod->](exposedmethod.md) Elemente enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="02a7c-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="02a7c-127">Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="02a7c-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a7c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02a7c-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="02a7c-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="02a7c-129">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="02a7c-130">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="02a7c-130">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="02a7c-131">Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen</span><span class="sxs-lookup"><span data-stu-id="02a7c-131">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
