---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855017"
---
# <a name="service"></a><span data-ttu-id="b2ed5-101">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="b2ed5-101">\<service></span></span>
<span data-ttu-id="b2ed5-102">Das `service`-Element enthält die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="b2ed5-103">Es enthält außerdem Endpunkte, die den Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-103">It also contains endpoints that expose the service.</span></span>  
  
<span data-ttu-id="b2ed5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2ed5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b2ed5-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b2ed5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b2ed5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienste >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="b2ed5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="b2ed5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Dienst >**</span><span class="sxs-lookup"><span data-stu-id="b2ed5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ed5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2ed5-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2ed5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2ed5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2ed5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2ed5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2ed5-111">Attributes</span></span>  
  
|<span data-ttu-id="b2ed5-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2ed5-112">Attribute</span></span>|<span data-ttu-id="b2ed5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2ed5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2ed5-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="b2ed5-114">behaviorConfiguration</span></span>|<span data-ttu-id="b2ed5-115">Eine Zeichenfolge mit dem Namen des Verhaltens, das zum Instanziieren des Diensts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="b2ed5-116">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="b2ed5-117">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="b2ed5-118">NAME</span><span class="sxs-lookup"><span data-stu-id="b2ed5-118">name</span></span>|<span data-ttu-id="b2ed5-119">Erforderliches Zeichenfolgenattribut, das den Typ des zu instanziierenden Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="b2ed5-120">Diese Einstellung muss einem gültigen Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="b2ed5-121">Das Format muss `Namespace.Class.` lauten.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2ed5-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2ed5-122">Child Elements</span></span>  
  
|<span data-ttu-id="b2ed5-123">Element</span><span class="sxs-lookup"><span data-stu-id="b2ed5-123">Element</span></span>|<span data-ttu-id="b2ed5-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2ed5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2ed5-125">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="b2ed5-125">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="b2ed5-126">Eine Auflistung von `endpoint`-Elementen, die diesen Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="b2ed5-127">\<host></span><span class="sxs-lookup"><span data-stu-id="b2ed5-127">\<host></span></span>](host.md)|<span data-ttu-id="b2ed5-128">Gibt den Host dieser Dienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="b2ed5-129">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2ed5-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2ed5-130">Parent Elements</span></span>  
  
|<span data-ttu-id="b2ed5-131">Element</span><span class="sxs-lookup"><span data-stu-id="b2ed5-131">Element</span></span>|<span data-ttu-id="b2ed5-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2ed5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2ed5-133">\<services></span><span class="sxs-lookup"><span data-stu-id="b2ed5-133">\<services></span></span>](services.md)|<span data-ttu-id="b2ed5-134">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2ed5-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2ed5-135">Remarks</span></span>  
 <span data-ttu-id="b2ed5-136">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="b2ed5-137">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="b2ed5-138">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="b2ed5-139">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="b2ed5-140">Das `behaviorConfiguration`-Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="b2ed5-141">Es identifiziert das vom Dienst verwendete Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="b2ed5-142">Das in diesem Attribut angegebene Verhalten muss mit einem Verhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="b2ed5-143">Jeder Dienst macht einen oder mehrere Endpunkte verfügbar, der über seine eigene Adresse und Bindung verfügt.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="b2ed5-144">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="b2ed5-145">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="b2ed5-146">Das `name`-Attribut beschreibt, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="b2ed5-147">Das `bindingConfiguration`-Attribut legt fest, welche Konfiguration innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="b2ed5-148">Ein Bindungsabschnitt kann verschiedene Konfigurationen definieren.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2ed5-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2ed5-149">Example</span></span>  
 <span data-ttu-id="b2ed5-150">Dies ist ein Beispiel für eine Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="b2ed5-150">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2ed5-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2ed5-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="b2ed5-152">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="b2ed5-152">Configuring Services</span></span>](../../../wcf/configuring-services.md)
