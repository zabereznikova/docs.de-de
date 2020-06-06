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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399442"
---
# \<system.serviceModel>
<span data-ttu-id="75f5c-102">Dieser Konfigurations Abschnitt enthält alle Service Model-Konfigurationselemente Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="75f5c-102">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="75f5c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="75f5c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75f5c-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75f5c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="75f5c-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75f5c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75f5c-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="75f5c-106">Attributes</span></span>  
 <span data-ttu-id="75f5c-107">Keine</span><span class="sxs-lookup"><span data-stu-id="75f5c-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75f5c-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75f5c-108">Child Elements</span></span>  
  
|<span data-ttu-id="75f5c-109">Element</span><span class="sxs-lookup"><span data-stu-id="75f5c-109">Element</span></span>|<span data-ttu-id="75f5c-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75f5c-110">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|<span data-ttu-id="75f5c-111">In diesem Abschnitt werden zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors` definiert.</span><span class="sxs-lookup"><span data-stu-id="75f5c-111">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="75f5c-112">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="75f5c-112">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="75f5c-113">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="75f5c-113">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[\<bindings>](bindings.md)|<span data-ttu-id="75f5c-114">Dieser Abschnitt enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="75f5c-114">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="75f5c-115">Jeder Eintrag wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="75f5c-115">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="75f5c-116">Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="75f5c-116">Services use bindings by linking them using the `name`.</span></span>|  
|[\<client>](client.md)|<span data-ttu-id="75f5c-117">Dieser Abschnitt enthält eine Liste mit Endpunkten, die ein Client für die Verbindungsherstellung mit einem Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="75f5c-117">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[\<comContracts>](comcontracts.md)|<span data-ttu-id="75f5c-118">Dieser Abschnitt definiert für WCF und COM-Interop aktivierte COM-Verträge.</span><span class="sxs-lookup"><span data-stu-id="75f5c-118">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[\<commonBehaviors>](commonbehaviors.md)|<span data-ttu-id="75f5c-119">Dieser Abschnitt kann nur in der Datei machine.config definiert werden.</span><span class="sxs-lookup"><span data-stu-id="75f5c-119">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="75f5c-120">Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="75f5c-120">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="75f5c-121">Jede Auflistung definiert Verhaltenselemente, die von allen WCF-Endpunkten und-Diensten auf dem Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75f5c-121">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="75f5c-122">Wenn ein Verhalten im `<commonBehaviors>`-Abschnitt und im `<behaviors>`-Abschnitt definiert ist, wird dem Verhalten im \<behaviors>-Abschnitt Priorität eingeräumt.</span><span class="sxs-lookup"><span data-stu-id="75f5c-122">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="75f5c-123">Dieser Abschnitt enthält Einstellungen für die Diagnosefunktionen von WCF.</span><span class="sxs-lookup"><span data-stu-id="75f5c-123">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="75f5c-124">Der Benutzer kann Ablaufverfolgung, Leistungsindikatoren und den WMI-Anbieter aktivieren/deaktivieren und benutzerdefinierte Meldungsfilter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75f5c-124">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[\<extensions>](extensions-section.md)|<span data-ttu-id="75f5c-125">Dieser Abschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte von Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="75f5c-125">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="75f5c-126">Dieser Abschnitt definiert einen Satz von Standardprotokollzuordnungen zwischen Transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen.</span><span class="sxs-lookup"><span data-stu-id="75f5c-126">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[\<routing>](routing.md)|<span data-ttu-id="75f5c-127">Dieser Abschnitt definiert einen Satz von Routing filtern, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="75f5c-127">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="75f5c-128">Dieser Abschnitt definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="75f5c-128">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="75f5c-129">Wenn dieser Abschnitt leer ist, wird der Standardtyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="75f5c-129">If this section is empty, the default type is used.</span></span>|  
|[\<services>](services.md)|<span data-ttu-id="75f5c-130">Der Abschnitt enthält eine Auflistung von Diensten.</span><span class="sxs-lookup"><span data-stu-id="75f5c-130">The section contains a collection of services.</span></span> <span data-ttu-id="75f5c-131">Für jeden in der Assembly definierten Dienst enthält dieses Element ein `service`-Element mit den Einstellungen für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="75f5c-131">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="75f5c-132">Dieser Abschnitt definiert eine Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt.</span><span class="sxs-lookup"><span data-stu-id="75f5c-132">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="75f5c-133">Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75f5c-133">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="75f5c-134">Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert.</span><span class="sxs-lookup"><span data-stu-id="75f5c-134">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="75f5c-135">Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.</span><span class="sxs-lookup"><span data-stu-id="75f5c-135">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[\<tracking>](tracking-of-wcf.md)|<span data-ttu-id="75f5c-136">In diesem Abschnitt werden die Überwachungs Einstellungen für einen Workflow Dienst definiert.</span><span class="sxs-lookup"><span data-stu-id="75f5c-136">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="75f5c-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75f5c-137">Parent Elements</span></span>  
  
|<span data-ttu-id="75f5c-138">Element</span><span class="sxs-lookup"><span data-stu-id="75f5c-138">Element</span></span>|<span data-ttu-id="75f5c-139">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75f5c-139">Description</span></span>|  
|-------------|-----------------|  
|\<configuration>|<span data-ttu-id="75f5c-140">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="75f5c-140">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75f5c-141">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="75f5c-141">Remarks</span></span>  
 <span data-ttu-id="75f5c-142">WCF fügt den Konfigurations Abschnitten anderer Produkte keine Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="75f5c-142">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="75f5c-143">WCF-Dienste werden im- `services` Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="75f5c-143">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="75f5c-144">Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="75f5c-144">An assembly can contain any number of services.</span></span> <span data-ttu-id="75f5c-145">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="75f5c-145">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="75f5c-146">Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="75f5c-146">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="75f5c-147">Es wird lediglich das `name`-Attribut eines Diensts benötigt.</span><span class="sxs-lookup"><span data-stu-id="75f5c-147">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="75f5c-148">Standardmäßig beschreibt ein Dienstname den zugrunde liegenden CLR-Typ, der für die Implementierung eines Diensts verwendet wird. Sie können jedoch die ConfigurationName-Eigenschaft eines <xref:System.ServiceModel.ServiceContractAttribute> ändern, um die CLR-Typanforderung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="75f5c-148">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="75f5c-149">Das `behaviorConfiguration`-Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="75f5c-149">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="75f5c-150">Es identifiziert das von einem Dienst verwendete Dienstverhalten.</span><span class="sxs-lookup"><span data-stu-id="75f5c-150">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="75f5c-151">Das von diesem Attribut angegebene Verhalten muss mit einem Dienstverhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei (das heißt derselben Datei oder einer übergeordneten Datei) verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="75f5c-151">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="75f5c-152">Jeder Dienst macht einen oder mehrere in einem `endpoint`-Element definierte Endpunkte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75f5c-152">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="75f5c-153">Jeder Endpunkt hat eine eigene Adresse und eine eigene Bindung.</span><span class="sxs-lookup"><span data-stu-id="75f5c-153">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="75f5c-154">Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.</span><span class="sxs-lookup"><span data-stu-id="75f5c-154">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="75f5c-155">Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="75f5c-155">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="75f5c-156">Das `binding`-Attribut definiert, in welchem Abschnitt die Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="75f5c-156">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="75f5c-157">Das `bindingConfiguration`-Attribut legt fest, welche konfigurierte Bindung innerhalb des Bindungsabschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75f5c-157">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="75f5c-158">Ein Bindungsabschnitt kann verschiedene konfigurierte Bindungen definieren.</span><span class="sxs-lookup"><span data-stu-id="75f5c-158">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75f5c-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75f5c-159">Example</span></span>  
 <span data-ttu-id="75f5c-160">Hier sehen Sie ein Beispiel einer WCF-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="75f5c-160">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75f5c-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75f5c-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
