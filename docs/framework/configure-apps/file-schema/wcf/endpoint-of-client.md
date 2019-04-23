---
title: <endpoint> von <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 3af41ad5b5681b08aac44d984372ab5ac66caf5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231200"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="7424f-102">\<Endpunkt > der \<Client ></span><span class="sxs-lookup"><span data-stu-id="7424f-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="7424f-103">Gibt die Vertrags-, Bindungs- und Adresseigenschaften für den Kanalendpunkt an, mit dem Clients eine Verbindung zu Dienstendpunkten auf dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="7424f-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="7424f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7424f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7424f-105">\<client></span><span class="sxs-lookup"><span data-stu-id="7424f-105">\<client></span></span>  
<span data-ttu-id="7424f-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="7424f-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7424f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7424f-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7424f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7424f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7424f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7424f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7424f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7424f-110">Attributes</span></span>  
  
|<span data-ttu-id="7424f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7424f-111">Attribute</span></span>|<span data-ttu-id="7424f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7424f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7424f-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="7424f-113">address</span></span>|<span data-ttu-id="7424f-114">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="7424f-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7424f-115">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="7424f-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="7424f-116">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7424f-116">The default is an empty string.</span></span> <span data-ttu-id="7424f-117">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="7424f-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="7424f-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7424f-118">behaviorConfiguration</span></span>|<span data-ttu-id="7424f-119">Eine Zeichenfolge mit dem Namen des Verhaltens, das zur Instanziierung des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7424f-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="7424f-120">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="7424f-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="7424f-121">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7424f-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="7424f-122">Bindung</span><span class="sxs-lookup"><span data-stu-id="7424f-122">binding</span></span>|<span data-ttu-id="7424f-123">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="7424f-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7424f-124">Eine Zeichenfolge, die den Typ der zu verwendenden Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="7424f-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="7424f-125">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7424f-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="7424f-126">Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.</span><span class="sxs-lookup"><span data-stu-id="7424f-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="7424f-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7424f-127">bindingConfiguration</span></span>|<span data-ttu-id="7424f-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7424f-128">Optional.</span></span> <span data-ttu-id="7424f-129">Eine Zeichenfolge, die den Namen der Bindungskonfiguration enthält, die beim Instanziieren des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7424f-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="7424f-130">Die Bindungskonfiguration muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="7424f-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="7424f-131">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7424f-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7424f-132">Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="7424f-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="7424f-133">Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7424f-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="7424f-134">Andernfalls wird unter Umständen eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7424f-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="7424f-135">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="7424f-135">contract</span></span>|<span data-ttu-id="7424f-136">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="7424f-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7424f-137">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7424f-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="7424f-138">Die Assembly muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="7424f-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="7424f-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="7424f-139">endpointConfiguration</span></span>|<span data-ttu-id="7424f-140">Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.</span><span class="sxs-lookup"><span data-stu-id="7424f-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="7424f-141">Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7424f-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="7424f-142">kind</span><span class="sxs-lookup"><span data-stu-id="7424f-142">kind</span></span>|<span data-ttu-id="7424f-143">Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="7424f-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="7424f-144">Der Typ muss im Abschnitt `<extensions>` oder in machine.config registriert werden. Wenn nichts angegeben wird, wird ein allgemeiner Channelendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="7424f-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="7424f-145">Name</span><span class="sxs-lookup"><span data-stu-id="7424f-145">name</span></span>|<span data-ttu-id="7424f-146">Optionales Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="7424f-146">Optional string attribute.</span></span> <span data-ttu-id="7424f-147">Dieses Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="7424f-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="7424f-148">Sie können für einen angegebenen Vertragstyp mehrere Clients definieren.</span><span class="sxs-lookup"><span data-stu-id="7424f-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="7424f-149">Jede Definition muss sich durch einen eindeutigen Konfigurationsnamen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7424f-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="7424f-150">Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="7424f-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="7424f-151">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7424f-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7424f-152">Das `name`-Attribut einer Bindung wird zum Definitionsexport durch WSDL verwendet.</span><span class="sxs-lookup"><span data-stu-id="7424f-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7424f-153">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7424f-153">Child Elements</span></span>  
  
|<span data-ttu-id="7424f-154">Element</span><span class="sxs-lookup"><span data-stu-id="7424f-154">Element</span></span>|<span data-ttu-id="7424f-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7424f-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7424f-156">\<headers></span><span class="sxs-lookup"><span data-stu-id="7424f-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="7424f-157">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="7424f-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="7424f-158">\<identity></span><span class="sxs-lookup"><span data-stu-id="7424f-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="7424f-159">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="7424f-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7424f-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7424f-160">Parent Elements</span></span>  
  
|<span data-ttu-id="7424f-161">Element</span><span class="sxs-lookup"><span data-stu-id="7424f-161">Element</span></span>|<span data-ttu-id="7424f-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7424f-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7424f-163">\<client></span><span class="sxs-lookup"><span data-stu-id="7424f-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="7424f-164">Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="7424f-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7424f-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7424f-165">Example</span></span>  
 <span data-ttu-id="7424f-166">Dies ist ein Beispiel für eine Kanalendpunkt-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="7424f-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="7424f-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7424f-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="7424f-168">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7424f-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7424f-169">Clients</span><span class="sxs-lookup"><span data-stu-id="7424f-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
