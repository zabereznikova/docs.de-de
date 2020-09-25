---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 2947f0de6a88f39463e58a3b39bda52588fe4baa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203903"
---
# \<exposedMethod>

<span data-ttu-id="3b585-101">Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3b585-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="3b585-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b585-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b585-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3b585-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3b585-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b585-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b585-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="3b585-105">Attributes</span></span>  
  
|<span data-ttu-id="3b585-106">attribute</span><span class="sxs-lookup"><span data-stu-id="3b585-106">Attribute</span></span>|<span data-ttu-id="3b585-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b585-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b585-108">name</span><span class="sxs-lookup"><span data-stu-id="3b585-108">name</span></span>|<span data-ttu-id="3b585-109">Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3b585-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b585-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b585-110">Child Elements</span></span>  

 <span data-ttu-id="3b585-111">Keine</span><span class="sxs-lookup"><span data-stu-id="3b585-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b585-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b585-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3b585-113">Element</span><span class="sxs-lookup"><span data-stu-id="3b585-113">Element</span></span>|<span data-ttu-id="3b585-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b585-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="3b585-115">Eine Auflistung von- [\<exposedMethod>](exposedmethod.md) Elementen.</span><span class="sxs-lookup"><span data-stu-id="3b585-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b585-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3b585-116">Remarks</span></span>  

 <span data-ttu-id="3b585-117">Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3b585-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="3b585-118">Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3b585-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="3b585-119">Wenn Sie die ComSvcConfig.exe auch ausführen, generiert Sie den folgenden Dienstvertrag, der die zuvor erwähnten Methoden als [\<exposedMethod>](exposedmethod.md) Elemente auflistet.</span><span class="sxs-lookup"><span data-stu-id="3b585-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="3b585-120">Bei der Dienst Initialisierung wird von der Laufzeit versucht, einen Dienstvertrag zu generieren, indem reflektiert und nur die in der Liste der Elemente enthaltenen Methoden hinzugefügt werden [\<exposedMethod>](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="3b585-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="3b585-121">Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3b585-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b585-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b585-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="3b585-123">Integration in com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3b585-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="3b585-124">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="3b585-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
