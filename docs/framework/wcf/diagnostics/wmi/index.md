---
title: Verwenden der Windows-Verwaltungsinstrumentierung für die Diagnose
ms.date: 03/30/2017
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
ms.openlocfilehash: 26758c8a4f537f9522d5ab650ae6b3cd8f044db2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837440"
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a>Verwenden der Windows-Verwaltungsinstrumentierung für die Diagnose
Windows Communication Foundation (WCF) macht Inspektionsdaten eines Dienstanbieters zur Laufzeit über einen WCF-Windows-Verwaltungsinstrumentation (WMI)-Anbieter verfügbar.  
  
## <a name="enabling-wmi"></a>Aktivieren von WMI  
 Bei WMI handelt es sich um die Implementierung des Web-Based Enterprise Management (WBEM)-Standards von Microsoft. Weitere Informationen zum WMI-SDK finden Sie unter [Windows-Verwaltungsinstrumentation](/windows/desktop/WmiSdk/wmi-start-page). Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentation für externe Verwaltungstools.  
  
 Ein WMI-Anbieter ist eine Komponente zum Verfügbarmachen der Instrumentierung zur Laufzeit über eine WBEM-kompatible Schnittstelle. Sie besteht aus einer Gruppe von WMI-Objekten mit Attribut/Wert-Paaren. Bei den Paaren kann es sich um eine Reihe einfacher Typen handeln. Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen. WCF macht Attribute von Diensten verfügbar, z. b. Adressen, Bindungen, Verhaltensweisen und Listener.  
  
 Der integrierte WMI-Anbieter kann in der Konfigurationsdatei der Anwendung aktiviert werden. Dies erfolgt über das `wmiProviderEnabled`-Attribut der [\<Diagnose >](../../../configure-apps/file-schema/wcf/diagnostics.md) im Abschnitt [\<System. Service Model >](../../../configure-apps/file-schema/wcf/system-servicemodel.md) , wie in der folgenden Beispielkonfiguration gezeigt.  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 Mit diesem Konfigurationseintrag wird eine WMI-Schnittstelle verfügbar gemacht. Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentierung der Anwendung zugegriffen werden.  
  
## <a name="accessing-wmi-data"></a>Zugreifen auf WMI-Daten  
 Der Zugriff auf WMI-Daten kann auf mehrere Arten erfolgen. Microsoft stellt WMI-APIs für Skripts, Visual Basic C++ Anwendungen, Anwendungen und die .NET Framework bereit. Weitere Informationen finden Sie unter [Verwenden von WMI](https://go.microsoft.com/fwlink/?LinkId=95183).  
  
> [!CAUTION]
> Bei Verwendung der von .NET Framework bereitgestellten Methoden zum programmgesteuerten Zugreifen auf WMI-Daten ist darauf zu achten, dass von solchen Methoden bei hergestellter Verbindung möglicherweise Ausnahmen ausgelöst werden. Die Verbindung ist zwar beim Erstellen der <xref:System.Management.ManagementObject>-Instanz nicht hergestellt, dies ändert sich jedoch bei der ersten Anforderung, die einen tatsächlichen Austausch von Daten erfordert. Verwenden Sie deshalb zum Abfangen möglicher Ausnahmen einen `try..catch`-Block.  
  
 Sie können die Ablaufverfolgungs- und Nachrichtenprotokollierungsebene sowie die Nachrichtenprotokollierungsoptionen für die `System.ServiceModel`-Ablaufverfolgungsquelle in WMI ändern. Dies kann durchzugreifen auf die [AppDomainInfo](appdomaininfo.md) -Instanz erfolgen, die diese booleschen Eigenschaften verfügbar macht: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`und `TraceLevel`. Wenn Sie einen Ablaufverfolgungslistener für die Nachrichtenprotokollierung konfigurieren, diese Optionen in der Konfiguration jedoch auf `false` festlegen, können Sie sie später, wenn die Anwendung ausgeführt wird, zu `true` ändern. Dadurch wird die Nachrichtenprotokollierung zur Laufzeit aktiviert. Entsprechend können Sie die Nachrichtenprotokollierung zur Laufzeit mit WMI deaktivieren, wenn Sie sie in der Konfigurationsdatei aktivieren.  
  
 Sind in der Konfigurationsdatei keine Ablaufverfolgungslistener für die Nachrichtenprotokollierung oder keine `System.ServiceModel`-Ablaufverfolgungslistener angegeben, haben die vorgenommenen Änderungen keinerlei Auswirkungen, obgleich sie von WMI akzeptiert werden. Weitere Informationen zum ordnungsgemäßen Einrichten der jeweiligen Listener finden Sie unter [Konfigurieren der Nachrichten Protokollierung](../configuring-message-logging.md) und Konfigurieren der Ablauf [Verfolgung](../tracing/configuring-tracing.md). Die Ablaufverfolgungsebene aller anderen in der Konfiguration angegebenen Ablaufverfolgungsquellen wird beim Start der Anwendung wirksam und kann nicht geändert werden.  
  
 WCF macht eine `GetOperationCounterInstanceName` Methode für die Skripterstellung verfügbar. Wird die Methode mit einem Vorgangsnamen angegeben, wird der Name einer Leistungsindikatorinstanz zurückgegeben. Die Eingabe wird jedoch nicht überprüft. Aus diesem Grund wird bei Angabe eines falschen Vorgangsnamens auch ein falscher Indikatorname zurückgegeben.  
  
 Die `OutgoingChannel`-Eigenschaft der `Service` Instanz zählt keine Kanäle, die von einem Dienst zum Herstellen einer Verbindung mit einem anderen Dienst geöffnet wurden, wenn der WCF-Client für den Ziel Dienst nicht innerhalb der `Service`-Methode erstellt wird.  
  
 **Vorsicht** WMI unterstützt nur einen <xref:System.TimeSpan> Wert von bis zu 3 Dezimalstellen. Beispiel: Wird eine der Eigenschaften des Diensts auf <xref:System.TimeSpan.MaxValue> festgelegt, wird der Wert beim Anzeigen in WMI nach 3Dezimalstellen abgeschnitten.  
  
## <a name="security"></a>Sicherheit  
 Da der WCF-WMI-Anbieter die Ermittlung von Diensten in einer Umgebung zulässt, sollten Sie bei der Gewährung des Zugriffs auf die Anwendung äußerst vorsichtig vorgehen. Durch Lockern des standardmäßig auf Administratoren beschränkten Zugriffs erhalten möglicherweise weniger vertrauenswürdige Parteien Zugriff auf sensible Daten der Umgebung. Genauer gesagt: Durch eine Lockerung der Berechtigungen für den Remote-WMI-Zugriff erhöht sich das Risiko für Überlastungsangriffe. Wird ein Prozess von einer Vielzahl von WMI-Anforderungen regelrecht überschwemmt, hat dies eine Beeinträchtigung der Leistung zur Folge.  
  
 Werden die Zugriffsberechtigungen für die MOF-Datei gelockert, haben weniger vertrauenswürdige Parteien die Möglichkeit zum Manipulieren des WMI-Verhaltens sowie zum Ändern der im WMI-Schema geladenen Objekte. So können beispielsweise Felder entfernt werden, was dazu führen kann, dass dem Administrator wichtige Daten nicht mehr zur Verfügung stehen oder der Datei Felder hinzugefügt werden, die nicht ausgefüllt werden oder Ausnahmen auslösen.  
  
 Standardmäßig erteilt der WCF-WMI-Anbieter die Berechtigung "Execute Method", "Provider Write" und "Enable Account" für den Administrator, und die Berechtigung "Konto aktivieren" für ASP.net, lokaler Dienst und Netzwerkdienst. Insbesondere auf nicht-Windows Vista-Plattformen verfügt das ASP.NET-Konto über Lesezugriff auf den WMI Service Model-Namespace. Sollen diese Rechte einer bestimmten Benutzergruppe vorenthalten werden, deaktivieren Sie entweder den WMI-Anbieter (ist standardmäßig deaktiviert), oder deaktivieren Sie den Zugriff für die gewünschte Benutzergruppe.  
  
 Darüber hinaus kann WMI beim Versuch, WMI mithilfe der Konfiguration zu aktivieren, möglicherweise aufgrund unzureichender Benutzerberechtigungen nicht aktiviert werden. Es wird jedoch kein Ereignis in das Ereignisprotokoll aufgenommen, um diesen Fehler zu protokollieren.  
  
 Gehen Sie zum Ändern der Benutzerberechtigungsebenen folgendermaßen vor:  
  
1. Klicken Sie auf Start und dann auf Ausführen, und geben Sie **compmgmt. msc**ein.  
  
2. Klicken Sie mit der rechten Maustaste auf **Dienste und Anwendungen/WMI-Steuerelemente** , um **Eigenschaften**auszuwählen  
  
3. Wählen Sie die Registerkarte **Sicherheit** aus, und navigieren Sie zum Namespace **root/Service Model** . Klicken Sie auf die Schaltfläche **Sicherheit** .  
  
4. Wählen Sie die Gruppe oder den Benutzer aus, für die Sie den Zugriff steuern möchten, und verwenden Sie das Kontrollkästchen **zulassen** oder **verweigern** , um Berechtigungen zu konfigurieren.  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a>Gewähren von WCF WMI-Registrierungsberechtigungen für zusätzliche Benutzer  
 WCF macht Verwaltungsdaten für WMI verfügbar. Dies erfolgt durch das Hosting eines Prozess internen WMI-Anbieters, der manchmal als "entkoppelter Anbieter" bezeichnet wird. Damit die Verwaltungsdaten verfügbar gemacht werden können, muss das Konto, das diesen Anbieter registriert, über die erforderlichen Berechtigungen verfügen. Unter Windows kann standardmäßig nur eine kleine Gruppe von berechtigten Konten entkoppelte Anbieter registrieren. Dies ist ein Problem, da Benutzer im Allgemeinen die WMI-Daten von einem WCF-Dienst verfügbar machen möchten, der unter einem Konto ausgeführt wird, das nicht im Standardsatz enthalten ist.  
  
 Um diesen Zugriff bereitzustellen, muss ein Administrator den zusätzlichen Konten die folgenden Berechtigungen in der angegebenen Reihenfolge erteilen:  
  
1. Berechtigung für den Zugriff auf den WCF WMI-Namespace.  
  
2. Berechtigung zum Registrieren des entkoppelten WCF WMI-Anbieters.  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a>So gewähren Sie eine Zugriffsberechtigung für den WMI-Namespace  
  
1. Führen Sie das folgende PowerShell-Skript aus.  
  
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
  
     Dieses PowerShell-Skript verwendet die Security Descriptor Definition Language (SDDL), um der integrierten Benutzergruppe Zugriff auf den WMI-Namespace "root/Service Model" zu gewähren. Folgende ACLs werden angegeben:  
  
    - Integriertes Administratorkonto (Built-In Administrator, BA) - Hatte bereits Zugriff.  
  
    - Netzwerkdienst (Network Service, NS) - Hatte bereits Zugriff.  
  
    - Lokales Systemkonto (Local System, LS) - Hatte bereits Zugriff.  
  
    - Integrierte Gruppe "Benutzer" - Die Gruppe, für die der Zugriff erteilt wird.  
  
#### <a name="to-grant-provider-registration-access"></a>So gewähren Sie Zugriff für die Anbieterregistrierung  
  
1. Führen Sie das folgende PowerShell-Skript aus.  
  
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
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a>Gewähren von Zugriff für beliebige Benutzer oder Gruppen  
 Mit dem Beispiel in diesem Abschnitt werden allen lokalen Benutzern Berechtigungen für die WMI-Anbieterregistrierung gewährt. Wenn Sie nicht integrierten Benutzern oder Gruppen Zugriff gewähren möchten, müssen Sie die Sicherheits-ID (SID) des Benutzers oder der Gruppe abrufen. Es gibt keine einfache Möglichkeit, die SID für einen beliebigen Benutzer abzurufen. Eine Methode besteht darin, sich als der gewünschte Benutzer anzumelden und dann den folgenden Shellbefehl auszuführen.  
  
```console
Whoami /user  
```  
  
 Dieser Befehl stellt die SID des aktuellen Benutzers bereit, aber diese Methode kann nicht verwendet werden, um die SID für einen beliebigen Benutzer abzurufen. Eine weitere Methode zum erhalten der SID ist die Verwendung des Tools [Getsid. exe](https://go.microsoft.com/fwlink/?LinkId=186467) aus den [Windows 2000 Resource Kit-Tools für administrative Aufgaben](https://go.microsoft.com/fwlink/?LinkId=178660). Dieses Tool vergleicht die SID von zwei Benutzern (lokal oder Domäne) und gibt als Nebeneffekt die beiden SIDs in der Befehlszeile aus. Weitere Informationen finden Sie unter [Bekannte SIDs](https://go.microsoft.com/fwlink/?LinkId=186468).  
  
## <a name="accessing-remote-wmi-object-instances"></a>Zugreifen auf Remote-WMI-Objektinstanzen  
 Wenn Sie auf WCF-WMI-Instanzen auf einem Remote Computer zugreifen müssen, müssen Sie den Paket Datenschutz für die Tools aktivieren, die Sie für den Zugriff verwenden. Im folgenden Abschnitt wird die hierzu erforderliche Vorgehensweise für WMI CIM Studio, das Testprogramm für Windows-Verwaltungsinstrumentation und .NET SDK 2.0 beschrieben.  
  
### <a name="wmi-cim-studio"></a>WMI CIM Studio  
 Wenn Sie die [WMI-Verwaltungs Tools](https://go.microsoft.com/fwlink/?LinkId=95185)installiert haben, können Sie den WMI-CIM-Studio für den Zugriff auf WMI-Instanzen verwenden. Die Tools befinden sich im folgenden Ordner:  
  
 **%windir%\Programme\WMI Tools\\**  
  
1. Geben Sie im Fenster mit **Namespace verbinden:** **root\ServiceModel** ein, und klicken Sie auf **OK.**  
  
2. Klicken Sie im Anmeldefenster für **WMI CIM Studio** auf die Schaltfläche **Optionen > >** , um das Fenster zu erweitern. Wählen Sie für **Authentifizierungs Ebene**die Option **Paket** Sicherheit aus, und klicken Sie auf **OK**  
  
### <a name="windows-management-instrumentation-tester"></a>Testprogramm für Windows-Verwaltungsinstrumentation  
 Dieses Tool wird von Windows installiert. Um es auszuführen, starten Sie eine Befehlskonsole, indem Sie im Dialogfeld **Starten/ausführen** den Befehl **cmd. exe** eingeben, und klicken Sie auf **OK**. Geben Sie dann im Befehlsfenster " **wbemtest. exe** " ein. Das Testprogramm für Windows-Verwaltungsinstrumentierung wird gestartet.  
  
1. Klicken Sie in der oberen rechten Ecke des Fensters auf die Schaltfläche **verbinden** .  
  
2. Geben Sie im neuen Fenster im Feld **Namespace** den Namen **root\ServiceModel** ein, und wählen Sie für **Authentifizierungs Ebene**die Option **Paket Datenschutz** aus. Klicken Sie auf **Verbinden**.  
  
### <a name="using-managed-code"></a>Verwenden von verwaltetem Code  
 Der Zugriff auf Remote-WMI-Instanzen kann auch programmgesteuert erfolgen. Verwenden Sie hierzu die vom <xref:System.Management>-Namespace bereitgestellten Klassen. Die erforderliche Vorgehensweise wird im folgenden Codebeispiel veranschaulicht:  
  
```csharp
String wcfNamespace = $@"\\{this.serviceMachineName}\Root\ServiceModel");
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
