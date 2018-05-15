---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: c62f2bd1a34aca31ea9f9d5de17840f2967b269c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="92e18-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="92e18-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="92e18-103">Ein Konfigurationselement, mit dem Sie Einstellungen hinzufügen, die virtuelle dienstaktivierungseinstellungen zu definieren, die für die Windows Communication Foundation (WCF) Diensttypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="92e18-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="92e18-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="92e18-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="92e18-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92e18-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="92e18-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="92e18-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="92e18-107">\<ServiceActivations ></span><span class="sxs-lookup"><span data-stu-id="92e18-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e18-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="92e18-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92e18-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92e18-109">Attributes and Elements</span></span>  
 <span data-ttu-id="92e18-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92e18-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92e18-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="92e18-111">Attributes</span></span>  
 <span data-ttu-id="92e18-112">Keine</span><span class="sxs-lookup"><span data-stu-id="92e18-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="92e18-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92e18-113">Child Elements</span></span>  
  
|<span data-ttu-id="92e18-114">Element</span><span class="sxs-lookup"><span data-stu-id="92e18-114">Element</span></span>|<span data-ttu-id="92e18-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92e18-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92e18-116">\<add></span><span class="sxs-lookup"><span data-stu-id="92e18-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="92e18-117">Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="92e18-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92e18-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92e18-118">Parent Elements</span></span>  
  
|<span data-ttu-id="92e18-119">Element</span><span class="sxs-lookup"><span data-stu-id="92e18-119">Element</span></span>|<span data-ttu-id="92e18-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92e18-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92e18-121">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="92e18-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="92e18-122">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="92e18-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92e18-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92e18-123">Remarks</span></span>  
 <span data-ttu-id="92e18-124">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="92e18-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="92e18-125">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="92e18-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="92e18-126">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="92e18-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="92e18-127">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="92e18-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="92e18-128">Außerdem ist `serviceHostingEnvironment` ein machinetoApplication-vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="92e18-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="92e18-129">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="92e18-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="92e18-130">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="92e18-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="92e18-131">Sie erfordert Erweiterungen im relatativeAddress-Element, z. B. .svc, .xoml oder .xamlx.</span><span class="sxs-lookup"><span data-stu-id="92e18-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="92e18-132">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="92e18-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="92e18-133">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="92e18-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e18-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92e18-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
