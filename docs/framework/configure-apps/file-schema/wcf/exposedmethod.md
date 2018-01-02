---
title: '&lt;exposedMethod&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9e5c9f61d67850d249d54ed5adfc08bf40bad47
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="59fe7-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="59fe7-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="59fe7-103">Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="59fe7-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="59fe7-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="59fe7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59fe7-105">\<ComContracts ></span><span class="sxs-lookup"><span data-stu-id="59fe7-105">\<comContracts></span></span>  
<span data-ttu-id="59fe7-106">\<ComContract ></span><span class="sxs-lookup"><span data-stu-id="59fe7-106">\<comContract></span></span>  
<span data-ttu-id="59fe7-107">\<Methoden ></span><span class="sxs-lookup"><span data-stu-id="59fe7-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59fe7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="59fe7-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59fe7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59fe7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59fe7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59fe7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59fe7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="59fe7-111">Attributes</span></span>  
  
|<span data-ttu-id="59fe7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="59fe7-112">Attribute</span></span>|<span data-ttu-id="59fe7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59fe7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59fe7-114">Name</span><span class="sxs-lookup"><span data-stu-id="59fe7-114">name</span></span>|<span data-ttu-id="59fe7-115">Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="59fe7-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59fe7-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59fe7-116">Child Elements</span></span>  
 <span data-ttu-id="59fe7-117">Keine</span><span class="sxs-lookup"><span data-stu-id="59fe7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59fe7-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59fe7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="59fe7-119">Element</span><span class="sxs-lookup"><span data-stu-id="59fe7-119">Element</span></span>|<span data-ttu-id="59fe7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59fe7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59fe7-121">\<ExposedMethods ></span><span class="sxs-lookup"><span data-stu-id="59fe7-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="59fe7-122">Eine Auflistung von [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="59fe7-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59fe7-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59fe7-123">Remarks</span></span>  
 <span data-ttu-id="59fe7-124">Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="59fe7-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="59fe7-125">Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="59fe7-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="59fe7-126">Wenn Sie auch die ComSvcConfig.exe ausführen, wird die folgende Dienstvertrag mit den zuvor erwähnten Methoden als [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="59fe7-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 <span data-ttu-id="59fe7-127">Bei Initialisierung des Diensts wird der Laufzeit versucht, einen Dienstvertrag zu generieren, durch Reflektieren über und nur die in der Liste der enthaltenen Methoden hinzufügen [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="59fe7-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="59fe7-128">Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="59fe7-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fe7-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59fe7-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [<span data-ttu-id="59fe7-130">\<ComContracts ></span><span class="sxs-lookup"><span data-stu-id="59fe7-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="59fe7-131">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="59fe7-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="59fe7-132">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="59fe7-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
