---
title: <endpoint> von <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 79d827691ec3898ad94af9835077c61ea35990ab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185846"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="11593-102">\<endpoint> von \<client></span><span class="sxs-lookup"><span data-stu-id="11593-102">\<endpoint> of \<client></span></span>

<span data-ttu-id="11593-103">Gibt die Vertrags-, Bindungs- und Adresseigenschaften für den Kanalendpunkt an, mit dem Clients eine Verbindung zu Dienstendpunkten auf dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="11593-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="11593-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11593-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11593-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11593-105">Attributes and Elements</span></span>  

 <span data-ttu-id="11593-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11593-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11593-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="11593-107">Attributes</span></span>  
  
|<span data-ttu-id="11593-108">attribute</span><span class="sxs-lookup"><span data-stu-id="11593-108">Attribute</span></span>|<span data-ttu-id="11593-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11593-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11593-110">address</span><span class="sxs-lookup"><span data-stu-id="11593-110">address</span></span>|<span data-ttu-id="11593-111">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="11593-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="11593-112">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="11593-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="11593-113">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11593-113">The default is an empty string.</span></span> <span data-ttu-id="11593-114">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="11593-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="11593-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="11593-115">behaviorConfiguration</span></span>|<span data-ttu-id="11593-116">Eine Zeichenfolge mit dem Namen des Verhaltens, das zur Instanziierung des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11593-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="11593-117">Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="11593-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="11593-118">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11593-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="11593-119">binding</span><span class="sxs-lookup"><span data-stu-id="11593-119">binding</span></span>|<span data-ttu-id="11593-120">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="11593-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="11593-121">Eine Zeichenfolge, die den Typ der zu verwendenden Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="11593-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="11593-122">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="11593-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="11593-123">Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.</span><span class="sxs-lookup"><span data-stu-id="11593-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="11593-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="11593-124">bindingConfiguration</span></span>|<span data-ttu-id="11593-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="11593-125">Optional.</span></span> <span data-ttu-id="11593-126">Eine Zeichenfolge, die den Namen der Bindungskonfiguration enthält, die beim Instanziieren des Endpunkts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11593-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="11593-127">Die Bindungskonfiguration muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="11593-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="11593-128">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11593-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="11593-129">Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="11593-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="11593-130">Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="11593-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="11593-131">Andernfalls wird unter Umständen eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="11593-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="11593-132">contract</span><span class="sxs-lookup"><span data-stu-id="11593-132">contract</span></span>|<span data-ttu-id="11593-133">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="11593-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="11593-134">Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="11593-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="11593-135">Die Assembly muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="11593-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="11593-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="11593-136">endpointConfiguration</span></span>|<span data-ttu-id="11593-137">Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.</span><span class="sxs-lookup"><span data-stu-id="11593-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="11593-138">Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="11593-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="11593-139">kind</span><span class="sxs-lookup"><span data-stu-id="11593-139">kind</span></span>|<span data-ttu-id="11593-140">Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="11593-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="11593-141">Der Typ muss im `<extensions>`-Abschnitt oder in machine.config registriert werden. Wenn nichts angegeben wird, wird ein allgemeiner Kanalendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="11593-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="11593-142">name</span><span class="sxs-lookup"><span data-stu-id="11593-142">name</span></span>|<span data-ttu-id="11593-143">Optionales Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="11593-143">Optional string attribute.</span></span> <span data-ttu-id="11593-144">Dieses Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="11593-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="11593-145">Sie können für einen angegebenen Vertragstyp mehrere Clients definieren.</span><span class="sxs-lookup"><span data-stu-id="11593-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="11593-146">Jede Definition muss sich durch einen eindeutigen Konfigurationsnamen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="11593-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="11593-147">Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="11593-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="11593-148">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11593-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="11593-149">Das `name`-Attribut einer Bindung wird zum Definitionsexport durch WSDL verwendet.</span><span class="sxs-lookup"><span data-stu-id="11593-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11593-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11593-150">Child Elements</span></span>  
  
|<span data-ttu-id="11593-151">Element</span><span class="sxs-lookup"><span data-stu-id="11593-151">Element</span></span>|<span data-ttu-id="11593-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11593-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="11593-153">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="11593-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="11593-154">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="11593-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11593-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11593-155">Parent Elements</span></span>  
  
|<span data-ttu-id="11593-156">Element</span><span class="sxs-lookup"><span data-stu-id="11593-156">Element</span></span>|<span data-ttu-id="11593-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11593-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="11593-158">Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="11593-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="11593-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11593-159">Example</span></span>  

 <span data-ttu-id="11593-160">Dies ist ein Beispiel für eine Kanalendpunkt-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="11593-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="11593-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11593-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="11593-162">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="11593-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="11593-163">Clients</span><span class="sxs-lookup"><span data-stu-id="11593-163">Clients</span></span>](../../../wcf/feature-details/clients.md)
