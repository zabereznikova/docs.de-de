---
title: Sperre der PII-Sicherheit
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ec8af8c7df9335774b1f3953f88c2aad438963b6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809029"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="35f1f-102">Sperre der PII-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="35f1f-102">PII Security Lockdown</span></span>
<span data-ttu-id="35f1f-103">In diesem Beispiel wird veranschaulicht, wie mehrere sicherheitsbezogene Funktionen eines Windows Communication Foundation (WCF)-Diensts durch steuern:</span><span class="sxs-lookup"><span data-stu-id="35f1f-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
-   <span data-ttu-id="35f1f-104">Das Verschlüsseln von vertraulichen Informationen in der Konfigurationsdatei eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="35f1f-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
-   <span data-ttu-id="35f1f-105">Das Sperren von Elementen in der Konfigurationsdatei, sodass geschachtelte Dienstunterverzeichnisse keine Einstellungen überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="35f1f-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
-   <span data-ttu-id="35f1f-106">Die Steuerung der Protokollierung von personenbezogenen Informationen (PII) in Ablaufverfolgungs- und Nachrichtenprotokollen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35f1f-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="35f1f-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="35f1f-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="35f1f-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35f1f-109">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="35f1f-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35f1f-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35f1f-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="35f1f-111">Diskussion</span><span class="sxs-lookup"><span data-stu-id="35f1f-111">Discussion</span></span>  
 <span data-ttu-id="35f1f-112">Jede dieser Funktionen kann getrennt oder gemeinsam verwendet werden, um Aspekte einer Dienstsicherheit zu steuern.</span><span class="sxs-lookup"><span data-stu-id="35f1f-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="35f1f-113">Dies ist kein endgültiger Leitfaden zur Sicherung eines WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="35f1f-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="35f1f-114">Die .NET Framework-Konfigurationsdateien können vertrauliche Informationen, wie beispielsweise Verbindungszeichenfolgen enthalten, um eine Verbindung mit Datenbanken herzustellen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="35f1f-115">In freigegebenen, im Internet gehosteten Szenarien kann es wünschenswert sein, diese Informationen in der Konfigurationsdatei für einen Dienst zu verschlüsseln, sodass die in der Konfigurationsdatei enthaltenen Daten gegen zufälliges Einsehen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="35f1f-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="35f1f-116">.NET Framework 2.0 und höher kann Teile der Konfigurationsdatei mithilfe von Windows-DPAPI (Data Protection Application Programming Interface) oder dem RSA Cryptographic Provider verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="35f1f-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="35f1f-117">Die Datei "aspnet_regiis.exe" kann mit DPAPI oder RSA ausgewählte Teile einer Konfigurationsdatei verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="35f1f-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="35f1f-118">In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen anderer Dienste zu haben.</span><span class="sxs-lookup"><span data-stu-id="35f1f-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="35f1f-119">Die Standardsemantik für die Bestimmung von Konfigurationswerten ermöglicht es Konfigurationsdateien in den geschachtelten Verzeichnissen, die Konfigurationswerte im übergeordneten Verzeichnis zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="35f1f-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="35f1f-120">In bestimmten Situationen kann dies aus verschiedenen Gründen unerwünscht sein.</span><span class="sxs-lookup"><span data-stu-id="35f1f-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="35f1f-121">WCF-Konfiguration unterstützt das Sperren von Konfigurationswerten, sodass geschachtelte Konfiguration Ausnahmen erzeugt werden, wenn ein geschachtelter Dienst ausgeführt wird, mit überschriebenen Konfigurationswerten.</span><span class="sxs-lookup"><span data-stu-id="35f1f-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="35f1f-122">Dieses Beispiel veranschaulicht das Steuern der Protokollierung von bekannten personenbezogenen Informationen (PII, Personally Identifiable Information) in Ablaufverfolgungs- und Nachrichtenprotokollen, beispielsweise Benutzername und Kennwort.</span><span class="sxs-lookup"><span data-stu-id="35f1f-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="35f1f-123">Standardmäßig ist die Protokollierung von bekannten PII deaktiviert. Allerdings kann in bestimmten Situationen die Protokollierung von PII beim Debuggen einer Anwendung wichtig sein.</span><span class="sxs-lookup"><span data-stu-id="35f1f-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="35f1f-124">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="35f1f-124">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="35f1f-125">In diesem Beispiel werden außerdem Ablaufverfolgungs- und Nachrichtenprotokollierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="35f1f-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="35f1f-126">Weitere Informationen finden Sie unter der [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="35f1f-126">For more information, see the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="35f1f-127">Verschlüsseln von Konfigurationsdateielementen</span><span class="sxs-lookup"><span data-stu-id="35f1f-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="35f1f-128">Aus Sicherheitsgründen kann es in einer freigegebenen Webhostingumgebung wünschenswert sein, bestimmte Konfigurationselemente zu verschlüsseln, wie beispielsweise Datenbankverbindungszeichenfolgen, die vertrauliche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="35f1f-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="35f1f-129">Ein Konfigurationselement kann mit dem Tool aspnet_regiis.exe im .NET Framework-Ordner (z. B. %WINDIR%\Micrsoft.NET\Framework\v4.0.20728) verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="35f1f-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Micrsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="35f1f-130">So verschlüsseln Sie die Werte im Abschnitt appSettings in Web.config für das Beispiel</span><span class="sxs-lookup"><span data-stu-id="35f1f-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1.  <span data-ttu-id="35f1f-131">Öffnen Sie eine Eingabeaufforderung über "Start->Ausführen".</span><span class="sxs-lookup"><span data-stu-id="35f1f-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="35f1f-132">Geben Sie in `cmd` , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="35f1f-132">Type in `cmd` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="35f1f-133">Navigieren Sie zum aktuellen .NET Framework-Verzeichnis, indem Sie folgenden Befehl ausgeben: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span><span class="sxs-lookup"><span data-stu-id="35f1f-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3.  <span data-ttu-id="35f1f-134">Verschlüsseln Sie die appSettings-Konfigurationseinstellungen im Web.config-Ordner, indem Sie folgenden Befehl ausgeben: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span><span class="sxs-lookup"><span data-stu-id="35f1f-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="35f1f-135">Weitere Informationen zum Verschlüsseln von Konfigurationsdateiabschnitten verwendbaren durch Lesen einer Vorgehensweise auf DPAPI in der ASP.NET-Konfiguration ([Building Secure ASP.NET Applications: Authentifizierung, Autorisierung und sichere Kommunikation](http://go.microsoft.com/fwlink/?LinkId=95137)) und eine exemplarische Vorgehensweise für RSA in der ASP.NET-Konfiguration ([Vorgehensweise: Verschlüsseln von Konfigurationsabschnitten in ASP.NET 2.0 mithilfe von RSA](http://go.microsoft.com/fwlink/?LinkId=95138)).</span><span class="sxs-lookup"><span data-stu-id="35f1f-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](http://go.microsoft.com/fwlink/?LinkId=95137)) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](http://go.microsoft.com/fwlink/?LinkId=95138)).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="35f1f-136">Sperren von Konfigurationsdateielementen</span><span class="sxs-lookup"><span data-stu-id="35f1f-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="35f1f-137">In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen von Diensten zu haben.</span><span class="sxs-lookup"><span data-stu-id="35f1f-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="35f1f-138">In diesen Situationen werden die Konfigurationswerte für den Dienst im Unterverzeichnis berechnet durch die Überprüfung von Werten in "Machine.config", darauf folgendes Zusammenfügen mit Web.config-Dateien in übergeordneten Verzeichnissen im Verzeichnisbaum nach unten gehend sowie durch das Zusammenfügen der Web.config-Datei im Verzeichnis, das den Dienst enthält.</span><span class="sxs-lookup"><span data-stu-id="35f1f-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="35f1f-139">Das Standardverhalten der meisten Konfigurationselemente besteht darin, zu erlauben, dass Konfigurationsdateien in Unterverzeichnissen die in den übergeordneten Verzeichnissen gesetzten Werte überschreiben.</span><span class="sxs-lookup"><span data-stu-id="35f1f-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="35f1f-140">In bestimmten Situationen kann es erwünscht sein, dass die Konfigurationsdateien in den Unterverzeichnissen die in der Konfiguration des übergeordneten Verzeichnisses gesetzten Werte nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="35f1f-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="35f1f-141">.NET Framework bietet eine Möglichkeit des Sperrens von Konfigurationsdateielementen, sodass Konfigurationen, die gesperrte Konfigurationselemente überschreiben, Laufzeitausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="35f1f-142">Ein Konfigurationselement kann gesperrt werden, indem das `lockItem`-Attribut für einen Knoten in der Konfigurationsdatei festgelegt wird. Beispielsweise kann die folgende Konfiguration genutzt werden, um einen CalculatorServiceBehavior-Knoten zu sperren, sodass Rechnerdienste in geschachtelten Konfigurationsdateien das Verhalten nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="35f1f-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>   
          <serviceBehaviors>   
             <behavior name="CalculatorServiceBehavior" lockItem="true">   
               <serviceMetadata httpGetEnabled="True"/>   
               <serviceDebug includeExceptionDetailInFaults="False" />   
             </behavior>   
          </serviceBehaviors>   
       </behaviors>   
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="35f1f-143">Konfigurationselemente können individuell gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="35f1f-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="35f1f-144">Als Wert für `lockElements` kann eine Liste von Elementen festgelegt werden, um nur bestimmte Elemente innerhalb einer Auflistung von Unterelementen zu sperren.</span><span class="sxs-lookup"><span data-stu-id="35f1f-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="35f1f-145">Eine Liste an Attributen kann als Wert für `lockAttributes` festgelegt werden, um eine Menge an Attributen innerhalb eines Elements zu sperren.</span><span class="sxs-lookup"><span data-stu-id="35f1f-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="35f1f-146">Eine gesamte Auflistung an Elementen oder Attributen kann mit Ausnahme einer festgelegten Liste gesperrt werden, indem die Attribute `lockAllElementsExcept` oder `lockAllAttributesExcept` auf einem Knoten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="35f1f-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="35f1f-147">Konfiguration von PII-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="35f1f-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="35f1f-148">Die Protokollierung von PII wird über zwei Schalter gesteuert: eine computerweite Einstellung in Machine.config, die es einem Computeradministrator ermöglicht, die Protokollierung von PII zu erlauben oder zu verweigern, und eine Anwendungseinstellung, die es einem Anwendungsadministrator ermöglicht, die Protokollierung von PII für jede Quelle in einer Web.config- oder App.config-Datei ein- bzw. auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="35f1f-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="35f1f-149">Die computerweite Einstellung wird in Machine.config im Abschnitt `enableLoggingKnownPii` mithilfe von `true` gesteuert, indem dieser Wert auf `false` oder `machineSettings` festgelegt wird. Dass Anwendungen die Protokollierung von PII aktivieren wird beispielsweise folgendermaßen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="35f1f-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="35f1f-150">Die Machine.config-Datei hat einen Standardspeicherort: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="35f1f-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="35f1f-151">Ist das `enableLoggingKnownPii`-Attribut nicht in "Machine.config" vorhanden, ist die Protokollierung von PII nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="35f1f-152">Die Aktivierung der Protokollierung von PII für eine Anwendung wird erreicht, indem man das `logKnownPii`-Attribut des Quellelements in der Web.config- oder App.config-Datei auf `true` oder `false` festlegt.</span><span class="sxs-lookup"><span data-stu-id="35f1f-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="35f1f-153">Die Protokollierung von PII sowohl für Nachrichten- als auch für Ablaufverfolgungsprotokollierung wird beispielsweise folgendermaßen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="35f1f-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>   
                ...   
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...   
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="35f1f-154">Wenn das `logKnownPii`-Attribut nicht festgelegt ist, wird PII nicht protokolliert.</span><span class="sxs-lookup"><span data-stu-id="35f1f-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="35f1f-155">PII wird nur protokolliert, wenn sowohl `enableLoggingKnownPii` auf `true` und `logKnownPii` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="35f1f-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35f1f-156">System.Diagnostics ignoriert alle Attribute auf allen Quellen, ausgenommen der zuerst in der Konfigurationsdatei aufgelisteten.</span><span class="sxs-lookup"><span data-stu-id="35f1f-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="35f1f-157">Das Hinzufügen des `logKnownPii`-Attributs zur zweiten Quelle in der Konfigurationsdatei hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35f1f-158">Die Ausführung dieses Beispiels erfordert die manuelle Änderung von "Machine.config". Die Änderung von "Machine.config" sollte vorsichtig vorgenommen werden, da falsche Werte oder Syntax dazu führen können, dass die Ausführung aller .NET Framework-Anwendungen verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="35f1f-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="35f1f-159">Es ist auch möglich, Konfigurationsdateielemente mit DPAPI und RSA zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="35f1f-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="35f1f-160">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="35f1f-160">For more information, see the following links:</span></span>  
  
-   [<span data-ttu-id="35f1f-161">Building Secure ASP.NET Applications: Authentifizierung, Autorisierung und sichere Kommunikation</span><span class="sxs-lookup"><span data-stu-id="35f1f-161">Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication</span></span>](http://go.microsoft.com/fwlink/?LinkId=95137)  
  
-   [<span data-ttu-id="35f1f-162">Gewusst wie: Verschlüsseln von Konfigurationsabschnitten in ASP.NET 2.0 mit RSA</span><span class="sxs-lookup"><span data-stu-id="35f1f-162">How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA</span></span>](http://go.microsoft.com/fwlink/?LinkId=95138)  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="35f1f-163">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="35f1f-163">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="35f1f-164">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35f1f-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="35f1f-165">Bearbeiten Sie "Machine.config", um das `enableLoggingKnownPii`-Attribut auf `true` festzulegen, wobei Sie, falls notwendig, die übergeordneten Knoten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3.  <span data-ttu-id="35f1f-166">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="35f1f-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="35f1f-167">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="35f1f-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="35f1f-168">So bereinigen Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="35f1f-168">To clean up the sample</span></span>  
  
1.  <span data-ttu-id="35f1f-169">Bearbeiten Sie Machine.config, und legen Sie `enableLoggingKnownPii`-Attribut auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="35f1f-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f1f-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35f1f-170">See Also</span></span>  
 [<span data-ttu-id="35f1f-171">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="35f1f-171">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
