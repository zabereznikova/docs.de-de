---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 7b0c91bafc14dee0d298a5cd31dc674f5002466a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274195"
---
# <a name="systemservicemodel"></a><span data-ttu-id="e8c80-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e8c80-102">\<system.serviceModel></span></span>
<span data-ttu-id="e8c80-103">Dieser Konfigurationsabschnitt enthält alle Elemente der Windows Communication Foundation (WCF)-ServiceModel-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e8c80-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8c80-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8c80-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e8c80-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e8c80-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8c80-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8c80-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e8c80-107">Attributes</span></span>  
 <span data-ttu-id="e8c80-108">Keine</span><span class="sxs-lookup"><span data-stu-id="e8c80-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8c80-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8c80-109">Child Elements</span></span>  
  
|<span data-ttu-id="e8c80-110">Element</span><span class="sxs-lookup"><span data-stu-id="e8c80-110">Element</span></span>|<span data-ttu-id="e8c80-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8c80-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8c80-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e8c80-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="e8c80-113">In diesem Abschnitt werden zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors` definiert.</span><span class="sxs-lookup"><span data-stu-id="e8c80-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e8c80-114">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="e8c80-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="e8c80-115">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e8c80-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="e8c80-116">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e8c80-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="e8c80-117">Dieser Abschnitt enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e8c80-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="e8c80-118">Jeder Eintrag wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e8c80-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="e8c80-119">Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e8c80-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="e8c80-120">\<client></span><span class="sxs-lookup"><span data-stu-id="e8c80-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="e8c80-121">Dieser Abschnitt enthält eine Liste mit Endpunkten, die ein Client für die Verbindungsherstellung mit einem Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8c80-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="e8c80-122">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e8c80-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="e8c80-123">Dieser Abschnitt definiert für WCF und COM-Interop aktivierte COM-Verträge.</span><span class="sxs-lookup"><span data-stu-id="e8c80-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="e8c80-124">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="e8c80-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="e8c80-125">Dieser Abschnitt kann nur in der Datei machine.config definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8c80-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="e8c80-126">Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="e8c80-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e8c80-127">Jede Auflistung definiert verhaltenselemente für alle WCF-Endpunkten und-Dienste auf dem Computer bzw.</span><span class="sxs-lookup"><span data-stu-id="e8c80-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="e8c80-128">Wenn ein Verhalten in beiden definiert ist `<commonBehaviors>` und `<behaviors>` Abschnitten, die das Verhalten in der \<Behaviors >-Abschnitt Priorität eingeräumt.</span><span class="sxs-lookup"><span data-stu-id="e8c80-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="e8c80-129">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="e8c80-129">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="e8c80-130">Dieser Abschnitt enthält Einstellungen für die Diagnosefunktionen von WCF.</span><span class="sxs-lookup"><span data-stu-id="e8c80-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="e8c80-131">Der Benutzer kann Ablaufverfolgung, Leistungsindikatoren und den WMI-Anbieter aktivieren/deaktivieren und benutzerdefinierte Meldungsfilter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e8c80-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="e8c80-132">\<extensions></span><span class="sxs-lookup"><span data-stu-id="e8c80-132">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="e8c80-133">Dieser Abschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte von Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e8c80-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="e8c80-134">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="e8c80-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="e8c80-135">Dieser Abschnitt definiert einen Satz von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e8c80-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="e8c80-136">\<routing></span><span class="sxs-lookup"><span data-stu-id="e8c80-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e8c80-137">In diesem Abschnitt definiert einen Satz von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die definieren, die Zielendpunkte zum Senden von Nachrichten, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e8c80-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="e8c80-138">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="e8c80-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="e8c80-139">Dieser Abschnitt definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8c80-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="e8c80-140">Wenn dieser Abschnitt leer ist, wird der Standardtyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8c80-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="e8c80-141">\<services></span><span class="sxs-lookup"><span data-stu-id="e8c80-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="e8c80-142">Der Abschnitt enthält eine Auflistung von Diensten.</span><span class="sxs-lookup"><span data-stu-id="e8c80-142">The section contains a collection of services.</span></span> <span data-ttu-id="e8c80-143">Für jeden in der Assembly definierten Dienst enthält dieses Element ein `service`-Element mit den Einstellungen für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="e8c80-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="e8c80-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e8c80-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e8c80-145">Dieser Abschnitt definiert eine Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt.</span><span class="sxs-lookup"><span data-stu-id="e8c80-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="e8c80-146">Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e8c80-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="e8c80-147">Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert.</span><span class="sxs-lookup"><span data-stu-id="e8c80-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="e8c80-148">Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e8c80-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="e8c80-149">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e8c80-149">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|<span data-ttu-id="e8c80-150">Dieser Abschnitt definiert die überwachungseinstellungen für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="e8c80-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e8c80-151">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8c80-151">Parent Elements</span></span>  
  
|<span data-ttu-id="e8c80-152">Element</span><span class="sxs-lookup"><span data-stu-id="e8c80-152">Element</span></span>|<span data-ttu-id="e8c80-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8c80-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8c80-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e8c80-154">\<configuration></span></span>|<span data-ttu-id="e8c80-155">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e8c80-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8c80-156">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8c80-156">Remarks</span></span>  
 <span data-ttu-id="e8c80-157">WCF fügt den Konfigurationsabschnitten anderer Produkte keine Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8c80-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="e8c80-158">WCF-Dienste werden definiert, der `services` Abschnitt der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e8c80-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e8c80-159">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e8c80-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="e8c80-160">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="e8c80-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="e8c80-161">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e8c80-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="e8c80-162">Es wird lediglich das `name`-Attribut eines Diensts benötigt.</span><span class="sxs-lookup"><span data-stu-id="e8c80-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="e8c80-163">Standardmäßig beschreibt ein Dienstname den zugrunde liegenden CLR-Typ, der für die Implementierung eines Diensts verwendet wird. Sie können jedoch die ConfigurationName-Eigenschaft eines <xref:System.ServiceModel.ServiceContractAttribute> ändern, um die CLR-Typanforderung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e8c80-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="e8c80-164">Das `behaviorConfiguration`-Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8c80-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="e8c80-165">Es identifiziert das von einem Dienst verwendete Dienstverhalten.</span><span class="sxs-lookup"><span data-stu-id="e8c80-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="e8c80-166">Das von diesem Attribut angegebene Verhalten muss mit einem Dienstverhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei (das heißt derselben Datei oder einer übergeordneten Datei) verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="e8c80-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="e8c80-167">Jeder Dienst macht einen oder mehrere in einem `endpoint`-Element definierte Endpunkte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8c80-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="e8c80-168">Jeder Endpunkt hat eine eigene Adresse und eine eigene Bindung.</span><span class="sxs-lookup"><span data-stu-id="e8c80-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="e8c80-169">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="e8c80-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="e8c80-170">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e8c80-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="e8c80-171">Das `binding`-Attribut definiert, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e8c80-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="e8c80-172">Das `bindingConfiguration`-Attribut legt fest, welche konfigurierte Bindung innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8c80-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="e8c80-173">Ein Bindungsabschnitt kann verschiedene konfigurierte Bindungen definieren.</span><span class="sxs-lookup"><span data-stu-id="e8c80-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8c80-174">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8c80-174">Example</span></span>  
 <span data-ttu-id="e8c80-175">Hier sehen Sie ein Beispiel einer WCF-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e8c80-175">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e8c80-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8c80-176">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
