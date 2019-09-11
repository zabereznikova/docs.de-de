---
title: <endpoint> von <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855318"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="4cacf-102">\<Endpunkt > des \<Client ></span><span class="sxs-lookup"><span data-stu-id="4cacf-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="4cacf-103">Gibt die Vertrags-, Bindungs- und Adresseigenschaften für den Kanalendpunkt an, mit dem Clients eine Verbindung zu Dienstendpunkten auf dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="4cacf-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="4cacf-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4cacf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4cacf-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4cacf-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4cacf-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="4cacf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="4cacf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Endpunkt >**</span><span class="sxs-lookup"><span data-stu-id="4cacf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cacf-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cacf-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cacf-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4cacf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4cacf-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4cacf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cacf-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4cacf-111">Attributes</span></span>  
  
|<span data-ttu-id="4cacf-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4cacf-112">Attribute</span></span>|<span data-ttu-id="4cacf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cacf-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4cacf-114">Adresse</span><span class="sxs-lookup"><span data-stu-id="4cacf-114">address</span></span>|<span data-ttu-id="4cacf-115">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="4cacf-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="4cacf-116">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="4cacf-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="4cacf-117">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4cacf-117">The default is an empty string.</span></span> <span data-ttu-id="4cacf-118">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="4cacf-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="4cacf-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cacf-119">behaviorConfiguration</span></span>|<span data-ttu-id="4cacf-120">Eine Zeichenfolge mit dem Namen des Verhaltens, das zur Instanziierung des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cacf-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="4cacf-121">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="4cacf-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="4cacf-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4cacf-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="4cacf-123">Bindung</span><span class="sxs-lookup"><span data-stu-id="4cacf-123">binding</span></span>|<span data-ttu-id="4cacf-124">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="4cacf-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="4cacf-125">Eine Zeichenfolge, die den Typ der zu verwendenden Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="4cacf-126">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4cacf-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="4cacf-127">Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.</span><span class="sxs-lookup"><span data-stu-id="4cacf-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="4cacf-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cacf-128">bindingConfiguration</span></span>|<span data-ttu-id="4cacf-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="4cacf-129">Optional.</span></span> <span data-ttu-id="4cacf-130">Eine Zeichenfolge, die den Namen der Bindungskonfiguration enthält, die beim Instanziieren des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cacf-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="4cacf-131">Die Bindungskonfiguration muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="4cacf-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="4cacf-132">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4cacf-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4cacf-133">Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cacf-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="4cacf-134">Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4cacf-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="4cacf-135">Andernfalls wird unter Umständen eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4cacf-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="4cacf-136">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="4cacf-136">contract</span></span>|<span data-ttu-id="4cacf-137">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="4cacf-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="4cacf-138">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="4cacf-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="4cacf-139">Die Assembly muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="4cacf-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="4cacf-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cacf-140">endpointConfiguration</span></span>|<span data-ttu-id="4cacf-141">Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.</span><span class="sxs-lookup"><span data-stu-id="4cacf-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="4cacf-142">Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4cacf-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="4cacf-143">kind</span><span class="sxs-lookup"><span data-stu-id="4cacf-143">kind</span></span>|<span data-ttu-id="4cacf-144">Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="4cacf-145">Der Typ muss im Abschnitt `<extensions>` oder in machine.config registriert werden. Wenn nichts angegeben wird, wird ein allgemeiner Channelendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="4cacf-146">NAME</span><span class="sxs-lookup"><span data-stu-id="4cacf-146">name</span></span>|<span data-ttu-id="4cacf-147">Optionales Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="4cacf-147">Optional string attribute.</span></span> <span data-ttu-id="4cacf-148">Dieses Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="4cacf-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="4cacf-149">Sie können für einen angegebenen Vertragstyp mehrere Clients definieren.</span><span class="sxs-lookup"><span data-stu-id="4cacf-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="4cacf-150">Jede Definition muss sich durch einen eindeutigen Konfigurationsnamen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4cacf-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="4cacf-151">Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="4cacf-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="4cacf-152">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4cacf-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4cacf-153">Das `name`-Attribut einer Bindung wird zum Definitionsexport durch WSDL verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cacf-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cacf-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4cacf-154">Child Elements</span></span>  
  
|<span data-ttu-id="4cacf-155">Element</span><span class="sxs-lookup"><span data-stu-id="4cacf-155">Element</span></span>|<span data-ttu-id="4cacf-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cacf-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cacf-157">\<headers></span><span class="sxs-lookup"><span data-stu-id="4cacf-157">\<headers></span></span>](headers.md)|<span data-ttu-id="4cacf-158">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="4cacf-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="4cacf-159">\<identity></span><span class="sxs-lookup"><span data-stu-id="4cacf-159">\<identity></span></span>](identity.md)|<span data-ttu-id="4cacf-160">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="4cacf-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4cacf-161">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4cacf-161">Parent Elements</span></span>  
  
|<span data-ttu-id="4cacf-162">Element</span><span class="sxs-lookup"><span data-stu-id="4cacf-162">Element</span></span>|<span data-ttu-id="4cacf-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cacf-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cacf-164">\<client></span><span class="sxs-lookup"><span data-stu-id="4cacf-164">\<client></span></span>](client.md)|<span data-ttu-id="4cacf-165">Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4cacf-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4cacf-166">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cacf-166">Example</span></span>  
 <span data-ttu-id="4cacf-167">Dies ist ein Beispiel für eine Kanalendpunkt-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4cacf-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="4cacf-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cacf-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="4cacf-169">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4cacf-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="4cacf-170">Clients</span><span class="sxs-lookup"><span data-stu-id="4cacf-170">Clients</span></span>](../../../wcf/feature-details/clients.md)
