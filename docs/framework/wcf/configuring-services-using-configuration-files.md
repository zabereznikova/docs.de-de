---
title: Konfigurieren von Diensten mit Konfigurationsdateien
description: Erfahren Sie, wie eine Konfigurationsdatei für einen WCF-Dienst Ihnen die Flexibilität bietet, während der Bereitstellung Endpunkt-und Dienst Verhaltensdaten bereitzustellen.
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: 25a6891564054878e7bdf7f43d431547ea1dee6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253348"
---
# <a name="configuring-services-using-configuration-files"></a><span data-ttu-id="908be-103">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="908be-103">Configuring Services Using Configuration Files</span></span>

<span data-ttu-id="908be-104">Wenn Sie einen Windows Communication Foundation (WCF)-Dienst mit einer Konfigurationsdatei konfigurieren, haben Sie die Flexibilität, Endpunkt-und Dienst Verhaltensdaten zum Zeitpunkt der Bereitstellung statt zur Entwurfszeit bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="908be-104">Configuring a Windows Communication Foundation (WCF) service with a configuration file gives you the flexibility of providing endpoint and service behavior data at the point of deployment instead of at design time.</span></span> <span data-ttu-id="908be-105">Dieses Thema beschreibt die dafür verfügbaren grundlegenden Verfahren.</span><span class="sxs-lookup"><span data-stu-id="908be-105">This topic outlines the primary techniques available.</span></span>  
  
 <span data-ttu-id="908be-106">Ein WCF-Dienst kann mit der .NET Framework-Konfigurations Technologie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="908be-106">A WCF service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="908be-107">In den meisten Fällen werden der Web.config Datei für eine Internetinformationsdienste (IIS)-Website, die einen WCF-Dienst hostet, XML-Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="908be-107">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="908be-108">Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen für die Kommunikation mit dem Dienst verwendeten Adressen) für einzelne Computer.</span><span class="sxs-lookup"><span data-stu-id="908be-108">The elements allow you to change details such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span> <span data-ttu-id="908be-109">Außerdem umfasst WCF mehrere vom System bereitgestellte Elemente, mit denen Sie schnell die grundlegendsten Features für einen Dienst auswählen können.</span><span class="sxs-lookup"><span data-stu-id="908be-109">In addition, WCF includes several system-provided elements that allow you to quickly select the most basic features for a service.</span></span> <span data-ttu-id="908be-110">Ab .NET Framework 4 enthält WCF ein neues Standard Konfigurations Modell, das die WCF-Konfigurations Anforderungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="908be-110">Starting with .NET Framework 4, WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="908be-111">Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime den Dienst automatisch mit einigen Standard Endpunkten und der Standard Bindung/dem Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="908be-111">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with some standard endpoints and default binding/behavior.</span></span> <span data-ttu-id="908be-112">In der Praxis ist das Schreiben von Konfigurationen ein wesentlicher Bestandteil der Programmierung von WCF-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="908be-112">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
 <span data-ttu-id="908be-113">Weitere Informationen finden Sie unter [Konfigurieren von Bindungen für Dienste](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="908be-113">For more information, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span> <span data-ttu-id="908be-114">Eine Liste der am häufigsten verwendeten Elemente finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="908be-114">For a list of the most commonly used elements, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="908be-115">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="908be-115">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="908be-116">Beim Bereitstellen paralleler Szenarien, in denen zwei verschiedene Versionen eines Diensts bereitgestellt werden, müssen bei Verweisen in Konfigurationsdateien partielle Assemblynamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="908be-116">When deploying side by side scenarios where two different versions of a service are deployed, it is necessary to specify partial names of assemblies referenced in configuration files.</span></span> <span data-ttu-id="908be-117">Dies liegt daran, dass die Konfigurationsdatei gemeinsam von allen Versionen eines Diensts verwendet wird und dass diese Dienste ggf. unter unterschiedlichen Versionen von .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="908be-117">This is because the configuration file is shared across all versions of a service and they could be running under different versions of the .NET Framework.</span></span>  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a><span data-ttu-id="908be-118">System.Configuration: Web.config und App.config</span><span class="sxs-lookup"><span data-stu-id="908be-118">System.Configuration: Web.config and App.config</span></span>  

 <span data-ttu-id="908be-119">WCF verwendet das System.Configurationskonfigurations-System des .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="908be-119">WCF uses the System.Configuration configuration system of the .NET Framework.</span></span>  
  
 <span data-ttu-id="908be-120">Wenn Sie einen Dienst in Visual Studio konfigurieren, verwenden Sie entweder eine Web.config Datei oder eine App.config Datei, um die Einstellungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="908be-120">When configuring a service in Visual Studio, use either a Web.config file or an App.config file to specify the settings.</span></span> <span data-ttu-id="908be-121">Die Wahl der Konfigurationsdatei wird durch die Hostumgebung des Diensts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="908be-121">The choice of the configuration file name is determined by the hosting environment you choose for the service.</span></span> <span data-ttu-id="908be-122">Wenn Sie den Dienst in IIS hosten, verwenden Sie eine Web.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="908be-122">If you are using IIS to host your service, use a Web.config file.</span></span> <span data-ttu-id="908be-123">Bei einer anderen Hostumgebung verwenden Sie eine App.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="908be-123">If you are using any other hosting environment, use an App.config file.</span></span>  
  
 <span data-ttu-id="908be-124">In Visual Studio wird die Datei mit dem Namen App.config zum Erstellen der endgültigen Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="908be-124">In Visual Studio, the file named App.config is used to create the final configuration file.</span></span> <span data-ttu-id="908be-125">Der tatsächlich für die Konfigurationsdatei verwendete Name hängt vom Assemblynamen ab.</span><span class="sxs-lookup"><span data-stu-id="908be-125">The final name actually used for the configuration depends on the assembly name.</span></span> <span data-ttu-id="908be-126">Einer Assembly mit dem Namen "Cohowinery.exe" ist beispielsweise die Konfigurationsdatei namens "Cohowinery.exe.config" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="908be-126">For example, an assembly named "Cohowinery.exe" has a final configuration file name of "Cohowinery.exe.config".</span></span> <span data-ttu-id="908be-127">Sie müssen jedoch nur die Datei App.config ändern.</span><span class="sxs-lookup"><span data-stu-id="908be-127">However, you only need to modify the App.config file.</span></span> <span data-ttu-id="908be-128">An dieser Datei vorgenommene Änderungen werden bei der Kompilierung automatisch an die tatsächliche Anwendungskonfigurationsdatei weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="908be-128">Changes made to that file are automatically made to the final application configuration file at compile time.</span></span>  
  
 <span data-ttu-id="908be-129">Bei Verwendung einer App.config-Datei führt das Konfigurationssystem den Inhalt dieser Datei mit dem Inhalt der Datei Machine.config zusammen, sobald die Anwendung gestartet und die Konfiguration übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="908be-129">In using an App.config, file the configuration system merges the App.config file with content of the Machine.config file when the application starts and the configuration is applied.</span></span> <span data-ttu-id="908be-130">Dieser Mechanismus ermöglicht es, computerweite Einstellungen in der Datei Machine.config zu definieren.</span><span class="sxs-lookup"><span data-stu-id="908be-130">This mechanism allows machine-wide settings to be defined in the Machine.config file.</span></span> <span data-ttu-id="908be-131">Die Datei App.config kann verwendet werden, um Einstellungen in der Datei Machine.config zu überschreiben. Sie können Einstellungen in der Datei Machine.config aber auch sperren, sodass diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="908be-131">The App.config file can be used to override the settings of the Machine.config file; you can also lock in the settings in Machine.config file so that they get used.</span></span> <span data-ttu-id="908be-132">Im Fall der Datei Web.config führt das Konfigurationssystem den Inhalt aller Web.config-Dateien in allen Verzeichnissen zur schließlich verwendeten Konfiguration im Anwendungsverzeichnis zusammen.</span><span class="sxs-lookup"><span data-stu-id="908be-132">In the Web.config case, the configuration system merges the Web.config files in all directories leading up to the application directory into the configuration that gets applied.</span></span> <span data-ttu-id="908be-133">Weitere Informationen zur Konfiguration und zu den Prioritäts Einstellungen finden Sie in den Themen im- <xref:System.Configuration> Namespace.</span><span class="sxs-lookup"><span data-stu-id="908be-133">For more information about configuration and the setting priorities, see topics in the <xref:System.Configuration> namespace.</span></span>  
  
## <a name="major-sections-of-the-configuration-file"></a><span data-ttu-id="908be-134">Hauptabschnitte der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="908be-134">Major Sections of the Configuration File</span></span>  

 <span data-ttu-id="908be-135">Die Hauptabschnitte der Konfigurationsdatei umfassen folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="908be-135">The main sections in the configuration file include the following elements.</span></span>  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!-- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
> <span data-ttu-id="908be-136">Die Bindungs- und Verhaltensabschnitte sind optional und nur bei Bedarf enthalten.</span><span class="sxs-lookup"><span data-stu-id="908be-136">The bindings and behaviors sections are optional and are only included if required.</span></span>  
  
### <a name="the-services-element"></a><span data-ttu-id="908be-137">Das \<services> Element</span><span class="sxs-lookup"><span data-stu-id="908be-137">The \<services> Element</span></span>  

 <span data-ttu-id="908be-138">Das `services` -Element enthält die Spezifikationen aller Dienste, die die Anwendung hostet.</span><span class="sxs-lookup"><span data-stu-id="908be-138">The `services` element contains the specifications for all services the application hosts.</span></span> <span data-ttu-id="908be-139">Ab dem vereinfachten Konfigurations Modell in .NET Framework 4 ist dieser Abschnitt optional.</span><span class="sxs-lookup"><span data-stu-id="908be-139">Starting with the simplified configuration model in .NET Framework 4, this section is optional.</span></span>  
  
 [\<services>](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a><span data-ttu-id="908be-140">Das \<service> Element</span><span class="sxs-lookup"><span data-stu-id="908be-140">The \<service> Element</span></span>  

 <span data-ttu-id="908be-141">Jeder Dienst verfügt über diese Attribute:</span><span class="sxs-lookup"><span data-stu-id="908be-141">Each service has these attributes:</span></span>  
  
- <span data-ttu-id="908be-142">`name`.</span><span class="sxs-lookup"><span data-stu-id="908be-142">`name`.</span></span> <span data-ttu-id="908be-143">Gibt den Typ an, der eine Implementierung eines Dienstvertrags bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="908be-143">Specifies the type that provides an implementation of a service contract.</span></span> <span data-ttu-id="908be-144">Dies ist ein vollqualifizierter Name, der aus dem Namespace und einem Punkt gefolgt von dem Typnamen besteht.</span><span class="sxs-lookup"><span data-stu-id="908be-144">This is a fully qualified name which consists of the namespace, a period, and then the type name.</span></span> <span data-ttu-id="908be-145">Beispiel: `"MyNameSpace.myServiceType"`.</span><span class="sxs-lookup"><span data-stu-id="908be-145">For example `"MyNameSpace.myServiceType"`.</span></span>  
  
- <span data-ttu-id="908be-146">`behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="908be-146">`behaviorConfiguration`.</span></span> <span data-ttu-id="908be-147">Gibt den Namen eines `behavior` -Elements an, das im `behaviors` -Element gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="908be-147">Specifies the name of one of the `behavior` elements found in the `behaviors` element.</span></span> <span data-ttu-id="908be-148">Das angegebene Verhalten steuert Aktionen, beispielsweise ob der Dienst Identitätswechsel erlaubt.</span><span class="sxs-lookup"><span data-stu-id="908be-148">The specified behavior governs actions such as whether the service allows impersonation.</span></span> <span data-ttu-id="908be-149">Wenn der Wert ein leerer Name oder kein `behaviorConfiguration` ist, wird dem Dienst der Standardsatz von Dienstverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="908be-149">If its value is the empty name or no `behaviorConfiguration` is provided then the default set of service behaviors is added to the service.</span></span>  
  
- [\<service>](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a><span data-ttu-id="908be-150">Das \<endpoint> Element</span><span class="sxs-lookup"><span data-stu-id="908be-150">The \<endpoint> Element</span></span>  

 <span data-ttu-id="908be-151">Jeder Endpunkt benötigt eine Adresse, eine Bindung und einen Vertrag. Diese Elemente werden durch die folgenden Attribute dargestellt:</span><span class="sxs-lookup"><span data-stu-id="908be-151">Each endpoint requires an address, a binding, and a contract, which are represented by the following attributes:</span></span>  
  
- <span data-ttu-id="908be-152">`address`.</span><span class="sxs-lookup"><span data-stu-id="908be-152">`address`.</span></span> <span data-ttu-id="908be-153">Gibt den Uniform Resource Identifier (URI) des Diensts an. Er kann als absolute Adresse oder als eine zur Basisadresse des Diensts relative Adresse angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="908be-153">Specifies the service's Uniform Resource Identifier (URI), which can be an absolute address or one that is given relative to the base address of the service.</span></span> <span data-ttu-id="908be-154">Eine leere Zeichenfolge zeigt an, dass der Endpunkt unter der Basisadresse verfügbar ist. Diese Basisadresse wird bei der Erstellung des <xref:System.ServiceModel.ServiceHost> für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="908be-154">If set to an empty string, it indicates that the endpoint is available at the base address that is specified when creating the <xref:System.ServiceModel.ServiceHost> for the service.</span></span>  
  
- <span data-ttu-id="908be-155">`binding`.</span><span class="sxs-lookup"><span data-stu-id="908be-155">`binding`.</span></span> <span data-ttu-id="908be-156">Gibt üblicherweise eine vom System bereitgestellte Bindung, beispielsweise <xref:System.ServiceModel.WSHttpBinding>an, kann aber auch eine benutzerdefinierte Bindung angeben.</span><span class="sxs-lookup"><span data-stu-id="908be-156">Typically specifies a system-provided binding like <xref:System.ServiceModel.WSHttpBinding>, but can also specify a user-defined binding.</span></span> <span data-ttu-id="908be-157">Die angegebene Bindung bestimmt, welcher Typ von Transport, Sicherheit und Codierung verwendet wird, und ob zuverlässige Sitzungen, Transaktionen oder Streaming unterstützt werden oder aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="908be-157">The binding specified determines the type of transport, security and encoding used, and whether reliable sessions, transactions, or streaming is supported or enabled.</span></span>  
  
- <span data-ttu-id="908be-158">`bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="908be-158">`bindingConfiguration`.</span></span> <span data-ttu-id="908be-159">Müssen die Standardwerte einer Bindung geändert werden, kann dies geschehen, indem das entsprechende `binding` -Element im `bindings` -Element konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="908be-159">If the default values of a binding must be modified, this can be done by configuring the appropriate `binding` element in the `bindings` element.</span></span> <span data-ttu-id="908be-160">Diesem Attribut sollte derselbe Wert zugewiesen werden, wie dem `name` -Attribut des `binding` -Elements, das verwendet wird, um die Standardwerte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="908be-160">This attribute should be given the same value as the `name` attribute of the `binding` element that is used to change the defaults.</span></span> <span data-ttu-id="908be-161">Wenn kein Name angegeben wird oder kein `bindingConfiguration` in der Bindung festgelegt ist, wird die Standardbindung des Bindungstyp im Endpunkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="908be-161">If no name is given, or no `bindingConfiguration` is specified in the binding, then the default binding of the binding type is used in the endpoint.</span></span>  
  
- <span data-ttu-id="908be-162">`contract`.</span><span class="sxs-lookup"><span data-stu-id="908be-162">`contract`.</span></span> <span data-ttu-id="908be-163">Gibt die Schnittstelle an, die den Vertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="908be-163">Specifies the interface that defines the contract.</span></span> <span data-ttu-id="908be-164">Das ist die Schnittstelle, die im CLR-Typ (Common Language Runtime) implementiert ist, der vom `name` -Attribut des `service` -Elements angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="908be-164">This is the interface implemented in the common language runtime (CLR) type specified by the `name` attribute of the `service` element.</span></span>  
  
- [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a><span data-ttu-id="908be-165">Das \<bindings> Element</span><span class="sxs-lookup"><span data-stu-id="908be-165">The \<bindings> Element</span></span>  

 <span data-ttu-id="908be-166">Das `bindings` -Element enthält die Spezifikationen für alle Bindungen, die von jedem in einem Dienst definierten Endpunkt verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="908be-166">The `bindings` element contains the specifications for all bindings that can be used by any endpoint defined in any service.</span></span>  
  
 [\<bindings>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a><span data-ttu-id="908be-167">Das \<binding> Element</span><span class="sxs-lookup"><span data-stu-id="908be-167">The \<binding> Element</span></span>  

 <span data-ttu-id="908be-168">Das `binding` -Elemente, die im `bindings` -Element enthalten sind, können entweder eine der systemeigenen Bindungen (siehe [System-Provided Bindings](system-provided-bindings.md)) oder eine benutzerdefinierte Bindung (siehe [Custom Bindings](./extending/custom-bindings.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="908be-168">The `binding` elements contained in the `bindings` element can be either one of the system-provided bindings (see [System-Provided Bindings](system-provided-bindings.md)) or a custom binding (see [Custom Bindings](./extending/custom-bindings.md)).</span></span> <span data-ttu-id="908be-169">Das `binding` -Element verfügt über ein `name` -Attribut, das eine Beziehung zwischen der Bindung und dem Endpunkt herstellt, der im `bindingConfiguration` -Attribut des `endpoint` -Elements angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="908be-169">The `binding` element has a `name` attribute that correlates the binding with the endpoint specified in the `bindingConfiguration` attribute of the `endpoint` element.</span></span> <span data-ttu-id="908be-170">Wenn kein Name angegeben wird, entspricht die Bindung der Standardbindung für diesen Bindungstyp.</span><span class="sxs-lookup"><span data-stu-id="908be-170">If no name is specified then that binding corresponds to the default of that binding type.</span></span>  
  
<span data-ttu-id="908be-171">Weitere Informationen zum Konfigurieren von Diensten und Clients finden Sie unter [Konfigurieren von WCF-Diensten](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="908be-171">For more information about configuring services and clients, see [Configuring WCF services](configuring-services.md).</span></span>
  
 [\<binding>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a><span data-ttu-id="908be-172">Das \<behaviors> Element</span><span class="sxs-lookup"><span data-stu-id="908be-172">The \<behaviors> Element</span></span>  

 <span data-ttu-id="908be-173">Dies ist ein Containerelement für die `behavior` -Elemente, die das Verhalten eines Diensts definieren.</span><span class="sxs-lookup"><span data-stu-id="908be-173">This is a container element for the `behavior` elements that define the behaviors for a service.</span></span>  
  
 [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a><span data-ttu-id="908be-174">Das \<behavior> Element</span><span class="sxs-lookup"><span data-stu-id="908be-174">The \<behavior> Element</span></span>  

 <span data-ttu-id="908be-175">Jedes `behavior` Element wird durch ein `name` -Attribut identifiziert und stellt entweder ein vom System bereitgestelltes Verhalten dar, z `throttling` . b. <> oder ein benutzerdefiniertes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="908be-175">Each `behavior` element is identified by a `name` attribute and provides either a system-provided behavior, such as <`throttling`>, or a custom behavior.</span></span> <span data-ttu-id="908be-176">Wenn kein Name angegeben wird, entspricht dieses Verhaltenselement dem standardmäßigen Dienst- oder Endpunktverhalten.</span><span class="sxs-lookup"><span data-stu-id="908be-176">If no name is given then that behavior element corresponds to the default service or endpoint behavior.</span></span>  
  
 [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a><span data-ttu-id="908be-177">Gewusst wie: Verwenden von Bindungs- und Verhaltenskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="908be-177">How to Use Binding and Behavior Configurations</span></span>  

 <span data-ttu-id="908be-178">WCF vereinfacht das Freigeben von Konfigurationen zwischen Endpunkten mithilfe eines Referenzsystems in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="908be-178">WCF makes it easy to share configurations between endpoints using a reference system in configuration.</span></span> <span data-ttu-id="908be-179">Statt einem Endpunkt direkt Konfigurationswerte zuzuweisen, werden bindungsrelevante Konfigurationswerte in `bindingConfiguration` -Elementen des `<binding>` -Abschnitts gruppiert.</span><span class="sxs-lookup"><span data-stu-id="908be-179">Rather than directly assigning configuration values to an endpoint, binding-related configuration values are grouped in `bindingConfiguration` elements in the `<binding>` section.</span></span> <span data-ttu-id="908be-180">Eine Bindungskonfiguration ist eine benannte Gruppe von Einstellungen einer Bindung.</span><span class="sxs-lookup"><span data-stu-id="908be-180">A binding configuration is a named group of settings on a binding.</span></span> <span data-ttu-id="908be-181">Endpunkte können dann mithilfe des Namens auf eine `bindingConfiguration` verweisen.</span><span class="sxs-lookup"><span data-stu-id="908be-181">Endpoints can then reference the `bindingConfiguration` by name.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!-- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint
          address="myAddress" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint
          address="myAddress2" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint
          address="myAddress3" binding="basicHttpBinding"
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="908be-182">Das `name` -Attribut der `bindingConfiguration` wird im `<binding>` -Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="908be-182">The `name` of the `bindingConfiguration` is set in the `<binding>` element.</span></span> <span data-ttu-id="908be-183">`name`Muss eine eindeutige Zeichenfolge im Bereich des Bindungs Typs sein – in diesem Fall die [<BasicHttpBinding \> ](../configure-apps/file-schema/wcf/basichttpbinding.md)oder ein leerer Wert, um auf die Standard Bindung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="908be-183">The `name` must be a unique string within the scope of the binding type—in this case the [<basicHttpBinding\>](../configure-apps/file-schema/wcf/basichttpbinding.md), or an empty value to refer to the default binding.</span></span> <span data-ttu-id="908be-184">Der Endpunkt wird mit der Konfiguration verknüpft, indem das `bindingConfiguration` -Attribut auf diese Zeichenfolge festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="908be-184">The endpoint links to the configuration by setting the `bindingConfiguration` attribute to this string.</span></span>  
  
 <span data-ttu-id="908be-185">Eine `behaviorConfiguration` wird genauso implementiert, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="908be-185">A `behaviorConfiguration` is implemented the same way, as illustrated in the following sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="908be-186">Beachten Sie, dass dem Dienst der Standardsatz von Dienstverhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="908be-186">Note that the default set of service behaviors are added to the service.</span></span> <span data-ttu-id="908be-187">Dieses System ermöglicht es Endpunkten, allgemeine Konfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="908be-187">This system allows endpoints to share common configurations without redefining the settings.</span></span> <span data-ttu-id="908be-188">Wenn ein Computer weiter Bereich erforderlich ist, erstellen Sie die Bindungs-oder Verhaltens Konfiguration in Machine.config. Die Konfigurationseinstellungen sind in allen App.config Dateien verfügbar.</span><span class="sxs-lookup"><span data-stu-id="908be-188">If machine-wide scope is required, create the binding or behavior configuration in Machine.config. The configuration settings are available in all App.config files.</span></span> <span data-ttu-id="908be-189">Das [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) macht es leicht, Konfigurationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="908be-189">The [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) makes it easy to create configurations.</span></span>  
  
## <a name="behavior-merge"></a><span data-ttu-id="908be-190">Verhaltenszusammenführung</span><span class="sxs-lookup"><span data-stu-id="908be-190">Behavior Merge</span></span>  

 <span data-ttu-id="908be-191">Die Funktion der Verhaltenszusammenführung erleichtert die Verwaltung von Verhalten, wenn eine Reihe allgemeiner Verhalten einheitlich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="908be-191">The behavior merge feature makes it easier to manage behaviors when you want a set of common behaviors to be used consistently.</span></span> <span data-ttu-id="908be-192">Mithilfe dieser Funktion können Sie Verhalten auf verschiedenen Ebenen der Konfigurationshierarchie angeben und festlegen, dass Dienste Verhalten von verschiedenen Ebenen der Konfigurationshierarchie erben sollen.</span><span class="sxs-lookup"><span data-stu-id="908be-192">This feature allows you to specify behaviors at different levels of the configuration hierarchy and have services inherit behaviors from multiple levels of the configuration hierarchy.</span></span> <span data-ttu-id="908be-193">Dies soll im Folgenden veranschaulicht werden. Angenommen, in IIS ist das folgende Layout virtueller Verzeichnisse gegeben:</span><span class="sxs-lookup"><span data-stu-id="908be-193">To illustrate how this works assume you have the following virtual directory layout in IIS:</span></span>  
  
 `~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc`
  
 <span data-ttu-id="908be-194">Und `~\Web.config` die Datei hat folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="908be-194">And your `~\Web.config` file has the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="908be-195">Außerdem ist eine untergeordnete Datei Web.config mit folgendem Inhalt unter ~\Child\Web.config vorhanden:</span><span class="sxs-lookup"><span data-stu-id="908be-195">And you have a child Web.config located at ~\Child\Web.config with the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="908be-196">Der Dienst unter ~\Child\Service.svc wird sowohl das serviceDebug-Verhalten als auch das serviceMetadata-Verhalten berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="908be-196">The service located at ~\Child\Service.svc will behave as though it has both the serviceDebug and serviceMetadata behaviors.</span></span> <span data-ttu-id="908be-197">Der Dienst unter ~\Service.svc berücksichtigt lediglich das serviceDebug-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="908be-197">The service located at ~\Service.svc will only have the serviceDebug behavior.</span></span> <span data-ttu-id="908be-198">Die beiden Verhaltensauflistungen mit demselben Namen (in diesem Fall einer leeren Zeichenfolge) werden zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="908be-198">What happens is that the two behavior collections with the same name (in this case the empty string) are merged.</span></span>  
  
 <span data-ttu-id="908be-199">Sie können Verhaltens Auflistungen auch mit dem \<clear> -Tag löschen und einzelne Verhalten aus der Auflistung entfernen, indem Sie das- \<remove> Tag verwenden.</span><span class="sxs-lookup"><span data-stu-id="908be-199">You can also clear behavior collections by using the \<clear> tag and removed individual behaviors from the collection by using the \<remove> tag.</span></span> <span data-ttu-id="908be-200">Die folgenden beiden Konfigurationen führen beispielsweise dazu, dass der untergeordnete Dienst lediglich das serviceMetadata-Verhalten verwendet:</span><span class="sxs-lookup"><span data-stu-id="908be-200">For example, the following two configuration results in the child service having only the serviceMetadata behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="908be-201">Die Verhaltenszusammenführung erfolgt für unbenannte Verhaltensauflistungen (wie oben veranschaulicht) sowie für benannte Verhaltensauflistungen.</span><span class="sxs-lookup"><span data-stu-id="908be-201">Behavior merge is done for nameless behavior collections as shown above and named behavior collections as well.</span></span>  
  
 <span data-ttu-id="908be-202">Die Verhaltens Zusammenführung funktioniert in der IIS-Hostingumgebung, in der Web.config Dateien hierarchisch mit den Stamm Web.config Datei und machine.config zusammengeführt werden. Es funktioniert aber auch in der Anwendungsumgebung, in der machine.config mit der App.config Datei zusammenführen können.</span><span class="sxs-lookup"><span data-stu-id="908be-202">Behavior merge works in the IIS hosting environment, in which Web.config files merge hierarchically with the root Web.config file and machine.config. But it also works in the application environment, where machine.config can merge with the App.config file.</span></span>  
  
 <span data-ttu-id="908be-203">Die Verhaltenszusammenführung wird sowohl auf Endpunktverhalten als auch auf Dienstverhalten in der Konfiguration angewendet.</span><span class="sxs-lookup"><span data-stu-id="908be-203">Behavior merge applies to both endpoint behaviors and service behaviors in configuration.</span></span>  
  
 <span data-ttu-id="908be-204">Wenn eine untergeordnete Verhaltensauflistung ein Verhalten enthält, das bereits in der übergeordneten Verhaltensauflistung enthalten ist, wird das übergeordnete Verhalten vom untergeordneten überschrieben.</span><span class="sxs-lookup"><span data-stu-id="908be-204">If a child behavior collection contains a behavior that’s already present in the parent behavior collection, the child behavior overrides the parent.</span></span> <span data-ttu-id="908be-205">Wenn also eine übergeordnete Verhaltens Auflistung `<serviceMetadata httpGetEnabled="False" />` und eine untergeordnete Verhaltens Auflistung hätte `<serviceMetadata httpGetEnabled="True" />` , würde das untergeordnete Verhalten das übergeordnete Verhalten in der Verhaltens Auflistung überschreiben, und HttpGetEnabled wäre "true".</span><span class="sxs-lookup"><span data-stu-id="908be-205">So if a parent behavior collection had `<serviceMetadata httpGetEnabled="False" />` and a child behavior collection had `<serviceMetadata httpGetEnabled="True" />`, the child behavior would override the parent behavior in the behavior collection and httpGetEnabled would be "true".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="908be-206">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="908be-206">See also</span></span>

- [<span data-ttu-id="908be-207">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="908be-207">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="908be-208">Konfigurieren von WCF-Diensten</span><span class="sxs-lookup"><span data-stu-id="908be-208">Configuring WCF services</span></span>](configuring-services.md)
- [\<service>](../configure-apps/file-schema/wcf/service.md)
- [\<binding>](../configure-apps/file-schema/wcf/bindings.md)
