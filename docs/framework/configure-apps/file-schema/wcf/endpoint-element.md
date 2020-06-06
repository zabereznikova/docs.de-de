---
title: <endpoint>-Element
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855380"
---
# <a name="endpoint-element"></a><span data-ttu-id="8c706-102">\<endpoint>-Element</span><span class="sxs-lookup"><span data-stu-id="8c706-102">\<endpoint> element</span></span>
<span data-ttu-id="8c706-103">Gibt die Bindung, den Vertrag und Adresseigenschaften für einen Dienstendpunkt an, der zur Verfügbarmachung von Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c706-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="8c706-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c706-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c706-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8c706-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8c706-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c706-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c706-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="8c706-107">Attributes</span></span>  
  
|<span data-ttu-id="8c706-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8c706-108">Attribute</span></span>|<span data-ttu-id="8c706-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c706-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c706-110">address</span><span class="sxs-lookup"><span data-stu-id="8c706-110">address</span></span>|<span data-ttu-id="8c706-111">Eine Zeichenfolge mit der Adresse des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="8c706-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="8c706-112">Die Adresse kann als absolute oder relative Adresse angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c706-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="8c706-113">Bei Bereitstellung einer relativen Adresse wird vom Host erwartet, dass er eine Basisadresse bereitstellt, die für das in der Bindung verwendete Transportschema geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="8c706-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="8c706-114">Wenn keine Adresse konfiguriert wird, wird angenommen, dass die Basisadresse der Adresse für diesen Endpunkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="8c706-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="8c706-115">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c706-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="8c706-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c706-116">behaviorConfiguration</span></span>|<span data-ttu-id="8c706-117">Eine Zeichenfolge mit dem Namen des Verhaltens, das am Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c706-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="8c706-118">binding</span><span class="sxs-lookup"><span data-stu-id="8c706-118">binding</span></span>|<span data-ttu-id="8c706-119">Erforderliches Zeichenfolgenattribut, das den Typ der zu verwendenden Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="8c706-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="8c706-120">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c706-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="8c706-121">Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.</span><span class="sxs-lookup"><span data-stu-id="8c706-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="8c706-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c706-122">bindingConfiguration</span></span>|<span data-ttu-id="8c706-123">Eine Zeichenfolge, die den Namen der Bindung enthält, die beim Instanziieren des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c706-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="8c706-124">Der Name der Bindung muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="8c706-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="8c706-125">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c706-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="8c706-126">Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c706-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="8c706-127">Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8c706-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="8c706-128">Andernfalls wird unter Umständen eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8c706-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="8c706-129">bindingName</span><span class="sxs-lookup"><span data-stu-id="8c706-129">bindingName</span></span>|<span data-ttu-id="8c706-130">Eine Zeichenfolge, die den eindeutigen qualifizierten Namen der Bindung für den Definitionsexport über WSDL definiert.</span><span class="sxs-lookup"><span data-stu-id="8c706-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="8c706-131">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c706-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="8c706-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="8c706-132">bindingNamespace</span></span>|<span data-ttu-id="8c706-133">Eine Zeichenfolge, die den qualifizierten Namen des Namespaces der Bindung für den Definitionsexport über WSDL definiert.</span><span class="sxs-lookup"><span data-stu-id="8c706-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="8c706-134">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c706-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="8c706-135">contract</span><span class="sxs-lookup"><span data-stu-id="8c706-135">contract</span></span>|<span data-ttu-id="8c706-136">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="8c706-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="8c706-137">Die Assembly muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="8c706-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="8c706-138">Wenn eine Dienstimplementierung einen einzelnen Vertragstyp implementiert, kann diese Eigenschaft ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="8c706-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="8c706-139">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c706-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="8c706-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c706-140">endpointConfiguration</span></span>|<span data-ttu-id="8c706-141">Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.</span><span class="sxs-lookup"><span data-stu-id="8c706-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="8c706-142">Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c706-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="8c706-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="8c706-143">isSystemEndpoint</span></span>|<span data-ttu-id="8c706-144">Ein boolescher Wert, der angibt, ob ein Endpunkt ein Infrastrukturendpunkt ist.</span><span class="sxs-lookup"><span data-stu-id="8c706-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="8c706-145">kind</span><span class="sxs-lookup"><span data-stu-id="8c706-145">kind</span></span>|<span data-ttu-id="8c706-146">Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="8c706-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="8c706-147">Der Typ muss im `<extensions>` Abschnitt oder in Machine. config registriert werden. Wenn nichts angegeben wird, wird ein allgemeiner Dienst Endpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="8c706-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="8c706-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="8c706-148">listenUriMode</span></span>|<span data-ttu-id="8c706-149">Gibt an, wie der Transport die `ListenUri` verarbeitet, die für die Überwachung durch den Dienst bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8c706-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="8c706-150">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="8c706-150">Valid values are</span></span><br /><br /> <span data-ttu-id="8c706-151">-Explizit</span><span class="sxs-lookup"><span data-stu-id="8c706-151">-   Explicit</span></span><br /><span data-ttu-id="8c706-152">-Eindeutig</span><span class="sxs-lookup"><span data-stu-id="8c706-152">-   Unique</span></span><br /><br /> <span data-ttu-id="8c706-153">Der Standardwert ist Explicit.</span><span class="sxs-lookup"><span data-stu-id="8c706-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="8c706-154">listenUri</span><span class="sxs-lookup"><span data-stu-id="8c706-154">listenUri</span></span>|<span data-ttu-id="8c706-155">Eine Zeichenfolge mit dem URI, an dem der Dienstendpunkt lauscht.</span><span class="sxs-lookup"><span data-stu-id="8c706-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="8c706-156">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c706-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="8c706-157">name</span><span class="sxs-lookup"><span data-stu-id="8c706-157">name</span></span>|<span data-ttu-id="8c706-158">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="8c706-158">Optional attribute.</span></span> <span data-ttu-id="8c706-159">Eine Zeichenfolge, die den Namen des Dienstendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="8c706-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="8c706-160">Der Standardwert ist die Verkettung des Bindungsnamen und des Vertragsbeschreibungsnamens.</span><span class="sxs-lookup"><span data-stu-id="8c706-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="8c706-161">Dienste haben möglicherweise mehrere Endpunkte, sodass das `name`-Attribut des Endpunkts sich vom Namen des Diensts unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="8c706-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c706-162">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c706-162">Child Elements</span></span>  
  
|<span data-ttu-id="8c706-163">Element</span><span class="sxs-lookup"><span data-stu-id="8c706-163">Element</span></span>|<span data-ttu-id="8c706-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c706-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="8c706-165">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="8c706-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="8c706-166">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="8c706-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c706-167">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c706-167">Parent Elements</span></span>  
  
|<span data-ttu-id="8c706-168">Element</span><span class="sxs-lookup"><span data-stu-id="8c706-168">Element</span></span>|<span data-ttu-id="8c706-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c706-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="8c706-170">Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="8c706-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c706-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c706-171">Example</span></span>  
 <span data-ttu-id="8c706-172">Dies ist ein Beispiel für eine Dienstendpunkt-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8c706-172">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c706-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c706-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="8c706-174">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="8c706-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="8c706-175">Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8c706-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
