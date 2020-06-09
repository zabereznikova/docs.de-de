---
title: Sperre der PII-Sicherheit
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: 64c07825f0756b029781e173eb2098711cdbe60a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600476"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="d6798-102">Sperre der PII-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d6798-102">PII Security Lockdown</span></span>
<span data-ttu-id="d6798-103">In diesem Beispiel wird veranschaulicht, wie Sie verschiedene sicherheitsrelevante Features eines Windows Communication Foundation (WCF)-Diensts wie folgt steuern:</span><span class="sxs-lookup"><span data-stu-id="d6798-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
- <span data-ttu-id="d6798-104">Das Verschlüsseln von vertraulichen Informationen in der Konfigurationsdatei eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="d6798-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
- <span data-ttu-id="d6798-105">Das Sperren von Elementen in der Konfigurationsdatei, sodass geschachtelte Dienstunterverzeichnisse keine Einstellungen überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="d6798-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
- <span data-ttu-id="d6798-106">Die Steuerung der Protokollierung von personenbezogenen Informationen (PII) in Ablaufverfolgungs- und Nachrichtenprotokollen.</span><span class="sxs-lookup"><span data-stu-id="d6798-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d6798-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d6798-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d6798-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d6798-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d6798-109">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6798-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d6798-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d6798-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="d6798-111">Diskussion</span><span class="sxs-lookup"><span data-stu-id="d6798-111">Discussion</span></span>  
 <span data-ttu-id="d6798-112">Jede dieser Funktionen kann getrennt oder gemeinsam verwendet werden, um Aspekte einer Dienstsicherheit zu steuern.</span><span class="sxs-lookup"><span data-stu-id="d6798-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="d6798-113">Dies ist keine definitive Anleitung zum Sichern eines WCF-Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="d6798-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="d6798-114">Die .NET Framework-Konfigurationsdateien können vertrauliche Informationen, wie beispielsweise Verbindungszeichenfolgen enthalten, um eine Verbindung mit Datenbanken herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6798-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="d6798-115">In freigegebenen, im Internet gehosteten Szenarien kann es wünschenswert sein, diese Informationen in der Konfigurationsdatei für einen Dienst zu verschlüsseln, sodass die in der Konfigurationsdatei enthaltenen Daten gegen zufälliges Einsehen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="d6798-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="d6798-116">.NET Framework 2.0 und höher kann Teile der Konfigurationsdatei mithilfe von Windows-DPAPI (Data Protection Application Programming Interface) oder dem RSA Cryptographic Provider verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d6798-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="d6798-117">Die Datei "aspnet_regiis.exe" kann mit DPAPI oder RSA ausgewählte Teile einer Konfigurationsdatei verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d6798-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="d6798-118">In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen anderer Dienste zu haben.</span><span class="sxs-lookup"><span data-stu-id="d6798-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="d6798-119">Die Standardsemantik für die Bestimmung von Konfigurationswerten ermöglicht es Konfigurationsdateien in den geschachtelten Verzeichnissen, die Konfigurationswerte im übergeordneten Verzeichnis zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d6798-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="d6798-120">In bestimmten Situationen kann dies aus verschiedenen Gründen unerwünscht sein.</span><span class="sxs-lookup"><span data-stu-id="d6798-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="d6798-121">Die WCF-Dienst Konfiguration unterstützt das Sperren von Konfigurations Werten, sodass beim Ausführen eines unterstützten Konfigurations Werts bei der Verwendung eines unterstützten Dienstanbieter Ausnahmen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6798-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="d6798-122">Dieses Beispiel veranschaulicht das Steuern der Protokollierung von bekannten personenbezogenen Informationen (PII, Personally Identifiable Information) in Ablaufverfolgungs- und Nachrichtenprotokollen, beispielsweise Benutzername und Kennwort.</span><span class="sxs-lookup"><span data-stu-id="d6798-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="d6798-123">Standardmäßig ist die Protokollierung von bekannten PII deaktiviert. Allerdings kann in bestimmten Situationen die Protokollierung von PII beim Debuggen einer Anwendung wichtig sein.</span><span class="sxs-lookup"><span data-stu-id="d6798-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="d6798-124">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="d6798-124">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="d6798-125">In diesem Beispiel werden außerdem Ablaufverfolgungs- und Nachrichtenprotokollierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6798-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="d6798-126">Weitere Informationen finden Sie im Beispiel Ablauf [Verfolgung und Nachrichten Protokollierung](tracing-and-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="d6798-126">For more information, see the [Tracing and Message Logging](tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="d6798-127">Verschlüsseln von Konfigurationsdateielementen</span><span class="sxs-lookup"><span data-stu-id="d6798-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="d6798-128">Aus Sicherheitsgründen kann es in einer freigegebenen Webhostingumgebung wünschenswert sein, bestimmte Konfigurationselemente zu verschlüsseln, wie beispielsweise Datenbankverbindungszeichenfolgen, die vertrauliche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6798-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="d6798-129">Ein Konfigurationselement kann mit dem Tool "Aspnet_regiis. exe" im Ordner ".NET Framework" verschlüsselt werden, z. b .%windir%\Microsoft.Net\Framework\v4.0.20728.</span><span class="sxs-lookup"><span data-stu-id="d6798-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="d6798-130">So verschlüsseln Sie die Werte im Abschnitt appSettings in Web.config für das Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6798-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1. <span data-ttu-id="d6798-131">Öffnen Sie eine Eingabeaufforderung mithilfe von Start->Run....</span><span class="sxs-lookup"><span data-stu-id="d6798-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="d6798-132">Geben Sie ein, `cmd` und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6798-132">Type in `cmd` and click **OK**.</span></span>  
  
2. <span data-ttu-id="d6798-133">Navigieren Sie zum aktuellen .NET Framework-Verzeichnis, indem Sie folgenden Befehl ausgeben: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span><span class="sxs-lookup"><span data-stu-id="d6798-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3. <span data-ttu-id="d6798-134">Verschlüsseln Sie die appSettings-Konfigurationseinstellungen im Web.config-Ordner, indem Sie folgenden Befehl ausgeben: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span><span class="sxs-lookup"><span data-stu-id="d6798-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="d6798-135">Weitere Informationen zum Verschlüsseln von Abschnitten von Konfigurationsdateien finden Sie unter Vorgehensweise bei DPAPI in der ASP.NET-Konfiguration (entwickeln von[sicheren ASP.NET-Anwendungen: Authentifizierung, Autorisierung und sichere Kommunikation](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) und in einer Vorgehensweise bei RSA in ASP.net Configuration (Gewusst[wie: Verschlüsseln von Konfigurations Abschnitten in ASP.NET 2,0 mit RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span><span class="sxs-lookup"><span data-stu-id="d6798-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="d6798-136">Sperren von Konfigurationsdateielementen</span><span class="sxs-lookup"><span data-stu-id="d6798-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="d6798-137">In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen von Diensten zu haben.</span><span class="sxs-lookup"><span data-stu-id="d6798-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="d6798-138">In diesen Situationen werden die Konfigurationswerte für den Dienst im Unterverzeichnis berechnet durch die Überprüfung von Werten in "Machine.config", darauf folgendes Zusammenfügen mit Web.config-Dateien in übergeordneten Verzeichnissen im Verzeichnisbaum nach unten gehend sowie durch das Zusammenfügen der Web.config-Datei im Verzeichnis, das den Dienst enthält.</span><span class="sxs-lookup"><span data-stu-id="d6798-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="d6798-139">Das Standardverhalten der meisten Konfigurationselemente besteht darin, zu erlauben, dass Konfigurationsdateien in Unterverzeichnissen die in den übergeordneten Verzeichnissen gesetzten Werte überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d6798-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="d6798-140">In bestimmten Situationen kann es erwünscht sein, dass die Konfigurationsdateien in den Unterverzeichnissen die in der Konfiguration des übergeordneten Verzeichnisses gesetzten Werte nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d6798-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="d6798-141">.NET Framework bietet eine Möglichkeit des Sperrens von Konfigurationsdateielementen, sodass Konfigurationen, die gesperrte Konfigurationselemente überschreiben, Laufzeitausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="d6798-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="d6798-142">Ein Konfigurationselement kann gesperrt werden, indem das `lockItem`-Attribut für einen Knoten in der Konfigurationsdatei festgelegt wird. Beispielsweise kann die folgende Konfiguration genutzt werden, um einen CalculatorServiceBehavior-Knoten zu sperren, sodass Rechnerdienste in geschachtelten Konfigurationsdateien das Verhalten nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="d6798-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
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
  
 <span data-ttu-id="d6798-143">Konfigurationselemente können individuell gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="d6798-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="d6798-144">Als Wert für `lockElements` kann eine Liste von Elementen festgelegt werden, um nur bestimmte Elemente innerhalb einer Auflistung von Unterelementen zu sperren.</span><span class="sxs-lookup"><span data-stu-id="d6798-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="d6798-145">Eine Liste an Attributen kann als Wert für `lockAttributes` festgelegt werden, um eine Menge an Attributen innerhalb eines Elements zu sperren.</span><span class="sxs-lookup"><span data-stu-id="d6798-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="d6798-146">Eine gesamte Auflistung an Elementen oder Attributen kann mit Ausnahme einer festgelegten Liste gesperrt werden, indem die Attribute `lockAllElementsExcept` oder `lockAllAttributesExcept` auf einem Knoten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d6798-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="d6798-147">Konfiguration von PII-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="d6798-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="d6798-148">Die Protokollierung von PII wird über zwei Schalter gesteuert: eine computerweite Einstellung in Machine.config, die es einem Computeradministrator ermöglicht, die Protokollierung von PII zu erlauben oder zu verweigern, und eine Anwendungseinstellung, die es einem Anwendungsadministrator ermöglicht, die Protokollierung von PII für jede Quelle in einer Web.config- oder App.config-Datei ein- bzw. auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="d6798-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="d6798-149">Die Computer weite Einstellung wird gesteuert `enableLoggingKnownPii` , indem auf `true` oder im- `false` `machineSettings` Element in Machine. config festgelegt wird. Mit dem folgenden Beispiel können Anwendungen die Protokollierung von PII aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6798-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="d6798-150">Die Machine.config-Datei hat einen Standardspeicherort: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="d6798-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="d6798-151">Ist das `enableLoggingKnownPii`-Attribut nicht in "Machine.config" vorhanden, ist die Protokollierung von PII nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="d6798-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="d6798-152">Die Aktivierung der Protokollierung von PII für eine Anwendung wird erreicht, indem man das `logKnownPii`-Attribut des Quellelements in der Web.config- oder App.config-Datei auf `true` oder `false` festlegt.</span><span class="sxs-lookup"><span data-stu-id="d6798-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="d6798-153">Die Protokollierung von PII sowohl für Nachrichten- als auch für Ablaufverfolgungsprotokollierung wird beispielsweise folgendermaßen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d6798-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
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
  
 <span data-ttu-id="d6798-154">Wenn das `logKnownPii`-Attribut nicht festgelegt ist, wird PII nicht protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d6798-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="d6798-155">PII wird nur protokolliert, wenn sowohl `enableLoggingKnownPii` auf `true` und `logKnownPii` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d6798-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6798-156">System.Diagnostics ignoriert alle Attribute auf allen Quellen, ausgenommen der zuerst in der Konfigurationsdatei aufgelisteten.</span><span class="sxs-lookup"><span data-stu-id="d6798-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="d6798-157">Das Hinzufügen des `logKnownPii`-Attributs zur zweiten Quelle in der Konfigurationsdatei hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d6798-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d6798-158">Zum Ausführen dieses Beispiels gehört die manuelle Änderung von "Machine. config". Wenn Sie "Machine. config" ändern, sollten Sie beim Ändern von "Machine. config" darauf achten, dass alle .NET Framework Anwendungen nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6798-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="d6798-159">Es ist auch möglich, Konfigurationsdateielemente mit DPAPI und RSA zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d6798-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="d6798-160">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="d6798-160">For more information, see the following links:</span></span>  
  
- <span data-ttu-id="d6798-161">[Aufbauen von sicheren ASP.NET-Anwendungen: Authentifizierung, Autorisierung und sichere Kommunikation](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="d6798-161">[Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span></span>  
  
- <span data-ttu-id="d6798-162">[Gewusst wie: Verschlüsseln von Konfigurationsabschnitten in ASP.NET 2.0 mithilfe von RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="d6798-162">[How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d6798-163">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="d6798-163">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="d6798-164">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d6798-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d6798-165">Bearbeiten Sie "Machine.config", um das `enableLoggingKnownPii`-Attribut auf `true` festzulegen, wobei Sie, falls notwendig, die übergeordneten Knoten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6798-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3. <span data-ttu-id="d6798-166">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d6798-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="d6798-167">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d6798-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="d6798-168">So bereinigen Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6798-168">To clean up the sample</span></span>  
  
1. <span data-ttu-id="d6798-169">Bearbeiten Sie Machine.config, und legen Sie `enableLoggingKnownPii`-Attribut auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="d6798-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6798-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6798-170">See also</span></span>

- <span data-ttu-id="d6798-171">[AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d6798-171">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
