---
title: Verwenden der Windows-Verwaltungsinstrumentierung für die Diagnose
ms.date: 03/30/2017
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
ms.openlocfilehash: b1ebb6b438df6d7efb5342a82e42220a58ea5cbd
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "42908145"
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a>Verwenden der Windows-Verwaltungsinstrumentierung für die Diagnose
Windows Communication Foundation (WCF) macht inspektionsdaten eines Diensts zur Laufzeit über einen WCF (Windows Management Instrumentation, WMI) Anbieter verfügbar.  
  
## <a name="enabling-wmi"></a>Aktivieren von WMI  
 Bei WMI handelt es sich um die Implementierung des Web-Based Enterprise Management (WBEM)-Standards von Microsoft. Weitere Informationen zum WMI-SDK finden Sie unter [Windows-Verwaltungsinstrumentation](/windows/desktop/WmiSdk/wmi-start-page). Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentierung für externe Verwaltungstools.  
  
 Ein WMI-Anbieter ist eine Komponente zum Verfügbarmachen der Instrumentation zur Laufzeit über eine WBEM-kompatible Schnittstelle. Sie besteht aus einer Gruppe von WMI-Objekten mit Attribut/Wert-Paaren. Bei den Paaren kann es sich um eine Reihe einfacher Typen handeln. Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen. WCF macht Attribute von Diensten wie z. B. Adressen, Bindungen, Verhaltensweisen und Listener.  
  
 Der integrierte WMI-Anbieter kann in der Konfigurationsdatei der Anwendung aktiviert werden. Dies erfolgt mithilfe der `wmiProviderEnabled` Attribut des der [ \<Diagnose >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in die [ \<system.serviceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt, wie im folgenden Beispiel gezeigt. die Konfiguration.  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 Mit diesem Konfigurationseintrag wird eine WMI-Schnittstelle verfügbar gemacht. Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentation der Anwendung zugegriffen werden.  
  
## <a name="accessing-wmi-data"></a>Zugreifen auf WMI-Daten  
 Der Zugriff auf WMI-Daten kann auf mehrere Arten erfolgen. Microsoft stellt WMI-APIs für Skripts, die Visual Basic-Anwendungen, die C++-Anwendungen und die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. Weitere Informationen finden Sie unter [mit WMI](http://go.microsoft.com/fwlink/?LinkId=95183).  
  
> [!CAUTION]
>  Bei Verwendung der von .NET Framework bereitgestellten Methoden zum programmgesteuerten Zugreifen auf WMI-Daten ist darauf zu achten, dass von solchen Methoden bei hergestellter Verbindung möglicherweise Ausnahmen ausgelöst werden. Die Verbindung ist zwar beim Erstellen der <xref:System.Management.ManagementObject>-Instanz nicht hergestellt, dies ändert sich jedoch bei der ersten Anforderung, die einen tatsächlichen Austausch von Daten erfordert. Verwenden Sie deshalb zum Abfangen möglicher Ausnahmen einen `try..catch`-Block.  
  
 Sie können die Ablaufverfolgungs- und Nachrichtenprotokollierungsebene sowie die Nachrichtenprotokollierungsoptionen für die `System.ServiceModel`-Ablaufverfolgungsquelle in WMI ändern. Dies ist möglich durch den Zugriff auf die [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) -Instanz, die folgende booleschen Eigenschaften verfügbar macht: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, und `TraceLevel`. Wenn Sie einen Ablaufverfolgungslistener für die Nachrichtenprotokollierung konfigurieren, diese Optionen in der Konfiguration jedoch auf `false` festlegen, können Sie sie später, wenn die Anwendung ausgeführt wird, zu `true` ändern. Dadurch wird die Nachrichtenprotokollierung zur Laufzeit aktiviert. Entsprechend können Sie die Nachrichtenprotokollierung zur Laufzeit mit WMI deaktivieren, wenn Sie sie in der Konfigurationsdatei aktivieren.  
  
 Sind in der Konfigurationsdatei keine Ablaufverfolgungslistener für die Nachrichtenprotokollierung oder keine `System.ServiceModel`-Ablaufverfolgungslistener angegeben, haben die vorgenommenen Änderungen keinerlei Auswirkungen, obgleich sie von WMI akzeptiert werden. Weitere Informationen zum ordnungsgemäßen Einrichten der jeweiligen Listener finden Sie unter [Konfigurieren der Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) und [Konfigurieren der Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md). Die Ablaufverfolgungsebene aller anderen in der Konfiguration angegebenen Ablaufverfolgungsquellen wird beim Start der Anwendung wirksam und kann nicht geändert werden.  
  
 WCF macht einen `GetOperationCounterInstanceName` Methode für die Skripterstellung. Wird die Methode mit einem Vorgangsnamen angegeben, wird der Name einer Leistungsindikatorinstanz zurückgegeben. Die Eingabe wird jedoch nicht überprüft. Aus diesem Grund wird bei Angabe eines falschen Vorgangsnamens auch ein falscher Indikatorname zurückgegeben.  
  
 Die `OutgoingChannel` Eigenschaft der `Service` Instanz werden keine Channels, die von einem Dienst für die Verbindung zu einem anderen Dienst geöffnet wird, wenn der WCF-Client an den Zieldienst nicht innerhalb erstellt wird gezählt. die `Service` Methode.  
  
 **Vorsicht** WMI unterstützt nur eine <xref:System.TimeSpan> Wert bis zu 3 Dezimalstellen. Beispiel: Wird eine der Eigenschaften des Diensts auf <xref:System.TimeSpan.MaxValue> festgelegt, wird der Wert beim Anzeigen in WMI nach 3Dezimalstellen abgeschnitten.  
  
## <a name="security"></a>Sicherheit  
 Da der WCF WMI-Anbieter das Erkennen von Diensten in einer Umgebung ermöglicht wird, sollten Sie vorsichtig, zum Gewähren des Zugriffs darauf ausführen. Durch Lockern des standardmäßig auf Administratoren beschränkten Zugriffs erhalten möglicherweise weniger vertrauenswürdige Parteien Zugriff auf sensible Daten der Umgebung. Genauer gesagt: Durch eine Lockerung der Berechtigungen für den Remote-WMI-Zugriff erhöht sich das Risiko für Überlastungsangriffe. Wird ein Prozess von einer Vielzahl von WMI-Anforderungen regelrecht überschwemmt, hat dies eine Beeinträchtigung der Leistung zur Folge.  
  
 Werden die Zugriffsberechtigungen für die MOF-Datei gelockert, haben weniger vertrauenswürdige Parteien die Möglichkeit zum Manipulieren des WMI-Verhaltens sowie zum Ändern der im WMI-Schema geladenen Objekte. So können beispielsweise Felder entfernt werden, was dazu führen kann, dass dem Administrator wichtige Daten nicht mehr zur Verfügung stehen oder der Datei Felder hinzugefügt werden, die nicht ausgefüllt werden oder Ausnahmen auslösen.  
  
 Standardmäßig der WCF WMI-Anbieter gewährt "execute Method", "Provider Write" und "Konto aktivieren" die Berechtigung für den Administrator und Berechtigungen für ASP.NET "," Lokaler Dienst "und" Netzwerkdienst "Konto aktivieren". Auf Nicht-[!INCLUDE[wv](../../../../../includes/wv-md.md)]-Plattformen besitzt das ASP.NET-Konto Lesezugriff auf den WMI-ServiceModel-Namespace. Sollen diese Rechte einer bestimmten Benutzergruppe vorenthalten werden, deaktivieren Sie entweder den WMI-Anbieter (ist standardmäßig deaktiviert), oder deaktivieren Sie den Zugriff für die gewünschte Benutzergruppe.  
  
 Darüber hinaus kann WMI beim Versuch, WMI mithilfe der Konfiguration zu aktivieren, möglicherweise aufgrund unzureichender Benutzerberechtigungen nicht aktiviert werden. Es wird jedoch kein Ereignis in das Ereignisprotokoll aufgenommen, um diesen Fehler zu protokollieren.  
  
 Gehen Sie zum Ändern der Benutzerberechtigungsebenen folgendermaßen vor:  
  
1.  Klicken Sie auf Start, und klicken Sie dann ausführen, und geben Sie **compmgmt.msc**.  
  
2.  Mit der rechten Maustaste **Dienste und Anwendungen/WMI-Steuerelemente** auszuwählenden **Eigenschaften**.  
  
3.  Wählen Sie die **Sicherheit** Registerkarte, und navigieren Sie zu der **Root/ServiceModel** Namespace. Klicken Sie auf die **Sicherheit** Schaltfläche.  
  
4.  Wählen Sie die spezifischen Gruppe oder Benutzer, die Sie verwenden möchten, den Zugriff steuern und verwenden Sie die **zulassen** oder **Verweigern** Kontrollkästchen, um Berechtigungen zu konfigurieren.  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a>Gewähren von WCF WMI-Registrierungsberechtigungen für zusätzliche Benutzer  
 WCF macht Verwaltungsdaten für WMI verfügbar. Dies erfolgt durch das Hosten eines in-Process-WMI-Anbieters, manchmal als "entkoppelten Anbieter" bezeichnet. Damit die Verwaltungsdaten verfügbar gemacht werden können, muss das Konto, das diesen Anbieter registriert, über die erforderlichen Berechtigungen verfügen. Unter Windows kann standardmäßig nur eine kleine Gruppe von berechtigten Konten entkoppelte Anbieter registrieren. Dies ist ein Problem, da Benutzer im Allgemeinen die WMI-Daten von einem WCF-Dienst verfügbar machen möchten, der unter einem Konto ausgeführt wird, das nicht im Standardsatz enthalten ist.  
  
 Um diesen Zugriff bereitzustellen, muss ein Administrator den zusätzlichen Konten die folgenden Berechtigungen in der angegebenen Reihenfolge erteilen:  
  
1.  Berechtigung für den Zugriff auf den WCF WMI-Namespace.  
  
2.  Berechtigung zum Registrieren des entkoppelten WCF WMI-Anbieters.  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a>So gewähren Sie eine Zugriffsberechtigung für den WMI-Namespace  
  
1.  Führen Sie das folgende PowerShell-Skript aus.  
  
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
  
     Dieses PowerShell-Skript verwendet die Security Descriptor Definition Language (SDDL) um den integrierten Benutzergruppe Zugriff auf den WMI-Namespace "Root/Servicemodel" zu gewähren. Folgende ACLs werden angegeben:  
  
    -   Integriertes Administratorkonto (Built-In Administrator, BA) - Hatte bereits Zugriff.  
  
    -   Netzwerkdienst (Network Service, NS) - Hatte bereits Zugriff.  
  
    -   Lokales Systemkonto (Local System, LS) - Hatte bereits Zugriff.  
  
    -   Integrierte Gruppe "Benutzer" - Die Gruppe, für die der Zugriff erteilt wird.  
  
#### <a name="to-grant-provider-registration-access"></a>So gewähren Sie Zugriff für die Anbieterregistrierung  
  
1.  Führen Sie das folgende PowerShell-Skript aus.  
  
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
  
```  
Whoami /user  
```  
  
 Dieser Befehl stellt die SID des aktuellen Benutzers bereit, aber diese Methode kann nicht verwendet werden, um die SID für einen beliebigen Benutzer abzurufen. Eine andere Methode zum Abrufen der SID ist die Verwendung der [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) tool die [Windows 2000 Resource Kit-Tools für administrative Aufgaben](http://go.microsoft.com/fwlink/?LinkId=178660). Dieses Tool vergleicht die SID von zwei Benutzern (lokal oder Domäne) und gibt als Nebeneffekt die beiden SIDs in der Befehlszeile aus. Weitere Informationen finden Sie unter [Well-Known-SIDs](http://go.microsoft.com/fwlink/?LinkId=186468).  
  
## <a name="accessing-remote-wmi-object-instances"></a>Zugreifen auf Remote-WMI-Objektinstanzen  
 Bei Bedarf den Zugriff auf WCF WMI-Instanzen auf einem Remotecomputer, müssen Sie die paketsicherheit zu den Tools aktivieren, die Sie für den Zugriff verwenden. Im folgenden Abschnitt wird die hierzu erforderliche Vorgehensweise für WMI CIM Studio, das Testprogramm für Windows-Verwaltungsinstrumentierung und .NET SDK 2.0 beschrieben.  
  
### <a name="wmi-cim-studio"></a>WMI CIM Studio  
 Wenn Sie installiert haben [WMI-Verwaltung](http://go.microsoft.com/fwlink/?LinkId=95185), können Sie die WMI CIM Studio Zugriff auf WMI-Instanzen. Die Tools befinden sich im folgenden Ordner:  
  
 **%WINDIR%\Programme\Microsoft %windir%\programme\wmi Tools\\**  
  
1.  In der **Herstellen einer Verbindung mit dem Namespace:** geben **Root\ServiceModel** , und klicken Sie auf **OK.**  
  
2.  In der **WMI CIM Studio Anmeldung** Fenster, klicken Sie auf die **Optionen >>** Schaltfläche, um das Fenster zu erweitern. Wählen Sie **paketsicherheit** für **Authentifizierungsebene**, und klicken Sie auf **OK**.  
  
### <a name="windows-management-instrumentation-tester"></a>Testprogramm für Windows-Verwaltungsinstrumentierung  
 Dieses Tool wird von Windows installiert. Um es auszuführen, starten Sie eine Befehlskonsole durch Eingabe **cmd.exe** in die **starten/ausführen** Dialogfeld und klicken Sie auf **OK**. Geben Sie dann **wbemtest.exe** im Befehlsfenster angezeigt. Das Testprogramm für Windows-Verwaltungsinstrumentierung wird gestartet.  
  
1.  Klicken Sie auf die **Connect** auf der oberen rechten Ecke des Fensters auf die Schaltfläche.  
  
2.  Geben Sie im neuen Fenster **Root\ServiceModel** für die **Namespace** Feld, und wählen **paketsicherheit** für **Authentifizierungsebene**. Klicken Sie auf **Verbinden**.  
  
### <a name="using-managed-code"></a>Verwenden von verwaltetem Code  
 Der Zugriff auf Remote-WMI-Instanzen kann auch programmgesteuert erfolgen. Verwenden Sie hierzu die vom <xref:System.Management>-Namespace bereitgestellten Klassen. Die erforderliche Vorgehensweise wird im folgenden Codebeispiel veranschaulicht:  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
