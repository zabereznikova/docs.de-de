---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: c12f57d68de870123d92c8a101e2999c24bb988f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855017"
---
# \<service>
<span data-ttu-id="dba95-101">Das `service`-Element enthält die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="dba95-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="dba95-102">Es enthält außerdem Endpunkte, die den Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="dba95-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="dba95-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="dba95-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dba95-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dba95-104">Attributes and Elements</span></span>  
 <span data-ttu-id="dba95-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dba95-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dba95-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="dba95-106">Attributes</span></span>  
  
|<span data-ttu-id="dba95-107">attribute</span><span class="sxs-lookup"><span data-stu-id="dba95-107">Attribute</span></span>|<span data-ttu-id="dba95-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dba95-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dba95-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="dba95-109">behaviorConfiguration</span></span>|<span data-ttu-id="dba95-110">Eine Zeichenfolge mit dem Namen des Verhaltens, das zum Instanziieren des Diensts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dba95-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="dba95-111">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="dba95-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="dba95-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dba95-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="dba95-113">name</span><span class="sxs-lookup"><span data-stu-id="dba95-113">name</span></span>|<span data-ttu-id="dba95-114">Erforderliches Zeichenfolgenattribut, das den Typ des zu instanziierenden Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="dba95-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="dba95-115">Diese Einstellung muss einem gültigen Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dba95-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="dba95-116">Das Format muss `Namespace.Class.` lauten.</span><span class="sxs-lookup"><span data-stu-id="dba95-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dba95-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dba95-117">Child Elements</span></span>  
  
|<span data-ttu-id="dba95-118">Element</span><span class="sxs-lookup"><span data-stu-id="dba95-118">Element</span></span>|<span data-ttu-id="dba95-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dba95-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="dba95-120">Eine Auflistung von `endpoint`-Elementen, die diesen Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="dba95-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="dba95-121">Gibt den Host dieser Dienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="dba95-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="dba95-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="dba95-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dba95-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dba95-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dba95-124">Element</span><span class="sxs-lookup"><span data-stu-id="dba95-124">Element</span></span>|<span data-ttu-id="dba95-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dba95-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="dba95-126">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="dba95-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dba95-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dba95-127">Remarks</span></span>  
 <span data-ttu-id="dba95-128">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="dba95-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="dba95-129">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="dba95-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="dba95-130">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="dba95-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="dba95-131">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="dba95-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="dba95-132">Das `behaviorConfiguration`-Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="dba95-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="dba95-133">Es identifiziert das vom Dienst verwendete Verhalten.</span><span class="sxs-lookup"><span data-stu-id="dba95-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="dba95-134">Das in diesem Attribut angegebene Verhalten muss mit einem Verhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="dba95-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="dba95-135">Jeder Dienst macht einen oder mehrere Endpunkte verfügbar, der über seine eigene Adresse und Bindung verfügt.</span><span class="sxs-lookup"><span data-stu-id="dba95-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="dba95-136">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="dba95-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="dba95-137">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="dba95-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="dba95-138">Das `name`-Attribut beschreibt, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="dba95-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="dba95-139">Das `bindingConfiguration`-Attribut legt fest, welche Konfiguration innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dba95-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="dba95-140">Ein Bindungsabschnitt kann verschiedene Konfigurationen definieren.</span><span class="sxs-lookup"><span data-stu-id="dba95-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dba95-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dba95-141">Example</span></span>  
 <span data-ttu-id="dba95-142">Dies ist ein Beispiel für eine Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dba95-142">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dba95-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dba95-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="dba95-144">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="dba95-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)
