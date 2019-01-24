---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 5da05c7b6a9685b9e34b3181ce8e0bd31ccd052b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704955"
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="0edbd-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="0edbd-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="0edbd-103">Ein Konfigurationselement mit dem Sie Einstellungen hinzufügen, die virtuelle dienstaktivierungseinstellungen zu definieren, die die Windows Communication Foundation (WCF) Diensttypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0edbd-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="0edbd-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0edbd-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="0edbd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0edbd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0edbd-106">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="0edbd-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="0edbd-107">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="0edbd-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0edbd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0edbd-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0edbd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0edbd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0edbd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0edbd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0edbd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="0edbd-111">Attributes</span></span>  
 <span data-ttu-id="0edbd-112">Keine</span><span class="sxs-lookup"><span data-stu-id="0edbd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0edbd-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0edbd-113">Child Elements</span></span>  
  
|<span data-ttu-id="0edbd-114">Element</span><span class="sxs-lookup"><span data-stu-id="0edbd-114">Element</span></span>|<span data-ttu-id="0edbd-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0edbd-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0edbd-116">\<add></span><span class="sxs-lookup"><span data-stu-id="0edbd-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="0edbd-117">Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="0edbd-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0edbd-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0edbd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0edbd-119">Element</span><span class="sxs-lookup"><span data-stu-id="0edbd-119">Element</span></span>|<span data-ttu-id="0edbd-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0edbd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0edbd-121">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="0edbd-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="0edbd-122">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="0edbd-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0edbd-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0edbd-123">Remarks</span></span>  
 <span data-ttu-id="0edbd-124">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0edbd-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="0edbd-125">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0edbd-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="0edbd-126">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="0edbd-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="0edbd-127">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="0edbd-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="0edbd-128">Außerdem ist `serviceHostingEnvironment` ein machinetoApplication-vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0edbd-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="0edbd-129">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="0edbd-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="0edbd-130">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="0edbd-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="0edbd-131">Sie erfordert Erweiterungen im relatativeAddress-Element, z. B. .svc, .xoml oder .xamlx.</span><span class="sxs-lookup"><span data-stu-id="0edbd-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="0edbd-132">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0edbd-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="0edbd-133">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="0edbd-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0edbd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0edbd-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
