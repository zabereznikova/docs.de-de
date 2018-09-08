---
title: Konfigurieren von Diensten mit Konfigurationsdateien
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: 904abff4f3cae5873fe3cc9705dee84f73e2a523
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195570"
---
# <a name="configuring-services-using-configuration-files"></a><span data-ttu-id="8bd36-102">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8bd36-102">Configuring Services Using Configuration Files</span></span>
<span data-ttu-id="8bd36-103">Konfigurieren eines Windows Communication Foundation (WCF)-Diensts mit einer Konfigurationsdatei bietet Ihnen die Flexibilität für die Bereitstellung von Endpunkt und die Daten zum Dienst zum Zeitpunkt der Bereitstellung statt zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="8bd36-103">Configuring a Windows Communication Foundation (WCF) service with a configuration file gives you the flexibility of providing endpoint and service behavior data at the point of deployment instead of at design time.</span></span> <span data-ttu-id="8bd36-104">Dieses Thema beschreibt die dafür verfügbaren grundlegenden Verfahren.</span><span class="sxs-lookup"><span data-stu-id="8bd36-104">This topic outlines the primary techniques available.</span></span>  
  
 <span data-ttu-id="8bd36-105">Ein WCF-Dienst ist konfigurierbar mit der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Configuration-Technologie.</span><span class="sxs-lookup"><span data-stu-id="8bd36-105">A WCF service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="8bd36-106">In den meisten Fällen werden die XML-Elemente in die Datei "Web.config" für eine Website (Internet Information Services, IIS) hinzugefügt, die einen WCF-Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="8bd36-106">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="8bd36-107">Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen für die Kommunikation mit dem Dienst verwendeten Adressen) für einzelne Computer.</span><span class="sxs-lookup"><span data-stu-id="8bd36-107">The elements allow you to change details such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span> <span data-ttu-id="8bd36-108">WCF umfasst darüber hinaus mehrere vom System bereitgestellte Elemente, mit die Sie schnell die grundlegenden Features für einen Dienst auswählen können.</span><span class="sxs-lookup"><span data-stu-id="8bd36-108">In addition, WCF includes several system-provided elements that allow you to quickly select the most basic features for a service.</span></span> <span data-ttu-id="8bd36-109">Beginnend mit [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF enthält ein neues Standard-Konfigurationsmodell, das WCF-konfigurationsanforderungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="8bd36-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="8bd36-110">Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime automatisch Ihren Dienst mit einigen Standardendpunkte und standardmäßige Bindung/benutzerdefiniertem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="8bd36-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with some standard endpoints and default binding/behavior.</span></span> <span data-ttu-id="8bd36-111">In der Praxis ist das Schreiben einer Konfiguration einem wesentlichen Teil der WCF-Anwendungen zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="8bd36-111">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
 <span data-ttu-id="8bd36-112">Weitere Informationen finden Sie unter [Konfigurieren von Bindungen für Dienste](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8bd36-112">For more information, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span> <span data-ttu-id="8bd36-113">Eine Liste der mit den am häufigsten verwendeten Elemente, finden Sie unter [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="8bd36-113">For a list of of the most commonly used elements, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="8bd36-114">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8bd36-114">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8bd36-115">Beim Bereitstellen paralleler Szenarien, in denen zwei verschiedene Versionen eines Diensts bereitgestellt werden, müssen bei Verweisen in Konfigurationsdateien partielle Assemblynamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8bd36-115">When deploying side by side scenarios where two different versions of a service are deployed, it is necessary to specify partial names of assemblies referenced in configuration files.</span></span> <span data-ttu-id="8bd36-116">Dies liegt daran, dass die Konfigurationsdatei gemeinsam von allen Versionen eines Diensts verwendet wird und dass diese Dienste ggf. unter unterschiedlichen Versionen von .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd36-116">This is because the configuration file is shared across all versions of a service and they could be running under different versions of the .NET Framework.</span></span>  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a><span data-ttu-id="8bd36-117">System.Configuration: Web.config und App.config</span><span class="sxs-lookup"><span data-stu-id="8bd36-117">System.Configuration: Web.config and App.config</span></span>  
 <span data-ttu-id="8bd36-118">WCF verwendet das Konfigurationssystem System.Configuration über die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bd36-118">WCF uses the System.Configuration configuration system of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="8bd36-119">Wenn einen Dienst in Visual Studio zu konfigurieren, verwenden Sie entweder eine Datei "Web.config" oder eine Datei "App.config", um die Einstellungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8bd36-119">When configuring a service in Visual Studio, use either a Web.config file or an App.config file to specify the settings.</span></span> <span data-ttu-id="8bd36-120">Die Wahl der Konfigurationsdatei wird durch die Hostumgebung des Diensts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-120">The choice of the configuration file name is determined by the hosting environment you choose for the service.</span></span> <span data-ttu-id="8bd36-121">Wenn Sie den Dienst in IIS hosten, verwenden Sie eine Web.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="8bd36-121">If you are using IIS to host your service, use a Web.config file.</span></span> <span data-ttu-id="8bd36-122">Bei einer anderen Hostumgebung verwenden Sie eine App.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="8bd36-122">If you are using any other hosting environment, use an App.config file.</span></span>  
  
 <span data-ttu-id="8bd36-123">In Visual Studio wird die Datei "App.config" verwendet, um die endgültige Konfiguration-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-123">In Visual Studio, the file named App.config is used to create the final configuration file.</span></span> <span data-ttu-id="8bd36-124">Der tatsächlich für die Konfigurationsdatei verwendete Name hängt vom Assemblynamen ab.</span><span class="sxs-lookup"><span data-stu-id="8bd36-124">The final name actually used for the configuration depends on the assembly name.</span></span> <span data-ttu-id="8bd36-125">Einer Assembly mit dem Namen "Cohowinery.exe" ist beispielsweise die Konfigurationsdatei namens "Cohowinery.exe.config" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8bd36-125">For example, an assembly named "Cohowinery.exe" has a final configuration file name of "Cohowinery.exe.config".</span></span> <span data-ttu-id="8bd36-126">Sie müssen jedoch nur die Datei App.config ändern.</span><span class="sxs-lookup"><span data-stu-id="8bd36-126">However, you only need to modify the App.config file.</span></span> <span data-ttu-id="8bd36-127">An dieser Datei vorgenommene Änderungen werden bei der Kompilierung automatisch an die tatsächliche Anwendungskonfigurationsdatei weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="8bd36-127">Changes made to that file are automatically made to the final application configuration file at compile time.</span></span>  
  
 <span data-ttu-id="8bd36-128">Bei Verwendung einer App.config-Datei führt das Konfigurationssystem den Inhalt dieser Datei mit dem Inhalt der Datei Machine.config zusammen, sobald die Anwendung gestartet und die Konfiguration übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="8bd36-128">In using an App.config, file the configuration system merges the App.config file with content of the Machine.config file when the application starts and the configuration is applied.</span></span> <span data-ttu-id="8bd36-129">Dieser Mechanismus ermöglicht es, computerweite Einstellungen in der Datei Machine.config zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8bd36-129">This mechanism allows machine-wide settings to be defined in the Machine.config file.</span></span> <span data-ttu-id="8bd36-130">Die Datei App.config kann verwendet werden, um Einstellungen in der Datei Machine.config zu überschreiben. Sie können Einstellungen in der Datei Machine.config aber auch sperren, sodass diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bd36-130">The App.config file can be used to override the settings of the Machine.config file; you can also lock in the settings in Machine.config file so that they get used.</span></span> <span data-ttu-id="8bd36-131">Im Fall der Datei Web.config führt das Konfigurationssystem den Inhalt aller Web.config-Dateien in allen Verzeichnissen zur schließlich verwendeten Konfiguration im Anwendungsverzeichnis zusammen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-131">In the Web.config case, the configuration system merges the Web.config files in all directories leading up to the application directory into the configuration that gets applied.</span></span> <span data-ttu-id="8bd36-132">Weitere Informationen zur Konfiguration und der Priorität der Einstellungen finden Sie unter Themen in der <xref:System.Configuration> Namespace.</span><span class="sxs-lookup"><span data-stu-id="8bd36-132">For more information about configuration and the setting priorities, see topics in the <xref:System.Configuration> namespace.</span></span>  
  
## <a name="major-sections-of-the-configuration-file"></a><span data-ttu-id="8bd36-133">Hauptabschnitte der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="8bd36-133">Major Sections of the Configuration File</span></span>  
 <span data-ttu-id="8bd36-134">Die Hauptabschnitte der Konfigurationsdatei umfassen folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="8bd36-134">The main sections in the configuration file include the following elements.</span></span>  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!—- Define the service endpoints. This section is optional in the new  
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
>  <span data-ttu-id="8bd36-135">Die Bindungs- und Verhaltensabschnitte sind optional und nur bei Bedarf enthalten.</span><span class="sxs-lookup"><span data-stu-id="8bd36-135">The bindings and behaviors sections are optional and are only included if required.</span></span>  
  
### <a name="the-services-element"></a><span data-ttu-id="8bd36-136">Die \<Services >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-136">The \<services> Element</span></span>  
 <span data-ttu-id="8bd36-137">Das `services` -Element enthält die Spezifikationen aller Dienste, die die Anwendung hostet.</span><span class="sxs-lookup"><span data-stu-id="8bd36-137">The `services` element contains the specifications for all services the application hosts.</span></span> <span data-ttu-id="8bd36-138">Wenn das vereinfachte Konfigurationsmodell in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]verwendet wird, ist dieser Abschnitt optional.</span><span class="sxs-lookup"><span data-stu-id="8bd36-138">Starting with the simplified configuration model in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], this section is optional.</span></span>  
  
 [<span data-ttu-id="8bd36-139">\<services></span><span class="sxs-lookup"><span data-stu-id="8bd36-139">\<services></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a><span data-ttu-id="8bd36-140">Die \<Service >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-140">The \<service> Element</span></span>  
 <span data-ttu-id="8bd36-141">Jeder Dienst verfügt über diese Attribute:</span><span class="sxs-lookup"><span data-stu-id="8bd36-141">Each service has these attributes:</span></span>  
  
-   <span data-ttu-id="8bd36-142">`name`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-142">`name`.</span></span> <span data-ttu-id="8bd36-143">Gibt den Typ an, der eine Implementierung eines Dienstvertrags bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-143">Specifies the type that provides an implementation of a service contract.</span></span> <span data-ttu-id="8bd36-144">Dies ist ein vollqualifizierter Name, der aus dem Namespace und einem Punkt gefolgt von dem Typnamen besteht.</span><span class="sxs-lookup"><span data-stu-id="8bd36-144">This is a fully qualified name which consists of the namespace, a period, and then the type name.</span></span> <span data-ttu-id="8bd36-145">Beispiel: `"MyNameSpace.myServiceType"`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-145">For example `"MyNameSpace.myServiceType"`.</span></span>  
  
-   <span data-ttu-id="8bd36-146">`behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-146">`behaviorConfiguration`.</span></span> <span data-ttu-id="8bd36-147">Gibt den Namen eines `behavior` -Elements an, das im `behaviors` -Element gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="8bd36-147">Specifies the name of one of the `behavior` elements found in the `behaviors` element.</span></span> <span data-ttu-id="8bd36-148">Das angegebene Verhalten steuert Aktionen, beispielsweise ob der Dienst Identitätswechsel erlaubt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-148">The specified behavior governs actions such as whether the service allows impersonation.</span></span> <span data-ttu-id="8bd36-149">Wenn der Wert ein leerer Name oder kein `behaviorConfiguration` ist, wird dem Dienst der Standardsatz von Dienstverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-149">If its value is the empty name or no `behaviorConfiguration` is provided then the default set of service behaviors is added to the service.</span></span>  
  
-   [<span data-ttu-id="8bd36-150">\<service></span><span class="sxs-lookup"><span data-stu-id="8bd36-150">\<service></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a><span data-ttu-id="8bd36-151">Die \<Endpunkt >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-151">The \<endpoint> Element</span></span>  
 <span data-ttu-id="8bd36-152">Jeder Endpunkt benötigt eine Adresse, eine Bindung und einen Vertrag. Diese Elemente werden durch die folgenden Attribute dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8bd36-152">Each endpoint requires an address, a binding, and a contract, which are represented by the following attributes:</span></span>  
  
-   <span data-ttu-id="8bd36-153">`address`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-153">`address`.</span></span> <span data-ttu-id="8bd36-154">Gibt den Uniform Resource Identifier (URI) des Diensts an. Er kann als absolute Adresse oder als eine zur Basisadresse des Diensts relative Adresse angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8bd36-154">Specifies the service's Uniform Resource Identifier (URI), which can be an absolute address or one that is given relative to the base address of the service.</span></span> <span data-ttu-id="8bd36-155">Eine leere Zeichenfolge zeigt an, dass der Endpunkt unter der Basisadresse verfügbar ist. Diese Basisadresse wird bei der Erstellung des <xref:System.ServiceModel.ServiceHost> für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="8bd36-155">If set to an empty string, it indicates that the endpoint is available at the base address that is specified when creating the <xref:System.ServiceModel.ServiceHost> for the service.</span></span>  
  
-   <span data-ttu-id="8bd36-156">`binding`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-156">`binding`.</span></span> <span data-ttu-id="8bd36-157">Gibt üblicherweise eine vom System bereitgestellte Bindung, beispielsweise <xref:System.ServiceModel.WSHttpBinding>an, kann aber auch eine benutzerdefinierte Bindung angeben.</span><span class="sxs-lookup"><span data-stu-id="8bd36-157">Typically specifies a system-provided binding like <xref:System.ServiceModel.WSHttpBinding>, but can also specify a user-defined binding.</span></span> <span data-ttu-id="8bd36-158">Die angegebene Bindung bestimmt, welcher Typ von Transport, Sicherheit und Codierung verwendet wird, und ob zuverlässige Sitzungen, Transaktionen oder Streaming unterstützt werden oder aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8bd36-158">The binding specified determines the type of transport, security and encoding used, and whether reliable sessions, transactions, or streaming is supported or enabled.</span></span>  
  
-   <span data-ttu-id="8bd36-159">`bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-159">`bindingConfiguration`.</span></span> <span data-ttu-id="8bd36-160">Müssen die Standardwerte einer Bindung geändert werden, kann dies geschehen, indem das entsprechende `binding` -Element im `bindings` -Element konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8bd36-160">If the default values of a binding must be modified, this can be done by configuring the appropriate `binding` element in the `bindings` element.</span></span> <span data-ttu-id="8bd36-161">Diesem Attribut sollte derselbe Wert zugewiesen werden, wie dem `name` -Attribut des `binding` -Elements, das verwendet wird, um die Standardwerte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8bd36-161">This attribute should be given the same value as the `name` attribute of the `binding` element that is used to change the defaults.</span></span> <span data-ttu-id="8bd36-162">Wenn kein Name angegeben wird oder kein `bindingConfiguration` in der Bindung festgelegt ist, wird die Standardbindung des Bindungstyp im Endpunkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bd36-162">If no name is given, or no `bindingConfiguration` is specified in the binding, then the default binding of the binding type is used in the endpoint.</span></span>  
  
-   <span data-ttu-id="8bd36-163">`contract`.</span><span class="sxs-lookup"><span data-stu-id="8bd36-163">`contract`.</span></span> <span data-ttu-id="8bd36-164">Gibt die Schnittstelle an, die den Vertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd36-164">Specifies the interface that defines the contract.</span></span> <span data-ttu-id="8bd36-165">Das ist die Schnittstelle, die im CLR-Typ (Common Language Runtime) implementiert ist, der vom `name` -Attribut des `service` -Elements angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bd36-165">This is the interface implemented in the common language runtime (CLR) type specified by the `name` attribute of the `service` element.</span></span>  
  
-   [<span data-ttu-id="8bd36-166">\<Endpunkt >-Elementverweis</span><span class="sxs-lookup"><span data-stu-id="8bd36-166">\<endpoint> element reference</span></span>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)  
  
### <a name="the-bindings-element"></a><span data-ttu-id="8bd36-167">Die \<Bindings >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-167">The \<bindings> Element</span></span>  
 <span data-ttu-id="8bd36-168">Das `bindings` -Element enthält die Spezifikationen für alle Bindungen, die von jedem in einem Dienst definierten Endpunkt verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8bd36-168">The `bindings` element contains the specifications for all bindings that can be used by any endpoint defined in any service.</span></span>  
  
 [<span data-ttu-id="8bd36-169">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8bd36-169">\<bindings></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a><span data-ttu-id="8bd36-170">Die \<Bindung >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-170">The \<binding> Element</span></span>  
 <span data-ttu-id="8bd36-171">Das `binding` -Elemente, die im `bindings` -Element enthalten sind, können entweder eine der systemeigenen Bindungen (siehe [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) oder eine benutzerdefinierte Bindung (siehe [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="8bd36-171">The `binding` elements contained in the `bindings` element can be either one of the system-provided bindings (see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) or a custom binding (see [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="8bd36-172">Das `binding` -Element verfügt über ein `name` -Attribut, das eine Beziehung zwischen der Bindung und dem Endpunkt herstellt, der im `bindingConfiguration` -Attribut des `endpoint` -Elements angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8bd36-172">The `binding` element has a `name` attribute that correlates the binding with the endpoint specified in the `bindingConfiguration` attribute of the `endpoint` element.</span></span> <span data-ttu-id="8bd36-173">Wenn kein Name angegeben wird, entspricht die Bindung der Standardbindung für diesen Bindungstyp.</span><span class="sxs-lookup"><span data-stu-id="8bd36-173">If no name is specified then that binding corresponds to the default of that binding type.</span></span>  
  
 <span data-ttu-id="8bd36-174">Weitere Informationen zum Konfigurieren von Diensten und Clients finden Sie unter [Konfigurieren von Windows Communication Foundation-Anwendungen](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="8bd36-174">For more information about configuring services and clients, see [Configuring Windows Communication Foundation Applications](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
 [<span data-ttu-id="8bd36-175">\<binding></span><span class="sxs-lookup"><span data-stu-id="8bd36-175">\<binding></span></span>](../../../docs/framework/misc/binding.md)  
  
### <a name="the-behaviors-element"></a><span data-ttu-id="8bd36-176">Die \<Verhaltensweisen >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-176">The \<behaviors> Element</span></span>  
 <span data-ttu-id="8bd36-177">Dies ist ein Containerelement für die `behavior` -Elemente, die das Verhalten eines Diensts definieren.</span><span class="sxs-lookup"><span data-stu-id="8bd36-177">This is a container element for the `behavior` elements that define the behaviors for a service.</span></span>  
  
 [<span data-ttu-id="8bd36-178">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8bd36-178">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a><span data-ttu-id="8bd36-179">Die \<Verhalten >-Element</span><span class="sxs-lookup"><span data-stu-id="8bd36-179">The \<behavior> Element</span></span>  
 <span data-ttu-id="8bd36-180">Jedes `behavior`-Element wird durch ein `name`-Attribut identifiziert und stellt entweder ein vom System definiertes Verhalten, beispielsweise <`throttling`>, oder ein benutzerdefiniertes Verhalten bereit.</span><span class="sxs-lookup"><span data-stu-id="8bd36-180">Each `behavior` element is identified by a `name` attribute and provides either a system-provided behavior, such as <`throttling`>, or a custom behavior.</span></span> <span data-ttu-id="8bd36-181">Wenn kein Name angegeben wird, entspricht dieses Verhaltenselement dem standardmäßigen Dienst- oder Endpunktverhalten.</span><span class="sxs-lookup"><span data-stu-id="8bd36-181">If no name is given then that behavior element corresponds to the default service or endpoint behavior.</span></span>  
  
 [<span data-ttu-id="8bd36-182">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8bd36-182">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a><span data-ttu-id="8bd36-183">Gewusst wie: Verwenden von Bindungs- und Verhaltenskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="8bd36-183">How to Use Binding and Behavior Configurations</span></span>  
 <span data-ttu-id="8bd36-184">WCF erleichtert die Konfigurationen zwischen Endpunkten, die mithilfe eines Verweissystems in der Konfiguration gemeinsam zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bd36-184">WCF makes it easy to share configurations between endpoints using a reference system in configuration.</span></span> <span data-ttu-id="8bd36-185">Statt einem Endpunkt direkt Konfigurationswerte zuzuweisen, werden bindungsrelevante Konfigurationswerte in `bindingConfiguration` -Elementen des `<binding>` -Abschnitts gruppiert.</span><span class="sxs-lookup"><span data-stu-id="8bd36-185">Rather than directly assigning configuration values to an endpoint, binding-related configuration values are grouped in `bindingConfiguration` elements in the `<binding>` section.</span></span> <span data-ttu-id="8bd36-186">Eine Bindungskonfiguration ist eine benannte Gruppe von Einstellungen einer Bindung.</span><span class="sxs-lookup"><span data-stu-id="8bd36-186">A binding configuration is a named group of settings on a binding.</span></span> <span data-ttu-id="8bd36-187">Endpunkte können dann mithilfe des Namens auf eine `bindingConfiguration` verweisen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-187">Endpoints can then reference the `bindingConfiguration` by name.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!—- Default binding for basicHttpBinding -->  
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
  
 <span data-ttu-id="8bd36-188">Das `name` -Attribut der `bindingConfiguration` wird im `<binding>` -Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-188">The `name` of the `bindingConfiguration` is set in the `<binding>` element.</span></span> <span data-ttu-id="8bd36-189">Die `name` muss eine eindeutige Zeichenfolge im Bereich des Bindungstyps sein – in diesem Fall die [< BasicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), oder ein leerer Wert, auf die standardbindung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-189">The `name` must be a unique string within the scope of the binding type—in this case the [<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), or an empty value to refer to the default binding.</span></span> <span data-ttu-id="8bd36-190">Der Endpunkt wird mit der Konfiguration verknüpft, indem das `bindingConfiguration` -Attribut auf diese Zeichenfolge festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8bd36-190">The endpoint links to the configuration by setting the `bindingConfiguration` attribute to this string.</span></span>  
  
 <span data-ttu-id="8bd36-191">Eine `behaviorConfiguration` wird genauso implementiert, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-191">A `behaviorConfiguration` is implemented the same way, as illustrated in the following sample.</span></span>  
  
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
  
 <span data-ttu-id="8bd36-192">Beachten Sie, dass dem Dienst der Standardsatz von Dienstverhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8bd36-192">Note that the default set of service behaviors are added to the service.</span></span> <span data-ttu-id="8bd36-193">Dieses System ermöglicht es Endpunkten, allgemeine Konfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-193">This system allows endpoints to share common configurations without redefining the settings.</span></span> <span data-ttu-id="8bd36-194">Wenn ein computerweiter Bereich erforderlich ist, erstellen Sie die Bindungs- oder Verhaltenskonfiguration in Machine.config. Die Konfigurationseinstellungen sind in allen App.config-Dateien verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8bd36-194">If machine-wide scope is required, create the binding or behavior configuration in Machine.config. The configuration settings are available in all App.config files.</span></span> <span data-ttu-id="8bd36-195">Das [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) macht es leicht, Konfigurationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-195">The [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) makes it easy to create configurations.</span></span>  
  
## <a name="behavior-merge"></a><span data-ttu-id="8bd36-196">Verhaltenszusammenführung</span><span class="sxs-lookup"><span data-stu-id="8bd36-196">Behavior Merge</span></span>  
 <span data-ttu-id="8bd36-197">Die Funktion der Verhaltenszusammenführung erleichtert die Verwaltung von Verhalten, wenn eine Reihe allgemeiner Verhalten einheitlich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8bd36-197">The behavior merge feature makes it easier to manage behaviors when you want a set of common behaviors to be used consistently.</span></span> <span data-ttu-id="8bd36-198">Mithilfe dieser Funktion können Sie Verhalten auf verschiedenen Ebenen der Konfigurationshierarchie angeben und festlegen, dass Dienste Verhalten von verschiedenen Ebenen der Konfigurationshierarchie erben sollen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-198">This feature allows you to specify behaviors at different levels of the configuration hierarchy and have services inherit behaviors from multiple levels of the configuration hierarchy.</span></span> <span data-ttu-id="8bd36-199">Dies soll im Folgenden veranschaulicht werden. Angenommen, in IIS ist das folgende Layout virtueller Verzeichnisse gegeben:</span><span class="sxs-lookup"><span data-stu-id="8bd36-199">To illustrate how this works assume you have the following virtual directory layout in IIS:</span></span>  
  
 <span data-ttu-id="8bd36-200">~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc</span><span class="sxs-lookup"><span data-stu-id="8bd36-200">~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc</span></span>  
  
 <span data-ttu-id="8bd36-201">Die Datei ~\Web.config hat folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="8bd36-201">And your ~\Web.config file has the following contents:</span></span>  
  
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
  
 <span data-ttu-id="8bd36-202">Außerdem ist eine untergeordnete Datei Web.config mit folgendem Inhalt unter ~\Child\Web.config vorhanden:</span><span class="sxs-lookup"><span data-stu-id="8bd36-202">And you have a child Web.config located at ~\Child\Web.config with the following contents:</span></span>  
  
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
  
 <span data-ttu-id="8bd36-203">Der Dienst unter ~\Child\Service.svc wird sowohl das serviceDebug-Verhalten als auch das serviceMetadata-Verhalten berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-203">The service located at ~\Child\Service.svc will behave as though it has both the serviceDebug and serviceMetadata behaviors.</span></span> <span data-ttu-id="8bd36-204">Der Dienst unter ~\Service.svc berücksichtigt lediglich das serviceDebug-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="8bd36-204">The service located at ~\Service.svc will only have the serviceDebug behavior.</span></span> <span data-ttu-id="8bd36-205">Die beiden Verhaltensauflistungen mit demselben Namen (in diesem Fall einer leeren Zeichenfolge) werden zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="8bd36-205">What happens is that the two behavior collections with the same name (in this case the empty string) are merged.</span></span>  
  
 <span data-ttu-id="8bd36-206">Sie können verhaltensauflistungen auch löschen, mit der \<Löschen >-Tag und einzelne Verhaltensweisen mit aus der Auflistung entfernt die \<entfernen > Tag.</span><span class="sxs-lookup"><span data-stu-id="8bd36-206">You can also clear behavior collections by using the \<clear> tag and removed individual behaviors from the collection by using the \<remove> tag.</span></span> <span data-ttu-id="8bd36-207">Die folgenden beiden Konfigurationen führen beispielsweise dazu, dass der untergeordnete Dienst lediglich das serviceMetadata-Verhalten verwendet:</span><span class="sxs-lookup"><span data-stu-id="8bd36-207">For example, the following two configuration results in the child service having only the serviceMetadata behavior:</span></span>  
  
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
  
 <span data-ttu-id="8bd36-208">Die Verhaltenszusammenführung erfolgt für unbenannte Verhaltensauflistungen (wie oben veranschaulicht) sowie für benannte Verhaltensauflistungen.</span><span class="sxs-lookup"><span data-stu-id="8bd36-208">Behavior merge is done for nameless behavior collections as shown above and named behavior collections as well.</span></span>  
  
 <span data-ttu-id="8bd36-209">Die Verhaltenszusammenführung wird in der IIS-Hostingumgebung unterstützt, in der Web.config-Dateien hierarchisch mit den Stammdateien Web.config und machine.config zusammengeführt werden. Sie funktioniert jedoch auch in der Anwendungsumgebung, in der machine.config mit der Datei App.config zusammengeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bd36-209">Behavior merge works in the IIS hosting environment, in which Web.config files merge hierarchically with the root Web.config file and machine.config. But it also works in the application environment, where machine.config can merge with the App.config file.</span></span>  
  
 <span data-ttu-id="8bd36-210">Die Verhaltenszusammenführung wird sowohl auf Endpunktverhalten als auch auf Dienstverhalten in der Konfiguration angewendet.</span><span class="sxs-lookup"><span data-stu-id="8bd36-210">Behavior merge applies to both endpoint behaviors and service behaviors in configuration.</span></span>  
  
 <span data-ttu-id="8bd36-211">Wenn eine untergeordnete Verhaltensauflistung ein Verhalten enthält, das bereits in der übergeordneten Verhaltensauflistung enthalten ist, wird das übergeordnete Verhalten vom untergeordneten überschrieben.</span><span class="sxs-lookup"><span data-stu-id="8bd36-211">If a child behavior collection contains a behavior that’s already present in the parent behavior collection, the child behavior overrides the parent.</span></span> <span data-ttu-id="8bd36-212">Wenn eine übergeordnete verhaltensauflistung `<serviceMetadata httpGetEnabled="False" />` und eine untergeordnete verhaltensauflistung `<serviceMetadata httpGetEnabled="True" />`, überschreibt das untergeordnete Verhalten das übergeordnete Verhalten in der verhaltensauflistung, und HttpGetEnabled wird auf "true".</span><span class="sxs-lookup"><span data-stu-id="8bd36-212">So if a parent behavior collection had `<serviceMetadata httpGetEnabled="False" />` and a child behavior collection had `<serviceMetadata httpGetEnabled="True" />`, the child behavior would override the parent behavior in the behavior collection and httpGetEnabled would be "true".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd36-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bd36-213">See Also</span></span>  
 [<span data-ttu-id="8bd36-214">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8bd36-214">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="8bd36-215">Konfigurieren von Windows Communication Foundation-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8bd36-215">Configuring Windows Communication Foundation Applications</span></span>](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [<span data-ttu-id="8bd36-216">\<service></span><span class="sxs-lookup"><span data-stu-id="8bd36-216">\<service></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
 [<span data-ttu-id="8bd36-217">\<binding></span><span class="sxs-lookup"><span data-stu-id="8bd36-217">\<binding></span></span>](../../../docs/framework/misc/binding.md)
