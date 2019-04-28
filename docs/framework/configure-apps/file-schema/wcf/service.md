---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 68bddc01b02d9885b3f0fc4c2cbc5c3249de03f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670396"
---
# <a name="service"></a><span data-ttu-id="df8ca-101">\<service></span><span class="sxs-lookup"><span data-stu-id="df8ca-101">\<service></span></span>
<span data-ttu-id="df8ca-102">Das `service`-Element enthält die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="df8ca-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="df8ca-103">Es enthält außerdem Endpunkte, die den Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="df8ca-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="df8ca-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="df8ca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="df8ca-105">\<services></span><span class="sxs-lookup"><span data-stu-id="df8ca-105">\<services></span></span>  
<span data-ttu-id="df8ca-106">\<service></span><span class="sxs-lookup"><span data-stu-id="df8ca-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df8ca-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="df8ca-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df8ca-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="df8ca-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df8ca-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="df8ca-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df8ca-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="df8ca-110">Attributes</span></span>  
  
|<span data-ttu-id="df8ca-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="df8ca-111">Attribute</span></span>|<span data-ttu-id="df8ca-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df8ca-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df8ca-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="df8ca-113">behaviorConfiguration</span></span>|<span data-ttu-id="df8ca-114">Eine Zeichenfolge mit dem Namen des Verhaltens, das zum Instanziieren des Diensts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="df8ca-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="df8ca-115">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="df8ca-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="df8ca-116">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="df8ca-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="df8ca-117">Name</span><span class="sxs-lookup"><span data-stu-id="df8ca-117">name</span></span>|<span data-ttu-id="df8ca-118">Erforderliches Zeichenfolgenattribut, das den Typ des zu instanziierenden Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="df8ca-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="df8ca-119">Diese Einstellung muss einem gültigen Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="df8ca-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="df8ca-120">Das Format muss `Namespace.Class.` lauten.</span><span class="sxs-lookup"><span data-stu-id="df8ca-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df8ca-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df8ca-121">Child Elements</span></span>  
  
|<span data-ttu-id="df8ca-122">Element</span><span class="sxs-lookup"><span data-stu-id="df8ca-122">Element</span></span>|<span data-ttu-id="df8ca-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df8ca-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df8ca-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="df8ca-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="df8ca-125">Eine Auflistung von `endpoint`-Elementen, die diesen Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="df8ca-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="df8ca-126">\<host></span><span class="sxs-lookup"><span data-stu-id="df8ca-126">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="df8ca-127">Gibt den Host dieser Dienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="df8ca-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="df8ca-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="df8ca-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df8ca-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df8ca-129">Parent Elements</span></span>  
  
|<span data-ttu-id="df8ca-130">Element</span><span class="sxs-lookup"><span data-stu-id="df8ca-130">Element</span></span>|<span data-ttu-id="df8ca-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df8ca-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df8ca-132">\<services></span><span class="sxs-lookup"><span data-stu-id="df8ca-132">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="df8ca-133">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="df8ca-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df8ca-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df8ca-134">Remarks</span></span>  
 <span data-ttu-id="df8ca-135">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="df8ca-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="df8ca-136">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="df8ca-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="df8ca-137">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="df8ca-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="df8ca-138">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="df8ca-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="df8ca-139">Das `behaviorConfiguration`-Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="df8ca-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="df8ca-140">Es identifiziert das vom Dienst verwendete Verhalten.</span><span class="sxs-lookup"><span data-stu-id="df8ca-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="df8ca-141">Das in diesem Attribut angegebene Verhalten muss mit einem Verhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="df8ca-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="df8ca-142">Jeder Dienst macht einen oder mehrere Endpunkte verfügbar, der über seine eigene Adresse und Bindung verfügt.</span><span class="sxs-lookup"><span data-stu-id="df8ca-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="df8ca-143">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="df8ca-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="df8ca-144">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="df8ca-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="df8ca-145">Das `name`-Attribut beschreibt, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="df8ca-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="df8ca-146">Das `bindingConfiguration`-Attribut legt fest, welche Konfiguration innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df8ca-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="df8ca-147">Ein Bindungsabschnitt kann verschiedene Konfigurationen definieren.</span><span class="sxs-lookup"><span data-stu-id="df8ca-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df8ca-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df8ca-148">Example</span></span>  
 <span data-ttu-id="df8ca-149">Dies ist ein Beispiel für eine Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="df8ca-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="df8ca-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df8ca-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="df8ca-151">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="df8ca-151">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
