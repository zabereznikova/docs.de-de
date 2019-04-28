---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 91eafa46aa73b5e6d359fcbe48f098f9f8a4d0f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644298"
---
# <a name="exposedmethod"></a><span data-ttu-id="60c58-101">\<ExposedMethod ></span><span class="sxs-lookup"><span data-stu-id="60c58-101">\<exposedMethod></span></span>
<span data-ttu-id="60c58-102">Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="60c58-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="60c58-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="60c58-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="60c58-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="60c58-104">\<comContracts></span></span>  
<span data-ttu-id="60c58-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="60c58-105">\<comContract></span></span>  
<span data-ttu-id="60c58-106">\<methods></span><span class="sxs-lookup"><span data-stu-id="60c58-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60c58-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="60c58-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60c58-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="60c58-108">Attributes and Elements</span></span>  
 <span data-ttu-id="60c58-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60c58-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60c58-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="60c58-110">Attributes</span></span>  
  
|<span data-ttu-id="60c58-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="60c58-111">Attribute</span></span>|<span data-ttu-id="60c58-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60c58-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60c58-113">Name</span><span class="sxs-lookup"><span data-stu-id="60c58-113">name</span></span>|<span data-ttu-id="60c58-114">Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="60c58-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60c58-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60c58-115">Child Elements</span></span>  
 <span data-ttu-id="60c58-116">Keine</span><span class="sxs-lookup"><span data-stu-id="60c58-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60c58-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60c58-117">Parent Elements</span></span>  
  
|<span data-ttu-id="60c58-118">Element</span><span class="sxs-lookup"><span data-stu-id="60c58-118">Element</span></span>|<span data-ttu-id="60c58-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60c58-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60c58-120">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="60c58-120">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="60c58-121">Eine Auflistung von [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="60c58-121">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60c58-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60c58-122">Remarks</span></span>  
 <span data-ttu-id="60c58-123">Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="60c58-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="60c58-124">Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60c58-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="60c58-125">Wenn Sie auch die ComSvcConfig.exe ausführen, wird die folgende Dienstvertrag mit den bereits erwähnten Methoden als [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="60c58-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="60c58-126">Zum Zeitpunkt der dienstinitialisierung, versucht die Runtime, die einen Dienstvertrag zu erzeugen, durch Reflektieren über und nur die Methoden in der Liste der enthaltenen [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="60c58-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="60c58-127">Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="60c58-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c58-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60c58-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="60c58-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="60c58-129">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="60c58-130">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="60c58-130">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="60c58-131">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="60c58-131">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
