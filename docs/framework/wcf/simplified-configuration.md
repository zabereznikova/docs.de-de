---
title: Vereinfachte Konfiguration
description: Erfahren Sie mehr über die vereinfachte Konfiguration für WCF-Dienste. .NET Framework 4.6.1 bietet eine Möglichkeit, die Größe und Komplexität der Dienst Konfiguration zu reduzieren.
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 248fe05e5854dbbec1a66b046c4def3d11d30327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235947"
---
# <a name="simplified-configuration"></a><span data-ttu-id="24af8-104">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="24af8-104">Simplified Configuration</span></span>

<span data-ttu-id="24af8-105">Das Konfigurieren von Windows Communication Foundation (WCF)-Diensten kann eine komplexe Aufgabe sein.</span><span class="sxs-lookup"><span data-stu-id="24af8-105">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="24af8-106">Es gibt viele verschiedene Optionen, und es ist nicht immer einfach zu bestimmen, welche Einstellungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="24af8-106">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="24af8-107">Konfigurationsdateien erhöhen zwar die Flexibilität von WCF-Diensten, Sie sind jedoch auch die Quelle für viele schwer zu suchende Probleme.</span><span class="sxs-lookup"><span data-stu-id="24af8-107">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="24af8-108">behandelt diese Probleme und gibt Benutzern die Möglichkeit, den Umfang und die Komplexität der Dienstkonfiguration zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="24af8-108">addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="24af8-109">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="24af8-109">Simplified Configuration</span></span>  

 <span data-ttu-id="24af8-110">In den WCF-Dienst Konfigurationsdateien `system.serviceModel` enthält der Abschnitt <> ein <`service`>-Element für jeden gehosteten Dienst.</span><span class="sxs-lookup"><span data-stu-id="24af8-110">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="24af8-111">Das <`service`>-Element enthält eine Auflistung <`endpoint`> Elemente, die die für jeden Dienst verfügbar gemachten Endpunkte und optional einen Satz von Dienst Verhaltensweisen angeben.</span><span class="sxs-lookup"><span data-stu-id="24af8-111">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="24af8-112">Die <`endpoint`>-Elemente geben die Adresse, die Bindung und den Vertrag an, die vom Endpunkt verfügbar gemacht werden, und optional die Bindungs Konfiguration und das Endpunkt Verhalten.</span><span class="sxs-lookup"><span data-stu-id="24af8-112">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="24af8-113">Der `system.serviceModel` Abschnitt <> enthält auch ein <`behaviors`> Element, mit dem Sie Dienst-oder Endpunkt Verhaltensweisen angeben können.</span><span class="sxs-lookup"><span data-stu-id="24af8-113">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="24af8-114">Das folgende Beispiel zeigt den `system.serviceModel` Abschnitt <> einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="24af8-114">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="24af8-115">vereinfacht das Konfigurieren eines WCF-Dienstanbieter, indem die Anforderung für das <>-Element entfernt wird `service` .</span><span class="sxs-lookup"><span data-stu-id="24af8-115">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="24af8-116">Wenn Sie keine <`service`> Abschnitt hinzufügen oder Endpunkte in einem <`service`> Abschnitt hinzufügen und der Dienst keine Endpunkte Programm gesteuert definiert, wird dem Dienst automatisch ein Satz von Standard Endpunkten hinzugefügt, einer für jede Dienst Basisadresse und für jeden Vertrag, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="24af8-116">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="24af8-117">An jedem dieser Endpunkte entspricht die Endpunktadresse der Basisadresse, die Bindung wird anhand des Basisadressenschemas bestimmt, und der Vertrag ist der Vertrag, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="24af8-117">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="24af8-118">Wenn es nicht erforderlich ist, Endpunkte oder Dienstverhalten anzugeben oder Änderungen an den Bindungseinstellungen vorzunehmen, müssen Sie keine Dienstkonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="24af8-118">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="24af8-119">Wenn ein Dienst zwei Verträge implementiert und der Host sowohl HTTP- als auch TCP-Transporte zulässt, erstellt der Diensthost vier Standardendpunkte, einen für jeden Vertrag mit den einzelnen Transporten.</span><span class="sxs-lookup"><span data-stu-id="24af8-119">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="24af8-120">Um Standardendpunkte zu erstellen, muss der Diensthost wissen, welche Bindungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="24af8-120">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="24af8-121">Diese Einstellungen werden in einem <`protocolMappings`> Abschnitt innerhalb des Abschnitts <`system.serviceModel`> angegeben.</span><span class="sxs-lookup"><span data-stu-id="24af8-121">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="24af8-122">Der `protocolMappings` Abschnitt <> enthält eine Liste von Transportprotokoll Schemas, die Bindungs Typen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="24af8-122">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="24af8-123">Der Diensthost verwendet die übergebene Basisadresse, um die zu verwendende Bindung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="24af8-123">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="24af8-124">Im folgenden Beispiel wird das <`protocolMappings`>-Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="24af8-124">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="24af8-125">Das Ändern von Standardkonfigurationselementen, z. B. Bindungen oder Verhalten, wirkt sich möglicherweise auf Dienste aus, die auf niedrigeren Ebenen der Konfigurationshierarchie definiert sind, da sie eventuell diese Standardbindungen bzw. dieses Standardverhalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="24af8-125">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="24af8-126">Daher muss jede Person, die Standardbindungen und -verhalten ändert, berücksichtigen, dass sich diese Änderungen auf andere Dienste in der Hierarchie auswirken können.</span><span class="sxs-lookup"><span data-stu-id="24af8-126">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24af8-127">Unter Internetinformationsdienste (IIS) oder dem Windows-Prozessaktivierungsdienst (WAS) gehostete Dienste verwenden das virtuelle Verzeichnis als Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="24af8-127">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="24af8-128">Im vorherigen Beispiel verwendet ein Endpunkt mit einer Basisadresse, die mit dem Schema "http" beginnt, das <xref:System.ServiceModel.BasicHttpBinding>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="24af8-128">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="24af8-129">Ein Endpunkt mit einer Basisadresse, die mit dem Schema "net.tcp" beginnt, verwendet das <xref:System.ServiceModel.NetTcpBinding>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="24af8-129">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="24af8-130">Sie können Einstellungen in einer lokalen App.config- oder Web.config-Datei überschreiben.</span><span class="sxs-lookup"><span data-stu-id="24af8-130">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="24af8-131">Jedes Element innerhalb des `protocolMappings` Abschnitts <> muss ein Schema und eine Bindung angeben.</span><span class="sxs-lookup"><span data-stu-id="24af8-131">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="24af8-132">Optional kann ein-Attribut angegeben werden `bindingConfiguration` , das eine Bindungs Konfiguration im `bindings` Abschnitt <> der Konfigurationsdatei angibt.</span><span class="sxs-lookup"><span data-stu-id="24af8-132">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="24af8-133">Wenn keine `bindingConfiguration` angegeben wird, wird die anonyme Bindungskonfiguration des entsprechenden Bindungstyps verwendet.</span><span class="sxs-lookup"><span data-stu-id="24af8-133">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="24af8-134">Dienst Verhaltensweisen werden für die Standard Endpunkte konfiguriert, indem anonyme <`behavior`> Abschnitte innerhalb <`serviceBehaviors`> Abschnitte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24af8-134">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="24af8-135">Alle unbenannten <`behavior`> Elemente innerhalb <`serviceBehaviors`> werden verwendet, um Dienst Verhaltensweisen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24af8-135">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="24af8-136">Die folgende Konfigurationsdatei ermöglicht z. B. die Veröffentlichung von Dienstmetadaten für alle Dienste innerhalb des Hosts.</span><span class="sxs-lookup"><span data-stu-id="24af8-136">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="24af8-137">Endpunkt Verhaltensweisen werden mithilfe anonymer <`behavior`> Abschnitte innerhalb <`serviceBehaviors`> Abschnitte konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="24af8-137">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="24af8-138">Das folgende Beispiel zeigt eine Konfigurationsdatei, die der Datei am Anfang dieses Themas ähnelt, in der das vereinfachte Konfigurationsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="24af8-138">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> <span data-ttu-id="24af8-139">Diese Funktion ist nur für die WCF-Dienstkonfiguration, nicht für die Clientkonfiguration relevant.</span><span class="sxs-lookup"><span data-stu-id="24af8-139">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="24af8-140">WCF-Clientkonfigurationen werden meistens von einem Tool, z. B. svcutil.exe, oder durch Hinzufügen eines Dienstverweises aus Visual Studio generiert.</span><span class="sxs-lookup"><span data-stu-id="24af8-140">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="24af8-141">Wenn Sie einen WCF-Client manuell konfigurieren, müssen Sie \<client> der Konfiguration ein-Element hinzufügen und alle Endpunkte angeben, die Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="24af8-141">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24af8-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24af8-142">See also</span></span>

- [<span data-ttu-id="24af8-143">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="24af8-143">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="24af8-144">Konfigurieren von Bindungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="24af8-144">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="24af8-145">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="24af8-145">Configuring System-Provided Bindings</span></span>](./feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="24af8-146">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="24af8-146">Configuring Services</span></span>](configuring-services.md)
- [<span data-ttu-id="24af8-147">Konfigurieren von WCF-Diensten</span><span class="sxs-lookup"><span data-stu-id="24af8-147">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="24af8-148">Konfigurieren von WCF-Diensten in Code</span><span class="sxs-lookup"><span data-stu-id="24af8-148">Configuring WCF Services in Code</span></span>](configuring-wcf-services-in-code.md)
