---
title: <endpoint>-Element
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 71ddb3b860870ee8feeeb36c3f64fa7bfebb0f10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925827"
---
# <a name="endpoint-element"></a><span data-ttu-id="a572d-102">\<Endpunkt > Element</span><span class="sxs-lookup"><span data-stu-id="a572d-102">\<endpoint> element</span></span>
<span data-ttu-id="a572d-103">Gibt die Bindung, den Vertrag und Adresseigenschaften für einen Dienstendpunkt an, der zur Verfügbarmachung von Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a572d-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="a572d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a572d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a572d-105">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="a572d-105">\<service></span></span>  
<span data-ttu-id="a572d-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="a572d-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a572d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a572d-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a572d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a572d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a572d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a572d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a572d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a572d-110">Attributes</span></span>  
  
|<span data-ttu-id="a572d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a572d-111">Attribute</span></span>|<span data-ttu-id="a572d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a572d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a572d-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="a572d-113">address</span></span>|<span data-ttu-id="a572d-114">Eine Zeichenfolge mit der Adresse des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="a572d-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="a572d-115">Die Adresse kann als absolute oder relative Adresse angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a572d-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="a572d-116">Bei Bereitstellung einer relativen Adresse wird vom Host erwartet, dass er eine Basisadresse bereitstellt, die für das in der Bindung verwendete Transportschema geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="a572d-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="a572d-117">Wenn keine Adresse konfiguriert wird, wird angenommen, dass die Basisadresse der Adresse für diesen Endpunkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="a572d-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="a572d-118">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a572d-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="a572d-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="a572d-119">behaviorConfiguration</span></span>|<span data-ttu-id="a572d-120">Eine Zeichenfolge mit dem Namen des Verhaltens, das am Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a572d-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="a572d-121">Bindung</span><span class="sxs-lookup"><span data-stu-id="a572d-121">binding</span></span>|<span data-ttu-id="a572d-122">Erforderliches Zeichenfolgenattribut, das den Typ der zu verwendenden Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="a572d-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="a572d-123">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a572d-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="a572d-124">Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.</span><span class="sxs-lookup"><span data-stu-id="a572d-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="a572d-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a572d-125">bindingConfiguration</span></span>|<span data-ttu-id="a572d-126">Eine Zeichenfolge, die den Namen der Bindung enthält, die beim Instanziieren des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a572d-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="a572d-127">Der Name der Bindung muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="a572d-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="a572d-128">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a572d-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="a572d-129">Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="a572d-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="a572d-130">Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a572d-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="a572d-131">Andernfalls wird unter Umständen eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a572d-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="a572d-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="a572d-132">bindingName</span></span>|<span data-ttu-id="a572d-133">Eine Zeichenfolge, die den eindeutigen qualifizierten Namen der Bindung für den Definitionsexport über WSDL definiert.</span><span class="sxs-lookup"><span data-stu-id="a572d-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="a572d-134">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a572d-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="a572d-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="a572d-135">bindingNamespace</span></span>|<span data-ttu-id="a572d-136">Eine Zeichenfolge, die den qualifizierten Namen des Namespaces der Bindung für den Definitionsexport über WSDL definiert.</span><span class="sxs-lookup"><span data-stu-id="a572d-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="a572d-137">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a572d-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="a572d-138">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="a572d-138">contract</span></span>|<span data-ttu-id="a572d-139">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a572d-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="a572d-140">Die Assembly muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="a572d-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="a572d-141">Wenn eine Dienstimplementierung einen einzelnen Vertragstyp implementiert, kann diese Eigenschaft ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="a572d-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="a572d-142">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a572d-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="a572d-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="a572d-143">endpointConfiguration</span></span>|<span data-ttu-id="a572d-144">Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.</span><span class="sxs-lookup"><span data-stu-id="a572d-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="a572d-145">Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a572d-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="a572d-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="a572d-146">isSystemEndpoint</span></span>|<span data-ttu-id="a572d-147">Ein boolescher Wert, der angibt, ob ein Endpunkt ein Infrastrukturendpunkt ist.</span><span class="sxs-lookup"><span data-stu-id="a572d-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="a572d-148">kind</span><span class="sxs-lookup"><span data-stu-id="a572d-148">kind</span></span>|<span data-ttu-id="a572d-149">Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a572d-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="a572d-150">Der Typ muss im Abschnitt `<extensions>` oder in machine.config registriert werden. Wenn kein Wert angegeben wird, wird ein allgemeiner Dienstendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="a572d-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="a572d-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="a572d-151">listenUriMode</span></span>|<span data-ttu-id="a572d-152">Gibt an, wie der Transport die `ListenUri` verarbeitet, die für die Überwachung durch den Dienst bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a572d-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="a572d-153">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a572d-153">Valid values are</span></span><br /><br /> <span data-ttu-id="a572d-154">-Explizit</span><span class="sxs-lookup"><span data-stu-id="a572d-154">-   Explicit</span></span><br /><span data-ttu-id="a572d-155">-Eindeutig</span><span class="sxs-lookup"><span data-stu-id="a572d-155">-   Unique</span></span><br /><br /> <span data-ttu-id="a572d-156">Der Standardwert ist Explicit.</span><span class="sxs-lookup"><span data-stu-id="a572d-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="a572d-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="a572d-157">listenUri</span></span>|<span data-ttu-id="a572d-158">Eine Zeichenfolge mit dem URI, an dem der Dienstendpunkt lauscht.</span><span class="sxs-lookup"><span data-stu-id="a572d-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="a572d-159">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a572d-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="a572d-160">Name</span><span class="sxs-lookup"><span data-stu-id="a572d-160">name</span></span>|<span data-ttu-id="a572d-161">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="a572d-161">Optional attribute.</span></span> <span data-ttu-id="a572d-162">Eine Zeichenfolge, die den Namen des Dienstendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a572d-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="a572d-163">Der Standardwert ist die Verkettung des Bindungsnamen und des Vertragsbeschreibungsnamens.</span><span class="sxs-lookup"><span data-stu-id="a572d-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="a572d-164">Dienste haben möglicherweise mehrere Endpunkte, sodass das `name`-Attribut des Endpunkts sich vom Namen des Diensts unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="a572d-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a572d-165">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a572d-165">Child Elements</span></span>  
  
|<span data-ttu-id="a572d-166">Element</span><span class="sxs-lookup"><span data-stu-id="a572d-166">Element</span></span>|<span data-ttu-id="a572d-167">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a572d-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a572d-168">\<headers></span><span class="sxs-lookup"><span data-stu-id="a572d-168">\<headers></span></span>](headers.md)|<span data-ttu-id="a572d-169">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="a572d-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="a572d-170">\<identity></span><span class="sxs-lookup"><span data-stu-id="a572d-170">\<identity></span></span>](identity.md)|<span data-ttu-id="a572d-171">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="a572d-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a572d-172">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a572d-172">Parent Elements</span></span>  
  
|<span data-ttu-id="a572d-173">Element</span><span class="sxs-lookup"><span data-stu-id="a572d-173">Element</span></span>|<span data-ttu-id="a572d-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a572d-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a572d-175">\<service></span><span class="sxs-lookup"><span data-stu-id="a572d-175">\<service></span></span>](service.md)|<span data-ttu-id="a572d-176">Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a572d-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a572d-177">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a572d-177">Example</span></span>  
 <span data-ttu-id="a572d-178">Dies ist ein Beispiel für eine Dienstendpunkt-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a572d-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="a572d-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a572d-179">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="a572d-180">Endpunkte Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="a572d-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="a572d-181">Vorgehensweise: Erstellen eines Dienst Endpunkts in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a572d-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
