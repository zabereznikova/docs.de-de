---
title: Konfigurieren von Bindungen für Windows Communication Foundation-Dienste
description: Erfahren Sie, wie Sie Bindungen zum Zeitpunkt der Bereitstellung für eine WCF-Anwendung konfigurieren, indem Sie Elemente im System bearbeiten. Service Model-Element.
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: 60ab04764851ef82a43d5c2050d3bac7b56ce551
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266726"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a><span data-ttu-id="f62a8-103">Konfigurieren von Bindungen für Windows Communication Foundation-Dienste</span><span class="sxs-lookup"><span data-stu-id="f62a8-103">Configuring Bindings for Windows Communication Foundation Services</span></span>

<span data-ttu-id="f62a8-104">Beim Erstellen einer Anwendung möchten Sie dem Administrator nach Bereitstellung der Anwendung möglicherweise Entscheidungen mitteilen.</span><span class="sxs-lookup"><span data-stu-id="f62a8-104">When creating an application, you often want to defer decisions to the administrator after the deployment of the application.</span></span> <span data-ttu-id="f62a8-105">Beispielsweise wissen Sie häufig nicht im Voraus, welche Dienstadresse oder welcher URI (Uniform Resource Identifier) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f62a8-105">For example, there is often no way of knowing in advance what a service address, or Uniform Resource Identifier (URI), will be.</span></span> <span data-ttu-id="f62a8-106">Anstatt eine Adresse fest zu programmieren, sollte diese Aufgabe einem Administrator nach dem Erstellen eines Diensts übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-106">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="f62a8-107">Diese Flexibilität wird durch Konfiguration ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f62a8-107">This flexibility is accomplished through configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f62a8-108">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) mit dem- `/config` Schalter, um schnell Konfigurationsdateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f62a8-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config` switch to quickly create configuration files.</span></span>  
  
## <a name="major-sections"></a><span data-ttu-id="f62a8-109">Hauptabschnitte</span><span class="sxs-lookup"><span data-stu-id="f62a8-109">Major Sections</span></span>  

 <span data-ttu-id="f62a8-110">Das Konfigurations Schema Windows Communication Foundation (WCF) umfasst die folgenden drei Hauptabschnitte ( `serviceModel` , `bindings` und `services` ):</span><span class="sxs-lookup"><span data-stu-id="f62a8-110">The Windows Communication Foundation (WCF) configuration scheme includes the following three major sections (`serviceModel`, `bindings`, and `services`):</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a><span data-ttu-id="f62a8-111">ServiceModel-Elemente</span><span class="sxs-lookup"><span data-stu-id="f62a8-111">ServiceModel Elements</span></span>  

 <span data-ttu-id="f62a8-112">Sie können den Abschnitt, der durch das-Element begrenzt ist, verwenden, `system.ServiceModel` um einen Diensttyp mit einem oder mehreren Endpunkten und Einstellungen für einen Dienst zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f62a8-112">You can use the section bounded by the `system.ServiceModel` element to configure a service type with one or more endpoints, as well as settings for a service.</span></span> <span data-ttu-id="f62a8-113">Jeder Endpunkt kann dann mit einer Adresse, einem Vertrag und einer Bindung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-113">Each endpoint can then be configured with an address, a contract, and a binding.</span></span> <span data-ttu-id="f62a8-114">Weitere Informationen zu Endpunkten finden Sie unter [Übersicht über die Endpunkt Erstellung](endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f62a8-114">For more information about endpoints, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="f62a8-115">Wenn Sie keine Endpunkte angeben, werden von der Runtime automatisch Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f62a8-115">If no endpoints are specified, the runtime adds default endpoints.</span></span> <span data-ttu-id="f62a8-116">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f62a8-116">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="f62a8-117">Eine Bindung gibt Transporte (HTTP, TCP, Pipes und Message Queuing) sowie Protokolle (Sicherheit, Verlässlichkeit, Transaktionsflüsse) an und besteht aus Bindungselementen, von denen jedes einen Aspekt der Kommunikation eines Endpunkts mit der Welt angibt.</span><span class="sxs-lookup"><span data-stu-id="f62a8-117">A binding specifies transports (HTTP, TCP, pipes, Message Queuing) and protocols (Security, Reliability, Transaction flows) and consists of binding elements, each of which specifies an aspect of how an endpoint communicates with the world.</span></span>  
  
 <span data-ttu-id="f62a8-118">Wenn Sie das-Element angeben, wird beispielsweise angegeben, dass [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) http als Transport für einen Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f62a8-118">For example, specifying the [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) element indicates to use HTTP as the transport for an endpoint.</span></span> <span data-ttu-id="f62a8-119">Auf diese Weise wird der Endpunkt zur Laufzeit aktiviert, wenn der Dienst, der diesen Endpunkt verwendet, geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f62a8-119">This is used to wire up the endpoint at run time when the service using this endpoint is opened.</span></span>  
  
 <span data-ttu-id="f62a8-120">Es gibt zwei Arten von Bindungen: vordefinierte und benutzerdefinierte.</span><span class="sxs-lookup"><span data-stu-id="f62a8-120">There are two kinds of bindings: predefined and custom.</span></span> <span data-ttu-id="f62a8-121">Vordefinierte Bindungen enthalten nützliche Kombinationen von Elementen, die in allgemeinen Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-121">Predefined bindings contain useful combinations of elements that are used in common scenarios.</span></span> <span data-ttu-id="f62a8-122">Eine Liste der vordefinierten Bindungs Typen, die von WCF bereitgestellt werden, finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="f62a8-122">For a list of predefined binding types that WCF provides, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="f62a8-123">Wenn keine vordefinierte Bindungsauflistung über die korrekte Kombination von Funktionen verfügt, die eine Dienstanwendung benötigt, können Sie benutzerdefinierte Bindungen erstellen, um den Anforderungen der Anwendung zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f62a8-123">If no predefined binding collection has the correct combination of features that a service application needs, you can construct custom bindings to meet the application's requirements.</span></span> <span data-ttu-id="f62a8-124">Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f62a8-124">For more information about custom bindings, see [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
 <span data-ttu-id="f62a8-125">Die folgenden vier Beispiele veranschaulichen die gängigsten Bindungs Konfigurationen, die zum Einrichten eines WCF-Dienstanbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-125">The following four examples illustrate the most common binding configurations used for setting up a WCF service.</span></span>  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a><span data-ttu-id="f62a8-126">Angeben eines Endpunkts, um einen Bindungstyp zu verwenden</span><span class="sxs-lookup"><span data-stu-id="f62a8-126">Specifying an Endpoint to Use a Binding Type</span></span>  

 <span data-ttu-id="f62a8-127">Das erste Beispiel zeigt, wie ein Endpunkt angegeben wird, der mit einer Adresse, einem Vertrag oder einer Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f62a8-127">The first example illustrates how to specify an endpoint configured with an address, a contract, and a binding.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 <span data-ttu-id="f62a8-128">In diesem Beispiel gibt das `name`-Attribut an, für welchen Diensttyp die Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f62a8-128">In this example, the `name` attribute indicates which service type the configuration is for.</span></span> <span data-ttu-id="f62a8-129">Wenn Sie in Ihrem Code einen Dienst mit dem `HelloWorld`-Vertrag erstellen, wird er mit allen in der Beispielkonfiguration definierten Endpunkten initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f62a8-129">When you create a service in your code with the `HelloWorld` contract, it is initialized with all of the endpoints defined in the example configuration.</span></span> <span data-ttu-id="f62a8-130">Wenn die Assembly nur einen Dienstvertrag implementiert, `name` kann das Attribut weggelassen werden, da der Dienst den einzigen verfügbaren Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="f62a8-130">If the assembly implements only one service contract, the `name` attribute can be omitted because the service uses the only available type.</span></span> <span data-ttu-id="f62a8-131">Das Attribut nimmt eine Zeichenfolge, die im Format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null` vorliegen muss</span><span class="sxs-lookup"><span data-stu-id="f62a8-131">The attribute takes a string, which must be in the format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>  
  
 <span data-ttu-id="f62a8-132">Das `address`-Attribut gibt den URI an, den andere Endpunkte für die Kommunikation mit dem Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-132">The `address` attribute specifies the URI that other endpoints use to communicate to the service.</span></span> <span data-ttu-id="f62a8-133">Der URI kann entweder ein absoluter oder relativer Pfad sein.</span><span class="sxs-lookup"><span data-stu-id="f62a8-133">The URI can be either an absolute or relative path.</span></span> <span data-ttu-id="f62a8-134">Bei Bereitstellung einer relativen Adresse wird vom Host erwartet, dass er eine Basisadresse bereitstellt, die für das in der Bindung verwendete Transportschema geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f62a8-134">If a relative address is provided, the host is expected to provide a base address that is appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="f62a8-135">Wenn keine Adresse konfiguriert wird, wird angenommen, dass die Basisadresse der Adresse für diesen Endpunkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="f62a8-135">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span>  
  
 <span data-ttu-id="f62a8-136">Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f62a8-136">The `contract` attribute specifies the contract this endpoint is exposing.</span></span> <span data-ttu-id="f62a8-137">Der Dienstimplementierungstyp muss den Vertragstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="f62a8-137">The service implementation type must implement the contract type.</span></span> <span data-ttu-id="f62a8-138">Wenn eine Dienstimplementierung einen einzelnen Vertragstyp implementiert, kann diese Eigenschaft ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span>  
  
 <span data-ttu-id="f62a8-139">Das `binding`-Attribut wählt eine vordefinierte oder benutzerdefinierte Bindung aus, die für diesen speziellen Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f62a8-139">The `binding` attribute selects a predefined or custom binding to use for this specific endpoint.</span></span> <span data-ttu-id="f62a8-140">Ein Endpunkt, der eine Bindung nicht explizit auswählt, verwendet die standardmäßige Bindungsauswahl `BasicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="f62a8-140">An endpoint that does not explicitly select a binding uses the default binding selection, which is `BasicHttpBinding`.</span></span>  
  
#### <a name="modifying-a-predefined-binding"></a><span data-ttu-id="f62a8-141">Ändern einer vordefinierten Bindung</span><span class="sxs-lookup"><span data-stu-id="f62a8-141">Modifying a Predefined Binding</span></span>  

 <span data-ttu-id="f62a8-142">Im folgenden Beispiel wird eine vordefinierte Bindung geändert.</span><span class="sxs-lookup"><span data-stu-id="f62a8-142">In the following example, a predefined binding is modified.</span></span> <span data-ttu-id="f62a8-143">Sie kann anschließend verwendet werden, um einen beliebigen Endpunkt im Dienst zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f62a8-143">It can then be used to configure any endpoint in the service.</span></span> <span data-ttu-id="f62a8-144">Die Bindung wird geändert, indem der <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A>-Wert auf 1 Sekunde festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f62a8-144">The binding is modified by setting the <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> value to 1 second.</span></span> <span data-ttu-id="f62a8-145">Beachten Sie, dass die Eigenschaft ein <xref:System.TimeSpan>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f62a8-145">Note that the property returns a <xref:System.TimeSpan> object.</span></span>  
  
 <span data-ttu-id="f62a8-146">Diese geänderte Bindung finden Sie im Bindungsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="f62a8-146">That altered binding is found in the bindings section.</span></span> <span data-ttu-id="f62a8-147">Sie kann jetzt beim Erstellen von Endpunkten durch Festlegen des `binding`-Attributs im `endpoint`-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f62a8-147">This altered binding can now be used when creating any endpoint by setting the `binding` attribute in the `endpoint` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f62a8-148">Wenn Sie der Bindung einen besonderen Namen geben, muss die im Dienstendpunkt angegebene `bindingConfiguration` diesem Namen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f62a8-148">If you give a particular name to the binding, the `bindingConfiguration` specified in the service endpoint must match with it.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a><span data-ttu-id="f62a8-149">Konfigurieren eines Verhaltens für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="f62a8-149">Configuring a Behavior to Apply to a Service</span></span>  

 <span data-ttu-id="f62a8-150">Im folgenden Beispiel wird ein bestimmtes Verhalten für den Diensttyp konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f62a8-150">In the following example, a specific behavior is configured for the service type.</span></span> <span data-ttu-id="f62a8-151">Das- `ServiceMetadataBehavior` Element wird verwendet, um das Service [Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) zu aktivieren, um den Dienst abzufragen und Web Services Description Language (WSDL)-Dokumente aus den Metadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f62a8-151">The `ServiceMetadataBehavior` element is used to enable the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to query the service and generate Web Services Description Language (WSDL) documents from the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f62a8-152">Wenn Sie dem Verhalten einen besonderen Namen geben, muss die im Dienst- oder Endpunktabschnitt angegebene `behaviorConfiguration` diesem Namen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f62a8-152">If you give a particular name to the behavior, the `behaviorConfiguration` specified in the service or endpoint section must match it.</span></span>  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />
    </behavior>  
</behaviors>  
<services>  
    <service
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 <span data-ttu-id="f62a8-153">Die vorangehende Konfiguration ermöglicht einem Client, den "HelloWorld"-Dienst aufzurufen und die Metadaten des Diensts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f62a8-153">The preceding configuration enables a client to call and get the metadata of the "HelloWorld" typed service.</span></span>  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a><span data-ttu-id="f62a8-154">Angeben eines Diensts mit zwei Endpunkten mithilfe unterschiedlicher Bindungswerte</span><span class="sxs-lookup"><span data-stu-id="f62a8-154">Specifying a Service with Two Endpoints Using Different Binding Values</span></span>  

 <span data-ttu-id="f62a8-155">In diesem letzten Beispiel werden zwei Endpunkte für den `HelloWorld`-Diensttyp konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f62a8-155">In this last example, two endpoints are configured for the `HelloWorld` service type.</span></span> <span data-ttu-id="f62a8-156">Jeder Endpunkt verwendet ein anderes angepasstes  `bindingConfiguration` Attribut desselben Bindungs Typs (jedes ändert die `basicHttpBinding` ).</span><span class="sxs-lookup"><span data-stu-id="f62a8-156">Each endpoint uses a different customized  `bindingConfiguration` attribute of the same binding type (each modifies the `basicHttpBinding`).</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="f62a8-157">Sie können dasselbe Verhalten mit der Konfiguration erzielen, indem Sie einen `protocolMapping`-Abschnitt hinzufügen und die Bindungen konfigurieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f62a8-157">You can get the same behavior using the default configuration by adding a `protocolMapping` section and configuring the bindings as demonstrated in the following example.</span></span>  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f62a8-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f62a8-158">See also</span></span>

- [<span data-ttu-id="f62a8-159">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f62a8-159">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="f62a8-160">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f62a8-160">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [<span data-ttu-id="f62a8-161">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="f62a8-161">Endpoint Creation Overview</span></span>](endpoint-creation-overview.md)
- [<span data-ttu-id="f62a8-162">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="f62a8-162">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
