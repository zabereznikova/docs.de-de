---
title: '&lt;Dienst&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f909fe64e8997a39519fbde2e476a324319f57d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicegt"></a><span data-ttu-id="15696-102">&lt;Dienst&gt;</span><span class="sxs-lookup"><span data-stu-id="15696-102">&lt;service&gt;</span></span>
<span data-ttu-id="15696-103">Das `service`-Element enthält die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="15696-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="15696-104">Es enthält außerdem Endpunkte, die den Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="15696-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="15696-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="15696-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="15696-106">\<Services ></span><span class="sxs-lookup"><span data-stu-id="15696-106">\<services></span></span>  
<span data-ttu-id="15696-107">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="15696-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15696-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="15696-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15696-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15696-109">Attributes and Elements</span></span>  
 <span data-ttu-id="15696-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15696-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15696-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="15696-111">Attributes</span></span>  
  
|<span data-ttu-id="15696-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="15696-112">Attribute</span></span>|<span data-ttu-id="15696-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15696-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15696-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="15696-114">behaviorConfiguration</span></span>|<span data-ttu-id="15696-115">Eine Zeichenfolge mit dem Namen des Verhaltens, das zum Instanziieren des Diensts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="15696-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="15696-116">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="15696-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="15696-117">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="15696-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="15696-118">Name</span><span class="sxs-lookup"><span data-stu-id="15696-118">name</span></span>|<span data-ttu-id="15696-119">Erforderliches Zeichenfolgenattribut, das den Typ des zu instanziierenden Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="15696-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="15696-120">Diese Einstellung muss einem gültigen Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="15696-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="15696-121">Das Format muss `Namespace.Class.` lauten.</span><span class="sxs-lookup"><span data-stu-id="15696-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15696-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15696-122">Child Elements</span></span>  
  
|<span data-ttu-id="15696-123">Element</span><span class="sxs-lookup"><span data-stu-id="15696-123">Element</span></span>|<span data-ttu-id="15696-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15696-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15696-125">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="15696-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="15696-126">Eine Auflistung von `endpoint`-Elementen, die diesen Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="15696-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="15696-127">\<Host ></span><span class="sxs-lookup"><span data-stu-id="15696-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="15696-128">Gibt den Host dieser Dienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="15696-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="15696-129">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="15696-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15696-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15696-130">Parent Elements</span></span>  
  
|<span data-ttu-id="15696-131">Element</span><span class="sxs-lookup"><span data-stu-id="15696-131">Element</span></span>|<span data-ttu-id="15696-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15696-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15696-133">\<Services ></span><span class="sxs-lookup"><span data-stu-id="15696-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="15696-134">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="15696-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15696-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15696-135">Remarks</span></span>  
 <span data-ttu-id="15696-136">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="15696-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="15696-137">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="15696-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="15696-138">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="15696-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="15696-139">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="15696-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="15696-140">Das `behaviorConfiguration`-Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="15696-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="15696-141">Es identifiziert das vom Dienst verwendete Verhalten.</span><span class="sxs-lookup"><span data-stu-id="15696-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="15696-142">Das in diesem Attribut angegebene Verhalten muss mit einem Verhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="15696-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="15696-143">Jeder Dienst macht einen oder mehrere Endpunkte verfügbar, der über seine eigene Adresse und Bindung verfügt.</span><span class="sxs-lookup"><span data-stu-id="15696-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="15696-144">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="15696-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="15696-145">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="15696-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="15696-146">Das `name`-Attribut beschreibt, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="15696-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="15696-147">Das `bindingConfiguration`-Attribut legt fest, welche Konfiguration innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15696-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="15696-148">Ein Bindungsabschnitt kann verschiedene Konfigurationen definieren.</span><span class="sxs-lookup"><span data-stu-id="15696-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15696-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15696-149">Example</span></span>  
 <span data-ttu-id="15696-150">Dies ist ein Beispiel für eine Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="15696-150">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15696-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15696-151">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [<span data-ttu-id="15696-152">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="15696-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
