---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 82422716482eafe996534e3bf1a94b4c7a604a6d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145119"
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="8f4a1-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="8f4a1-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="8f4a1-103">Ein Konfigurationselement mit dem Sie Einstellungen hinzufügen, die virtuelle dienstaktivierungseinstellungen zu definieren, die die Windows Communication Foundation (WCF) Diensttypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="8f4a1-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="8f4a1-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8f4a1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f4a1-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="8f4a1-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="8f4a1-107">\<ServiceActivations ></span><span class="sxs-lookup"><span data-stu-id="8f4a1-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4a1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f4a1-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f4a1-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f4a1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8f4a1-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f4a1-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f4a1-111">Attributes</span></span>  
 <span data-ttu-id="8f4a1-112">Keine</span><span class="sxs-lookup"><span data-stu-id="8f4a1-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8f4a1-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f4a1-113">Child Elements</span></span>  
  
|<span data-ttu-id="8f4a1-114">Element</span><span class="sxs-lookup"><span data-stu-id="8f4a1-114">Element</span></span>|<span data-ttu-id="8f4a1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f4a1-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f4a1-116">\<add></span><span class="sxs-lookup"><span data-stu-id="8f4a1-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="8f4a1-117">Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f4a1-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f4a1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8f4a1-119">Element</span><span class="sxs-lookup"><span data-stu-id="8f4a1-119">Element</span></span>|<span data-ttu-id="8f4a1-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f4a1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f4a1-121">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="8f4a1-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="8f4a1-122">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f4a1-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f4a1-123">Remarks</span></span>  
 <span data-ttu-id="8f4a1-124">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
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
  
 <span data-ttu-id="8f4a1-125">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="8f4a1-126">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="8f4a1-127">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="8f4a1-128">Außerdem ist `serviceHostingEnvironment` ein machinetoApplication-vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="8f4a1-129">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="8f4a1-130">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="8f4a1-131">Sie erfordert Erweiterungen im relatativeAddress-Element, z. B. .svc, .xoml oder .xamlx.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="8f4a1-132">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="8f4a1-133">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="8f4a1-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4a1-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f4a1-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
