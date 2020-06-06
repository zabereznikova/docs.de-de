---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855305"
---
# \<exposedMethod>
<span data-ttu-id="065ef-101">Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="065ef-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="065ef-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="065ef-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="065ef-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="065ef-103">Attributes and Elements</span></span>  
 <span data-ttu-id="065ef-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="065ef-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="065ef-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="065ef-105">Attributes</span></span>  
  
|<span data-ttu-id="065ef-106">attribute</span><span class="sxs-lookup"><span data-stu-id="065ef-106">Attribute</span></span>|<span data-ttu-id="065ef-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="065ef-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="065ef-108">name</span><span class="sxs-lookup"><span data-stu-id="065ef-108">name</span></span>|<span data-ttu-id="065ef-109">Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="065ef-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="065ef-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="065ef-110">Child Elements</span></span>  
 <span data-ttu-id="065ef-111">Keine</span><span class="sxs-lookup"><span data-stu-id="065ef-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="065ef-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="065ef-112">Parent Elements</span></span>  
  
|<span data-ttu-id="065ef-113">Element</span><span class="sxs-lookup"><span data-stu-id="065ef-113">Element</span></span>|<span data-ttu-id="065ef-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="065ef-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="065ef-115">Eine Auflistung von- [\<exposedMethod>](exposedmethod.md) Elementen.</span><span class="sxs-lookup"><span data-stu-id="065ef-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="065ef-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="065ef-116">Remarks</span></span>  
 <span data-ttu-id="065ef-117">Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="065ef-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="065ef-118">Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="065ef-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="065ef-119">Wenn Sie auch die Datei "ComSvcConfig. exe" ausführen, generiert Sie den folgenden Dienstvertrag, der die zuvor erwähnten Methoden als Elemente auflistet [\<exposedMethod>](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="065ef-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="065ef-120">Bei der Dienst Initialisierung wird von der Laufzeit versucht, einen Dienstvertrag zu generieren, indem reflektiert und nur die in der Liste der Elemente enthaltenen Methoden hinzugefügt werden [\<exposedMethod>](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="065ef-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="065ef-121">Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="065ef-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065ef-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="065ef-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="065ef-123">Integration in com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="065ef-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="065ef-124">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="065ef-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
