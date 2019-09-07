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
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399442"
---
# <a name="systemservicemodel"></a><span data-ttu-id="e0da8-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e0da8-102">\<system.serviceModel></span></span>
<span data-ttu-id="e0da8-103">Dieser Konfigurations Abschnitt enthält alle Service Model-Konfigurationselemente Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e0da8-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

<span data-ttu-id="e0da8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0da8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0da8-105">&nbsp;&nbsp; **\<System. Service Model->**</span><span class="sxs-lookup"><span data-stu-id="e0da8-105">&nbsp;&nbsp;**\<system.serviceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0da8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0da8-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0da8-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0da8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e0da8-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0da8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0da8-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0da8-109">Attributes</span></span>  
 <span data-ttu-id="e0da8-110">None</span><span class="sxs-lookup"><span data-stu-id="e0da8-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e0da8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0da8-111">Child Elements</span></span>  
  
|<span data-ttu-id="e0da8-112">Element</span><span class="sxs-lookup"><span data-stu-id="e0da8-112">Element</span></span>|<span data-ttu-id="e0da8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0da8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0da8-114">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e0da8-114">\<behaviors></span></span>](behaviors.md)|<span data-ttu-id="e0da8-115">In diesem Abschnitt werden zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors` definiert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-115">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e0da8-116">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="e0da8-116">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="e0da8-117">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-117">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="e0da8-118">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e0da8-118">\<bindings></span></span>](bindings.md)|<span data-ttu-id="e0da8-119">Dieser Abschnitt enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e0da8-119">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="e0da8-120">Jeder Eintrag wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-120">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="e0da8-121">Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e0da8-121">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="e0da8-122">\<client></span><span class="sxs-lookup"><span data-stu-id="e0da8-122">\<client></span></span>](client.md)|<span data-ttu-id="e0da8-123">Dieser Abschnitt enthält eine Liste mit Endpunkten, die ein Client für die Verbindungsherstellung mit einem Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0da8-123">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="e0da8-124">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e0da8-124">\<comContracts></span></span>](comcontracts.md)|<span data-ttu-id="e0da8-125">Dieser Abschnitt definiert für WCF und COM-Interop aktivierte COM-Verträge.</span><span class="sxs-lookup"><span data-stu-id="e0da8-125">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="e0da8-126">\<commonverhaltensweisen ></span><span class="sxs-lookup"><span data-stu-id="e0da8-126">\<commonBehaviors></span></span>](commonbehaviors.md)|<span data-ttu-id="e0da8-127">Dieser Abschnitt kann nur in der Datei machine.config definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e0da8-127">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="e0da8-128">Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="e0da8-128">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e0da8-129">Jede Auflistung definiert Verhaltenselemente, die von allen WCF-Endpunkten und-Diensten auf dem Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0da8-129">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="e0da8-130">Wenn ein Verhalten sowohl `<commonBehaviors>` in-als auch in- `<behaviors>` Abschnitten definiert ist \<, wird das Verhalten im > Abschnitt Verhalten bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="e0da8-130">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="e0da8-131">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="e0da8-131">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="e0da8-132">Dieser Abschnitt enthält Einstellungen für die Diagnosefunktionen von WCF.</span><span class="sxs-lookup"><span data-stu-id="e0da8-132">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="e0da8-133">Der Benutzer kann Ablaufverfolgung, Leistungsindikatoren und den WMI-Anbieter aktivieren/deaktivieren und benutzerdefinierte Meldungsfilter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e0da8-133">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="e0da8-134">\<Erweiterungen ></span><span class="sxs-lookup"><span data-stu-id="e0da8-134">\<extensions></span></span>](extensions-section.md)|<span data-ttu-id="e0da8-135">Dieser Abschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte von Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e0da8-135">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="e0da8-136">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="e0da8-136">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="e0da8-137">In diesem Abschnitt wird ein Satz von Standardprotokoll Zuordnungen zwischen Transportprotokoll Schemas (z. b. http, net. TCP, net. Pipe usw.) und WCF-Bindungen definiert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-137">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="e0da8-138">\<routing></span><span class="sxs-lookup"><span data-stu-id="e0da8-138">\<routing></span></span>](routing.md)|<span data-ttu-id="e0da8-139">Dieser Abschnitt definiert einen Satz von Routing filtern, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="e0da8-139">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="e0da8-140">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="e0da8-140">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="e0da8-141">Dieser Abschnitt definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0da8-141">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="e0da8-142">Wenn dieser Abschnitt leer ist, wird der Standardtyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0da8-142">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="e0da8-143">\<services></span><span class="sxs-lookup"><span data-stu-id="e0da8-143">\<services></span></span>](services.md)|<span data-ttu-id="e0da8-144">Der Abschnitt enthält eine Auflistung von Diensten.</span><span class="sxs-lookup"><span data-stu-id="e0da8-144">The section contains a collection of services.</span></span> <span data-ttu-id="e0da8-145">Für jeden in der Assembly definierten Dienst enthält dieses Element ein `service`-Element mit den Einstellungen für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="e0da8-145">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="e0da8-146">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e0da8-146">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="e0da8-147">Dieser Abschnitt definiert eine Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt.</span><span class="sxs-lookup"><span data-stu-id="e0da8-147">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="e0da8-148">Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e0da8-148">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="e0da8-149">Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-149">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="e0da8-150">Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e0da8-150">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="e0da8-151">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e0da8-151">\<tracking></span></span>](tracking-of-wcf.md)|<span data-ttu-id="e0da8-152">In diesem Abschnitt werden die Überwachungs Einstellungen für einen Workflow Dienst definiert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-152">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e0da8-153">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0da8-153">Parent Elements</span></span>  
  
|<span data-ttu-id="e0da8-154">Element</span><span class="sxs-lookup"><span data-stu-id="e0da8-154">Element</span></span>|<span data-ttu-id="e0da8-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0da8-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0da8-156">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e0da8-156">\<configuration></span></span>|<span data-ttu-id="e0da8-157">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e0da8-157">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0da8-158">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0da8-158">Remarks</span></span>  
 <span data-ttu-id="e0da8-159">WCF fügt den Konfigurations Abschnitten anderer Produkte keine Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0da8-159">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="e0da8-160">WCF-Dienste werden im `services` -Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="e0da8-160">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e0da8-161">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e0da8-161">An assembly can contain any number of services.</span></span> <span data-ttu-id="e0da8-162">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="e0da8-162">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="e0da8-163">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e0da8-163">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="e0da8-164">Es wird lediglich das `name`-Attribut eines Diensts benötigt.</span><span class="sxs-lookup"><span data-stu-id="e0da8-164">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="e0da8-165">Standardmäßig beschreibt ein Dienstname den zugrunde liegenden CLR-Typ, der für die Implementierung eines Diensts verwendet wird. Sie können jedoch die ConfigurationName-Eigenschaft eines <xref:System.ServiceModel.ServiceContractAttribute> ändern, um die CLR-Typanforderung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e0da8-165">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="e0da8-166">Das `behaviorConfiguration`-Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="e0da8-166">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="e0da8-167">Es identifiziert das von einem Dienst verwendete Dienstverhalten.</span><span class="sxs-lookup"><span data-stu-id="e0da8-167">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="e0da8-168">Das von diesem Attribut angegebene Verhalten muss mit einem Dienstverhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei (das heißt derselben Datei oder einer übergeordneten Datei) verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="e0da8-168">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="e0da8-169">Jeder Dienst macht einen oder mehrere in einem `endpoint`-Element definierte Endpunkte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0da8-169">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="e0da8-170">Jeder Endpunkt hat eine eigene Adresse und eine eigene Bindung.</span><span class="sxs-lookup"><span data-stu-id="e0da8-170">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="e0da8-171">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="e0da8-171">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="e0da8-172">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e0da8-172">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="e0da8-173">Das `binding`-Attribut definiert, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0da8-173">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="e0da8-174">Das `bindingConfiguration`-Attribut legt fest, welche konfigurierte Bindung innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0da8-174">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="e0da8-175">Ein Bindungsabschnitt kann verschiedene konfigurierte Bindungen definieren.</span><span class="sxs-lookup"><span data-stu-id="e0da8-175">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0da8-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0da8-176">Example</span></span>  
 <span data-ttu-id="e0da8-177">Hier sehen Sie ein Beispiel einer WCF-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e0da8-177">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0da8-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0da8-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
