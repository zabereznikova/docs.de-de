---
title: Verwenden der Windows-Verwaltungsinstrumentierung für die Diagnose
ms.date: 03/30/2017
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
ms.openlocfilehash: cb015096f9e7cb815e5bd4e4e5487c03fea49bc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267935"
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a><span data-ttu-id="69a27-102">Verwenden der Windows-Verwaltungsinstrumentierung für die Diagnose</span><span class="sxs-lookup"><span data-stu-id="69a27-102">Using Windows Management Instrumentation for Diagnostics</span></span>

<span data-ttu-id="69a27-103">Windows Communication Foundation (WCF) macht Inspektionsdaten eines Dienstanbieters zur Laufzeit über einen WCF-Windows-Verwaltungsinstrumentation (WMI)-Anbieter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69a27-103">Windows Communication Foundation (WCF) exposes inspection data of a service at runtime through a WCF Windows Management Instrumentation (WMI) provider.</span></span>  
  
## <a name="enabling-wmi"></a><span data-ttu-id="69a27-104">Aktivieren von WMI</span><span class="sxs-lookup"><span data-stu-id="69a27-104">Enabling WMI</span></span>  

 <span data-ttu-id="69a27-105">Bei WMI handelt es sich um die Implementierung des Web-Based Enterprise Management (WBEM)-Standards von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69a27-105">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="69a27-106">Weitere Informationen zum WMI-SDK finden Sie unter [Windows-Verwaltungsinstrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="69a27-106">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="69a27-107">Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentation für externe Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="69a27-107">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="69a27-108">Ein WMI-Anbieter ist eine Komponente zum Verfügbarmachen der Instrumentierung zur Laufzeit über eine WBEM-kompatible Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="69a27-108">A WMI provider is a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="69a27-109">Sie besteht aus einer Gruppe von WMI-Objekten mit Attribut/Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="69a27-109">It consists of a set of WMI objects that have attribute/value pairs.</span></span> <span data-ttu-id="69a27-110">Bei den Paaren kann es sich um eine Reihe einfacher Typen handeln.</span><span class="sxs-lookup"><span data-stu-id="69a27-110">Pairs can be of a number of simple types.</span></span> <span data-ttu-id="69a27-111">Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="69a27-111">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="69a27-112">WCF macht Attribute von Diensten verfügbar, z. b. Adressen, Bindungen, Verhaltensweisen und Listener.</span><span class="sxs-lookup"><span data-stu-id="69a27-112">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="69a27-113">Der integrierte WMI-Anbieter kann in der Konfigurationsdatei der Anwendung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-113">The built-in WMI provider can be activated in the configuration file of the application.</span></span> <span data-ttu-id="69a27-114">Dies erfolgt über das- `wmiProviderEnabled` Attribut des [\<diagnostics>](../../../configure-apps/file-schema/wcf/diagnostics.md) im- [\<system.serviceModel>](../../../configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69a27-114">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="69a27-115">Mit diesem Konfigurationseintrag wird eine WMI-Schnittstelle verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="69a27-115">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="69a27-116">Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentierung der Anwendung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-116">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="accessing-wmi-data"></a><span data-ttu-id="69a27-117">Zugreifen auf WMI-Daten</span><span class="sxs-lookup"><span data-stu-id="69a27-117">Accessing WMI Data</span></span>  

 <span data-ttu-id="69a27-118">Der Zugriff auf WMI-Daten kann auf mehrere Arten erfolgen.</span><span class="sxs-lookup"><span data-stu-id="69a27-118">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="69a27-119">Microsoft stellt WMI-APIs für Skripts, Visual Basic Anwendungen, C++-Anwendungen und die .NET Framework bereit.</span><span class="sxs-lookup"><span data-stu-id="69a27-119">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework.</span></span> <span data-ttu-id="69a27-120">Weitere Informationen finden Sie unter [Verwenden von WMI](/windows/win32/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="69a27-120">For more information, see [Using WMI](/windows/win32/wmisdk/using-wmi).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="69a27-121">Bei Verwendung der von .NET Framework bereitgestellten Methoden zum programmgesteuerten Zugreifen auf WMI-Daten ist darauf zu achten, dass von solchen Methoden bei hergestellter Verbindung möglicherweise Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-121">If you use the .NET Framework provided methods to programmatically access WMI data, you should be aware that such methods may throw exceptions when the connection is established.</span></span> <span data-ttu-id="69a27-122">Die Verbindung ist zwar beim Erstellen der <xref:System.Management.ManagementObject>-Instanz nicht hergestellt, dies ändert sich jedoch bei der ersten Anforderung, die einen tatsächlichen Austausch von Daten erfordert.</span><span class="sxs-lookup"><span data-stu-id="69a27-122">The connection is not established during the construction of the <xref:System.Management.ManagementObject> instance, but on the first request involving actual data exchange.</span></span> <span data-ttu-id="69a27-123">Verwenden Sie deshalb zum Abfangen möglicher Ausnahmen einen `try..catch`-Block.</span><span class="sxs-lookup"><span data-stu-id="69a27-123">Therefore, you should use a `try..catch` block to catch the possible exceptions.</span></span>  
  
 <span data-ttu-id="69a27-124">Sie können die Ablaufverfolgungs- und Nachrichtenprotokollierungsebene sowie die Nachrichtenprotokollierungsoptionen für die `System.ServiceModel`-Ablaufverfolgungsquelle in WMI ändern.</span><span class="sxs-lookup"><span data-stu-id="69a27-124">You can change the trace and message logging level, as well as message logging options for the `System.ServiceModel` trace source in WMI.</span></span> <span data-ttu-id="69a27-125">Dies kann durchzugreifen auf die [AppDomainInfo](appdomaininfo.md) -Instanz erfolgen, die diese booleschen Eigenschaften verfügbar macht: `LogMessagesAtServiceLevel` , `LogMessagesAtTransportLevel` , `LogMalformedMessages` und `TraceLevel` .</span><span class="sxs-lookup"><span data-stu-id="69a27-125">This can be done by accessing the [AppDomainInfo](appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, and `TraceLevel`.</span></span> <span data-ttu-id="69a27-126">Wenn Sie einen Ablaufverfolgungslistener für die Nachrichtenprotokollierung konfigurieren, diese Optionen in der Konfiguration jedoch auf `false` festlegen, können Sie sie später, wenn die Anwendung ausgeführt wird, zu `true` ändern.</span><span class="sxs-lookup"><span data-stu-id="69a27-126">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="69a27-127">Dadurch wird die Nachrichtenprotokollierung zur Laufzeit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="69a27-127">This will effectively enable message logging at runtime.</span></span> <span data-ttu-id="69a27-128">Entsprechend können Sie die Nachrichtenprotokollierung zur Laufzeit mit WMI deaktivieren, wenn Sie sie in der Konfigurationsdatei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69a27-128">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span>  
  
 <span data-ttu-id="69a27-129">Sind in der Konfigurationsdatei keine Ablaufverfolgungslistener für die Nachrichtenprotokollierung oder keine `System.ServiceModel`-Ablaufverfolgungslistener angegeben, haben die vorgenommenen Änderungen keinerlei Auswirkungen, obgleich sie von WMI akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-129">You should be aware that if no message logging trace listeners for message logging, or no `System.ServiceModel` trace listeners for tracing are specified in the configuration file, none of your changes are taken into effect, even though the changes are accepted by WMI.</span></span> <span data-ttu-id="69a27-130">Weitere Informationen zum ordnungsgemäßen Einrichten der jeweiligen Listener finden Sie unter [Konfigurieren der Nachrichten Protokollierung](../configuring-message-logging.md) und Konfigurieren der Ablauf [Verfolgung](../tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="69a27-130">For more information on properly setting up the respective listeners, see [Configuring Message Logging](../configuring-message-logging.md) and [Configuring Tracing](../tracing/configuring-tracing.md).</span></span> <span data-ttu-id="69a27-131">Die Ablaufverfolgungsebene aller anderen in der Konfiguration angegebenen Ablaufverfolgungsquellen wird beim Start der Anwendung wirksam und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-131">The trace level of all other trace sources specified by configuration is effective when the application starts, and cannot be changed.</span></span>  
  
 <span data-ttu-id="69a27-132">WCF macht eine `GetOperationCounterInstanceName` Methode für die Skripterstellung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69a27-132">WCF exposes a `GetOperationCounterInstanceName` method for scripting.</span></span> <span data-ttu-id="69a27-133">Wird die Methode mit einem Vorgangsnamen angegeben, wird der Name einer Leistungsindikatorinstanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69a27-133">This method returns a performance counter instance name if you provide it with an operation name.</span></span> <span data-ttu-id="69a27-134">Die Eingabe wird jedoch nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="69a27-134">However, it does not validate your input.</span></span> <span data-ttu-id="69a27-135">Aus diesem Grund wird bei Angabe eines falschen Vorgangsnamens auch ein falscher Indikatorname zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69a27-135">Therefore, if you provide an incorrect operation name, an incorrect counter name is returned.</span></span>  
  
 <span data-ttu-id="69a27-136">Die- `OutgoingChannel` Eigenschaft der- `Service` Instanz zählt keine Kanäle, die von einem Dienst zum Herstellen einer Verbindung mit einem anderen Dienst geöffnet wurden, wenn der WCF-Client für den Ziel Dienst nicht innerhalb der-Methode erstellt wird `Service` .</span><span class="sxs-lookup"><span data-stu-id="69a27-136">The `OutgoingChannel` property of the `Service` instance does not count channels opened by a service to connect to another service, if the WCF client to the destination service is not created within the `Service` method.</span></span>  
  
 <span data-ttu-id="69a27-137">**Vorsicht** WMI unterstützt nur einen <xref:System.TimeSpan> Wert von bis zu 3 Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="69a27-137">**Caution** WMI only supports a <xref:System.TimeSpan> value up to 3 decimal points.</span></span> <span data-ttu-id="69a27-138">Beispiel: Wird eine der Eigenschaften des Diensts auf  festgelegt, wird der Wert beim Anzeigen in WMI nach 3Dezimalstellen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="69a27-138">For example, if your service sets one of its properties to <xref:System.TimeSpan.MaxValue>, its value is truncated after 3 decimal points when viewed through WMI.</span></span>  
  
## <a name="security"></a><span data-ttu-id="69a27-139">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="69a27-139">Security</span></span>  

 <span data-ttu-id="69a27-140">Da der WCF-WMI-Anbieter die Ermittlung von Diensten in einer Umgebung zulässt, sollten Sie bei der Gewährung des Zugriffs auf die Anwendung äußerst vorsichtig vorgehen.</span><span class="sxs-lookup"><span data-stu-id="69a27-140">Because the WCF WMI provider allows the discovery of services in an environment, you should exercise extreme caution for granting access to it.</span></span> <span data-ttu-id="69a27-141">Durch Lockern des standardmäßig auf Administratoren beschränkten Zugriffs erhalten möglicherweise weniger vertrauenswürdige Parteien Zugriff auf sensible Daten der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="69a27-141">If you relax the default administrator-only access, you may allow less-trusted parties access to sensitive data in your environment.</span></span> <span data-ttu-id="69a27-142">Genauer gesagt: Durch eine Lockerung der Berechtigungen für den Remote-WMI-Zugriff erhöht sich das Risiko für Überlastungsangriffe.</span><span class="sxs-lookup"><span data-stu-id="69a27-142">Specifically, if you loosen permissions on remote WMI access, flooding attacks can occur.</span></span> <span data-ttu-id="69a27-143">Wird ein Prozess von einer Vielzahl von WMI-Anforderungen regelrecht überschwemmt, hat dies eine Beeinträchtigung der Leistung zur Folge.</span><span class="sxs-lookup"><span data-stu-id="69a27-143">If a process is flooded by excessive WMI requests, its performance can be degraded.</span></span>  
  
 <span data-ttu-id="69a27-144">Werden die Zugriffsberechtigungen für die MOF-Datei gelockert, haben weniger vertrauenswürdige Parteien die Möglichkeit zum Manipulieren des WMI-Verhaltens sowie zum Ändern der im WMI-Schema geladenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="69a27-144">In addition, if you relax access permissions for the MOF file, less-trusted parties can manipulate the behavior of WMI and alter the objects that are loaded in the WMI schema.</span></span> <span data-ttu-id="69a27-145">So können beispielsweise Felder entfernt werden, was dazu führen kann, dass dem Administrator wichtige Daten nicht mehr zur Verfügung stehen oder der Datei Felder hinzugefügt werden, die nicht ausgefüllt werden oder Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="69a27-145">For example, fields can be removed such that critical data is concealed from the administrator or that fields that do not populate or cause exceptions are added to the file.</span></span>  
  
 <span data-ttu-id="69a27-146">Standardmäßig erteilt der WCF-WMI-Anbieter die Berechtigung "Execute Method", "Provider Write" und "Enable Account" für den Administrator, und die Berechtigung "Konto aktivieren" für ASP.net, lokaler Dienst und Netzwerkdienst.</span><span class="sxs-lookup"><span data-stu-id="69a27-146">By default, the WCF WMI provider grants "execute method", "provider write", and "enable account" permission for Administrator, and "enable account" permission for ASP.NET, Local Service and Network Service.</span></span> <span data-ttu-id="69a27-147">Insbesondere auf nicht-Windows Vista-Plattformen verfügt das ASP.NET-Konto über Lesezugriff auf den WMI Service Model-Namespace.</span><span class="sxs-lookup"><span data-stu-id="69a27-147">In particular, on non-Windows Vista platforms, the ASP.NET account has read access to the WMI ServiceModel namespace.</span></span> <span data-ttu-id="69a27-148">Sollen diese Rechte einer bestimmten Benutzergruppe vorenthalten werden, deaktivieren Sie entweder den WMI-Anbieter (ist standardmäßig deaktiviert), oder deaktivieren Sie den Zugriff für die gewünschte Benutzergruppe.</span><span class="sxs-lookup"><span data-stu-id="69a27-148">If you do not want to grant these privileges to a particular user group, you should either deactivate the WMI provider (it is disabled by default), or disable access for the specific user group.</span></span>  
  
 <span data-ttu-id="69a27-149">Darüber hinaus kann WMI beim Versuch, WMI mithilfe der Konfiguration zu aktivieren, möglicherweise aufgrund unzureichender Benutzerberechtigungen nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-149">In addition, when you attempt to enable WMI through configuration, WMI may not be enabled due to insufficient user privilege.</span></span> <span data-ttu-id="69a27-150">Es wird jedoch kein Ereignis in das Ereignisprotokoll aufgenommen, um diesen Fehler zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="69a27-150">However, no event is written to the event log to record this failure.</span></span>  
  
 <span data-ttu-id="69a27-151">Gehen Sie zum Ändern der Benutzerberechtigungsebenen folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="69a27-151">To modify user privilege levels, use the following steps.</span></span>  
  
1. <span data-ttu-id="69a27-152">Klicken Sie auf Start und dann auf Ausführen, und geben Sie **compmgmt. msc** ein.</span><span class="sxs-lookup"><span data-stu-id="69a27-152">Click Start and then Run and type **compmgmt.msc**.</span></span>  
  
2. <span data-ttu-id="69a27-153">Klicken Sie mit der rechten Maustaste auf **Dienste und Anwendungen/WMI-Steuerelemente** , um **Eigenschaften** auszuwählen</span><span class="sxs-lookup"><span data-stu-id="69a27-153">Right-click **Services and Application/WMI Controls** to select **Properties**.</span></span>  
  
3. <span data-ttu-id="69a27-154">Wählen Sie die Registerkarte **Sicherheit** aus, und navigieren Sie zum Namespace **root/Service Model** .</span><span class="sxs-lookup"><span data-stu-id="69a27-154">Select the **Security** Tab, and navigate to the **Root/ServiceModel** namespace.</span></span> <span data-ttu-id="69a27-155">Klicken Sie auf die Schaltfläche **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="69a27-155">Click the **Security** button.</span></span>  
  
4. <span data-ttu-id="69a27-156">Wählen Sie die Gruppe oder den Benutzer aus, für die Sie den Zugriff steuern möchten, und verwenden Sie das Kontrollkästchen **zulassen** oder **verweigern** , um Berechtigungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="69a27-156">Select the specific group or user that you want to control access and use the **Allow** or **Deny** checkbox to configure permissions.</span></span>  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a><span data-ttu-id="69a27-157">Gewähren von WCF WMI-Registrierungsberechtigungen für zusätzliche Benutzer</span><span class="sxs-lookup"><span data-stu-id="69a27-157">Granting WCF WMI Registration Permissions to Additional Users</span></span>  

 <span data-ttu-id="69a27-158">WCF macht Verwaltungsdaten für WMI verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69a27-158">WCF exposes management data to WMI.</span></span> <span data-ttu-id="69a27-159">Dies erfolgt durch das Hosting eines Prozess internen WMI-Anbieters, der manchmal als "entkoppelter Anbieter" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="69a27-159">It does so by hosting an in-process WMI provider, sometimes called a "decoupled provider".</span></span> <span data-ttu-id="69a27-160">Damit die Verwaltungsdaten verfügbar gemacht werden können, muss das Konto, das diesen Anbieter registriert, über die erforderlichen Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="69a27-160">For the management data to be exposed, the account that registers this provider must have the appropriate permissions.</span></span> <span data-ttu-id="69a27-161">Unter Windows kann standardmäßig nur eine kleine Gruppe von berechtigten Konten entkoppelte Anbieter registrieren.</span><span class="sxs-lookup"><span data-stu-id="69a27-161">In Windows, only a small set of privileged accounts can register decoupled providers by default.</span></span> <span data-ttu-id="69a27-162">Dies ist ein Problem, da Benutzer im Allgemeinen die WMI-Daten von einem WCF-Dienst verfügbar machen möchten, der unter einem Konto ausgeführt wird, das nicht im Standardsatz enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="69a27-162">This is a problem because users commonly want to expose WMI data from a WCF service running under an account that is not in the default set.</span></span>  
  
 <span data-ttu-id="69a27-163">Um diesen Zugriff bereitzustellen, muss ein Administrator den zusätzlichen Konten die folgenden Berechtigungen in der angegebenen Reihenfolge erteilen:</span><span class="sxs-lookup"><span data-stu-id="69a27-163">To provide this access, an administrator must grant the following permissions to the additional account in the following order:</span></span>  
  
1. <span data-ttu-id="69a27-164">Berechtigung für den Zugriff auf den WCF WMI-Namespace.</span><span class="sxs-lookup"><span data-stu-id="69a27-164">Permission to access to the WCF WMI Namespace.</span></span>  
  
2. <span data-ttu-id="69a27-165">Berechtigung zum Registrieren des entkoppelten WCF WMI-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="69a27-165">Permission to register the WCF Decoupled WMI Provider.</span></span>  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a><span data-ttu-id="69a27-166">So gewähren Sie eine Zugriffsberechtigung für den WMI-Namespace</span><span class="sxs-lookup"><span data-stu-id="69a27-166">To grant WMI namespace access permission</span></span>  
  
1. <span data-ttu-id="69a27-167">Führen Sie das folgende PowerShell-Skript aus.</span><span class="sxs-lookup"><span data-stu-id="69a27-167">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     <span data-ttu-id="69a27-168">Dieses PowerShell-Skript verwendet die Security Descriptor Definition Language (SDDL), um der Built-In Benutzergruppe Zugriff auf den WMI-Namespace "root/Service Model" zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="69a27-168">This PowerShell script uses Security Descriptor Definition Language (SDDL) to grant the Built-In Users group access to the "root/servicemodel" WMI namespace.</span></span> <span data-ttu-id="69a27-169">Folgende ACLs werden angegeben:</span><span class="sxs-lookup"><span data-stu-id="69a27-169">It specifies the following ACLs:</span></span>  
  
    - <span data-ttu-id="69a27-170">Integriertes Administratorkonto (Built-In Administrator, BA) - Hatte bereits Zugriff.</span><span class="sxs-lookup"><span data-stu-id="69a27-170">Built-In Administrator (BA) - Already Had Access.</span></span>  
  
    - <span data-ttu-id="69a27-171">Netzwerkdienst (Network Service, NS) - Hatte bereits Zugriff.</span><span class="sxs-lookup"><span data-stu-id="69a27-171">Network Service (NS) - Already Had Access.</span></span>  
  
    - <span data-ttu-id="69a27-172">Lokales Systemkonto (Local System, LS) - Hatte bereits Zugriff.</span><span class="sxs-lookup"><span data-stu-id="69a27-172">Local System (LS) - Already Had Access.</span></span>  
  
    - <span data-ttu-id="69a27-173">Integrierte Gruppe "Benutzer" - Die Gruppe, für die der Zugriff erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="69a27-173">Built-In Users - The group to grant access to.</span></span>  
  
#### <a name="to-grant-provider-registration-access"></a><span data-ttu-id="69a27-174">So gewähren Sie Zugriff für die Anbieterregistrierung</span><span class="sxs-lookup"><span data-stu-id="69a27-174">To grant provider registration access</span></span>  
  
1. <span data-ttu-id="69a27-175">Führen Sie das folgende PowerShell-Skript aus.</span><span class="sxs-lookup"><span data-stu-id="69a27-175">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a><span data-ttu-id="69a27-176">Gewähren von Zugriff für beliebige Benutzer oder Gruppen</span><span class="sxs-lookup"><span data-stu-id="69a27-176">Granting Access to Arbitrary Users or Groups</span></span>  

 <span data-ttu-id="69a27-177">Mit dem Beispiel in diesem Abschnitt werden allen lokalen Benutzern Berechtigungen für die WMI-Anbieterregistrierung gewährt.</span><span class="sxs-lookup"><span data-stu-id="69a27-177">The example in this section grants WMI Provider registration privileges to all local users.</span></span> <span data-ttu-id="69a27-178">Wenn Sie einem Benutzer oder einer Gruppe, der nicht integriert ist, Zugriff gewähren möchten, müssen Sie den Benutzer oder die Sicherheits-ID (SID) des Benutzers oder der Gruppe abrufen.</span><span class="sxs-lookup"><span data-stu-id="69a27-178">If you want to grant access to a user or group that is not built in, then you must obtain that user or group's Security Identifier (SID).</span></span> <span data-ttu-id="69a27-179">Es gibt keine einfache Möglichkeit, die SID für einen beliebigen Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="69a27-179">There is no simple way to get the SID for an arbitrary user.</span></span> <span data-ttu-id="69a27-180">Eine Methode besteht darin, sich als der gewünschte Benutzer anzumelden und dann den folgenden Shellbefehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="69a27-180">One method is to log on as the desired user and then issue the following shell command.</span></span>  
  
```console
Whoami /user  
```  
  
 <span data-ttu-id="69a27-181">Dieser Befehl stellt die SID des aktuellen Benutzers bereit, aber diese Methode kann nicht verwendet werden, um die SID für einen beliebigen Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="69a27-181">This provides the SID of the current user, but this method cannot be used to get the SID on any arbitrary user.</span></span> <span data-ttu-id="69a27-182">Eine weitere Methode zum erhalten der SID ist die Verwendung des [getsid.exe](/windows/win32/wmisdk/using-wmi) Tools aus den Windows 2000 Resource Kit-Tools für administrative Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="69a27-182">Another method to get the SID is to use the [getsid.exe](/windows/win32/wmisdk/using-wmi) tool from the Windows 2000 Resource Kit Tools for administrative tasks.</span></span> <span data-ttu-id="69a27-183">Dieses Tool vergleicht die SID von zwei Benutzern (lokal oder Domäne) und gibt als Nebeneffekt die beiden SIDs in der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="69a27-183">This tool compares the SID of two users (local or domain), and as a side effect prints the two SIDs to the command line.</span></span> <span data-ttu-id="69a27-184">Weitere Informationen finden Sie unter [Bekannte SIDs](https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="69a27-184">For more information, see [Well Known SIDs](https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems).</span></span>  
  
## <a name="accessing-remote-wmi-object-instances"></a><span data-ttu-id="69a27-185">Zugreifen auf Remote-WMI-Objektinstanzen</span><span class="sxs-lookup"><span data-stu-id="69a27-185">Accessing Remote WMI Object Instances</span></span>  

 <span data-ttu-id="69a27-186">Wenn Sie auf WCF-WMI-Instanzen auf einem Remote Computer zugreifen müssen, müssen Sie den Paket Datenschutz für die Tools aktivieren, die Sie für den Zugriff verwenden.</span><span class="sxs-lookup"><span data-stu-id="69a27-186">If you need to access WCF WMI instances on a remote machine, you must enable packet privacy on the tools that you use for access.</span></span> <span data-ttu-id="69a27-187">Im folgenden Abschnitt wird die hierzu erforderliche Vorgehensweise für WMI CIM Studio, das Testprogramm für Windows-Verwaltungsinstrumentation und .NET SDK 2.0 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69a27-187">The following section describes how to achieve these using the WMI CIM Studio, Windows Management Instrumentation Tester, as well as .NET SDK 2.0.</span></span>  
  
### <a name="wmi-cim-studio"></a><span data-ttu-id="69a27-188">WMI CIM Studio</span><span class="sxs-lookup"><span data-stu-id="69a27-188">WMI CIM Studio</span></span>

<span data-ttu-id="69a27-189">Wenn Sie die WMI-Verwaltungs Tools installiert haben, können Sie den WMI-CIM-Studio für den Zugriff auf WMI-Instanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="69a27-189">If you've installed WMI Administrative Tools, you can use the WMI CIM Studio to access WMI instances.</span></span> <span data-ttu-id="69a27-190">Die Tools befinden sich im folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="69a27-190">The tools are in the following folder:</span></span>
  
<span data-ttu-id="69a27-191">*%windir%\Programme\WMI Tools\\*</span><span class="sxs-lookup"><span data-stu-id="69a27-191">*%windir%\Program Files\WMI Tools\\*</span></span>
  
1. <span data-ttu-id="69a27-192">Geben Sie im Fenster mit **Namespace verbinden:** **root\ServiceModel** ein, und klicken Sie auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="69a27-192">In the **Connect to namespace:** window, type **root\ServiceModel** and click **OK.**</span></span>  
  
2. <span data-ttu-id="69a27-193">Klicken Sie im Anmeldefenster für **WMI CIM Studio** auf die Schaltfläche **Optionen >>** , um das Fenster zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="69a27-193">In the **WMI CIM Studio Login** window, click the **Options >>** button to expand the window.</span></span> <span data-ttu-id="69a27-194">Wählen Sie für **Authentifizierungs Ebene** die Option **Paket** Sicherheit aus, und klicken Sie auf **OK**</span><span class="sxs-lookup"><span data-stu-id="69a27-194">Select **Packet privacy** for **Authentication level**, and click **OK**.</span></span>  
  
### <a name="windows-management-instrumentation-tester"></a><span data-ttu-id="69a27-195">Testprogramm für Windows-Verwaltungsinstrumentation</span><span class="sxs-lookup"><span data-stu-id="69a27-195">Windows Management Instrumentation Tester</span></span>  

 <span data-ttu-id="69a27-196">Dieses Tool wird von Windows installiert.</span><span class="sxs-lookup"><span data-stu-id="69a27-196">This tool is installed by Windows.</span></span> <span data-ttu-id="69a27-197">Um es auszuführen, starten Sie eine Befehlskonsole, indem Sie im Dialogfeld **Start/ausführen** **cmd.exe** eingeben und auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="69a27-197">To run it, launch a command console by typing **cmd.exe** in the **Start/Run** dialog box and click **OK**.</span></span> <span data-ttu-id="69a27-198">Geben Sie dann **wbemtest.exe** in das Befehlsfenster ein.</span><span class="sxs-lookup"><span data-stu-id="69a27-198">Then, type **wbemtest.exe** in the command window.</span></span> <span data-ttu-id="69a27-199">Das Testprogramm für Windows-Verwaltungsinstrumentierung wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="69a27-199">The Windows Management Instrumentation Tester tool is then launched.</span></span>  
  
1. <span data-ttu-id="69a27-200">Klicken Sie in der oberen rechten Ecke des Fensters auf die Schaltfläche **verbinden** .</span><span class="sxs-lookup"><span data-stu-id="69a27-200">Click the **Connect** button on the top right corner of the window.</span></span>  
  
2. <span data-ttu-id="69a27-201">Geben Sie im neuen Fenster im Feld **Namespace** den Namen **root\ServiceModel** ein, und wählen Sie für **Authentifizierungs Ebene** die Option **Paket Datenschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="69a27-201">In the new window, enter **root\ServiceModel** for the **Namespace** field, and select **Packet privacy** for **Authentication level**.</span></span> <span data-ttu-id="69a27-202">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="69a27-202">Click **Connect**.</span></span>  
  
### <a name="using-managed-code"></a><span data-ttu-id="69a27-203">Verwenden von verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="69a27-203">Using Managed Code</span></span>  

 <span data-ttu-id="69a27-204">Der Zugriff auf Remote-WMI-Instanzen kann auch programmgesteuert erfolgen. Verwenden Sie hierzu die vom <xref:System.Management>-Namespace bereitgestellten Klassen.</span><span class="sxs-lookup"><span data-stu-id="69a27-204">You can also access remote WMI instances programmatically by using classes provided by the <xref:System.Management> namespace.</span></span> <span data-ttu-id="69a27-205">Die erforderliche Vorgehensweise wird im folgenden Codebeispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="69a27-205">The following code sample demonstrates how to do this.</span></span>  
  
```csharp
String wcfNamespace = $@"\\{this.serviceMachineName}\Root\ServiceModel");
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
