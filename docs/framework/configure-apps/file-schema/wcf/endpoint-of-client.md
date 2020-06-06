---
title: <endpoint> von <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855318"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="e1e31-102">\<endpoint> von \<client></span><span class="sxs-lookup"><span data-stu-id="e1e31-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="e1e31-103">Gibt die Vertrags-, Bindungs- und Adresseigenschaften für den Kanalendpunkt an, mit dem Clients eine Verbindung zu Dienstendpunkten auf dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="e1e31-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="e1e31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1e31-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1e31-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1e31-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e1e31-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1e31-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1e31-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1e31-107">Attributes</span></span>  
  
|<span data-ttu-id="e1e31-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e1e31-108">Attribute</span></span>|<span data-ttu-id="e1e31-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1e31-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1e31-110">address</span><span class="sxs-lookup"><span data-stu-id="e1e31-110">address</span></span>|<span data-ttu-id="e1e31-111">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="e1e31-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="e1e31-112">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="e1e31-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="e1e31-113">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e1e31-113">The default is an empty string.</span></span> <span data-ttu-id="e1e31-114">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="e1e31-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="e1e31-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e1e31-115">behaviorConfiguration</span></span>|<span data-ttu-id="e1e31-116">Eine Zeichenfolge mit dem Namen des Verhaltens, das zur Instanziierung des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1e31-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="e1e31-117">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="e1e31-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="e1e31-118">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e1e31-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="e1e31-119">binding</span><span class="sxs-lookup"><span data-stu-id="e1e31-119">binding</span></span>|<span data-ttu-id="e1e31-120">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="e1e31-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="e1e31-121">Eine Zeichenfolge, die den Typ der zu verwendenden Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="e1e31-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="e1e31-122">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1e31-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="e1e31-123">Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.</span><span class="sxs-lookup"><span data-stu-id="e1e31-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="e1e31-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e1e31-124">bindingConfiguration</span></span>|<span data-ttu-id="e1e31-125">(Optional)</span><span class="sxs-lookup"><span data-stu-id="e1e31-125">Optional.</span></span> <span data-ttu-id="e1e31-126">Eine Zeichenfolge, die den Namen der Bindungskonfiguration enthält, die beim Instanziieren des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1e31-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="e1e31-127">Die Bindungskonfiguration muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="e1e31-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="e1e31-128">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e1e31-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e1e31-129">Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1e31-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="e1e31-130">Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e1e31-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="e1e31-131">Andernfalls wird unter Umständen eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e1e31-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="e1e31-132">contract</span><span class="sxs-lookup"><span data-stu-id="e1e31-132">contract</span></span>|<span data-ttu-id="e1e31-133">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="e1e31-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="e1e31-134">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e1e31-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="e1e31-135">Die Assembly muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="e1e31-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="e1e31-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="e1e31-136">endpointConfiguration</span></span>|<span data-ttu-id="e1e31-137">Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.</span><span class="sxs-lookup"><span data-stu-id="e1e31-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="e1e31-138">Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1e31-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="e1e31-139">kind</span><span class="sxs-lookup"><span data-stu-id="e1e31-139">kind</span></span>|<span data-ttu-id="e1e31-140">Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="e1e31-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="e1e31-141">Der Typ muss im `<extensions>` Abschnitt oder in Machine. config registriert werden. Wenn nichts angegeben wird, wird ein allgemeiner Kanal Endpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1e31-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="e1e31-142">name</span><span class="sxs-lookup"><span data-stu-id="e1e31-142">name</span></span>|<span data-ttu-id="e1e31-143">Optionales Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="e1e31-143">Optional string attribute.</span></span> <span data-ttu-id="e1e31-144">Dieses Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e1e31-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="e1e31-145">Sie können für einen angegebenen Vertragstyp mehrere Clients definieren.</span><span class="sxs-lookup"><span data-stu-id="e1e31-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="e1e31-146">Jede Definition muss sich durch einen eindeutigen Konfigurationsnamen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e1e31-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="e1e31-147">Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e1e31-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="e1e31-148">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e1e31-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e1e31-149">Das `name`-Attribut einer Bindung wird zum Definitionsexport durch WSDL verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1e31-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1e31-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1e31-150">Child Elements</span></span>  
  
|<span data-ttu-id="e1e31-151">Element</span><span class="sxs-lookup"><span data-stu-id="e1e31-151">Element</span></span>|<span data-ttu-id="e1e31-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1e31-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="e1e31-153">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="e1e31-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="e1e31-154">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="e1e31-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1e31-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1e31-155">Parent Elements</span></span>  
  
|<span data-ttu-id="e1e31-156">Element</span><span class="sxs-lookup"><span data-stu-id="e1e31-156">Element</span></span>|<span data-ttu-id="e1e31-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1e31-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="e1e31-158">Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e1e31-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e1e31-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1e31-159">Example</span></span>  
 <span data-ttu-id="e1e31-160">Dies ist ein Beispiel für eine Kanalendpunkt-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e1e31-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="e1e31-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1e31-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="e1e31-162">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e1e31-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="e1e31-163">Clients</span><span class="sxs-lookup"><span data-stu-id="e1e31-163">Clients</span></span>](../../../wcf/feature-details/clients.md)
