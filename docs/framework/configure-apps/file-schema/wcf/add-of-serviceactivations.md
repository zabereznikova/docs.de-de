---
title: '&lt;add&gt; von &lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 956134f0db25055fb9a2f9317a770989cfdab67f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a><span data-ttu-id="b1c45-102">&lt;add&gt; von &lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="b1c45-102">&lt;add&gt; of &lt;serviceActivations&gt;</span></span>
<span data-ttu-id="b1c45-103">Ein Konfigurationselement, das Ihnen ermöglicht, virtuelle Dienstaktivierungseinstellungen zu definieren, die Ihren [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Diensttypen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b1c45-103">A configuration element that allows you to define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="b1c45-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b1c45-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="b1c45-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b1c45-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1c45-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="b1c45-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c45-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1c45-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1c45-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1c45-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b1c45-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1c45-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1c45-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1c45-110">Attributes</span></span>  
  
|<span data-ttu-id="b1c45-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b1c45-111">Attribute</span></span>|<span data-ttu-id="b1c45-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1c45-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1c45-113">factory</span><span class="sxs-lookup"><span data-stu-id="b1c45-113">factory</span></span>|<span data-ttu-id="b1c45-114">Eine Zeichenfolge, die den CLR-Typnamen der Factory angibt, die ein Dienstaktivierungselement generiert.</span><span class="sxs-lookup"><span data-stu-id="b1c45-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|  
|<span data-ttu-id="b1c45-115">service</span><span class="sxs-lookup"><span data-stu-id="b1c45-115">service</span></span>|<span data-ttu-id="b1c45-116">Der ServiceType, der den Dienst implementiert (entweder der vollqualifizierte Typname oder der kurze Typname, falls im Ordner "App_Code" enthalten).</span><span class="sxs-lookup"><span data-stu-id="b1c45-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|  
|<span data-ttu-id="b1c45-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="b1c45-117">relativeAddress</span></span>|<span data-ttu-id="b1c45-118">Die relative Adresse innerhalb der aktuellen IIS-Anwendung, z. B. "Service.svc".</span><span class="sxs-lookup"><span data-stu-id="b1c45-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="b1c45-119">In WCF 4.0 muss diese relative Adresse eine der gültigen Dateierweiterungen (.svc, .xamlx, …) enthalten. Für relativeUrl muss keine physische Datei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="b1c45-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1c45-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1c45-120">Child Elements</span></span>  
 <span data-ttu-id="b1c45-121">Keine</span><span class="sxs-lookup"><span data-stu-id="b1c45-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1c45-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1c45-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b1c45-123">Element</span><span class="sxs-lookup"><span data-stu-id="b1c45-123">Element</span></span>|<span data-ttu-id="b1c45-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1c45-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1c45-125">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="b1c45-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="b1c45-126">Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b1c45-126">A configuration section that describes activation settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1c45-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1c45-127">Remarks</span></span>  
 <span data-ttu-id="b1c45-128">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b1c45-128">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
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
  
 <span data-ttu-id="b1c45-129">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c45-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="b1c45-130">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="b1c45-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="b1c45-131">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="b1c45-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="b1c45-132">Außerdem ist `serviceHostingEnvironment` ein machinetoApplication-vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1c45-132">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="b1c45-133">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="b1c45-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="b1c45-134">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="b1c45-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="b1c45-135">Sie erfordert Erweiterungen im relatativeAddress-Element, z. B. .svc, .xoml oder .xamlx.</span><span class="sxs-lookup"><span data-stu-id="b1c45-135">It requires extensions in the relatativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="b1c45-136">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b1c45-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="b1c45-137">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="b1c45-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c45-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1c45-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
