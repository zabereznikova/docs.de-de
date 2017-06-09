---
title: "Verwenden der Windows-Verwaltungsinstrumentation f&#252;r die Diagnose | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Verwenden der Windows-Verwaltungsinstrumentation f&#252;r die Diagnose
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] macht zur Laufzeit Inspektionsdaten eines Diensts über einen Windows\-Verwaltungsinstrumentation \(WMI\)\-Anbieter von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] verfügbar.  
  
## Aktivieren von WMI  
 Bei WMI handelt es sich um die Implementierung des Web\-Based Enterprise Management \(WBEM\)\-Standards von Microsoft.  [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] zum WMI\-SDK finden Sie in der MSDN\-Bibliothek.  \(http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/wmisdk\/wmi\/wmi\_start\_page.asp\).  Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentation für externe Verwaltungstools.  
  
 Ein WMI\-Anbieter ist eine Komponente zum Verfügbarmachen der Instrumentation zur Laufzeit über eine WBEM\-kompatible Schnittstelle.  Sie besteht aus einer Gruppe von WMI\-Objekten mit Attribut\/Wert\-Paaren.  Bei den Paaren kann es sich um eine Reihe einfacher Typen handeln.  Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen.  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] macht Attribute von Diensten \(wie Adressen, Bindungen, Verhaltensweisen und Listener\) verfügbar.  
  
 Der integrierte WMI\-Anbieter kann in der Konfigurationsdatei der Anwendung aktiviert werden.  Dies erfolgt über das `wmiProviderEnabled`\-Attribut des [\<Diagnose\>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)s im Abschnitt des [\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Elements, wie in der folgenden Beispielkonfiguration gezeigt.  
  
```  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
  
```  
  
 Mit diesem Konfigurationseintrag wird eine WMI\-Schnittstelle verfügbar gemacht.  Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentation der Anwendung zugegriffen werden.  
  
## Zugreifen auf WMI\-Daten  
 Der Zugriff auf WMI\-Daten kann auf mehrere Arten erfolgen.  Von Microsoft werden WMI\-APIs für Skripts, [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)]\-Anwendungen, C\+\+\-Anwendungen sowie [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] bereitgestellt.  Weitere Informationen finden Sie unter [Verwenden von WMI](http://go.microsoft.com/fwlink/?LinkId=95183).  
  
> [!CAUTION]
>  Bei Verwendung der von .NET Framework bereitgestellten Methoden zum programmgesteuerten Zugreifen auf WMI\-Daten ist darauf zu achten, dass von solchen Methoden bei hergestellter Verbindung möglicherweise Ausnahmen ausgelöst werden.  Die Verbindung ist zwar beim Erstellen der <xref:System.Management.ManagementObject>\-Instanz nicht hergestellt, dies ändert sich jedoch bei der ersten Anforderung, die einen tatsächlichen Austausch von Daten erfordert.  Verwenden Sie deshalb zum Abfangen möglicher Ausnahmen einen `try..catch`\-Block.  
  
 Sie können die Ablaufverfolgungs\- und Nachrichtenprotokollierungsebene sowie die Nachrichtenprotokollierungsoptionen für die `System.ServiceModel`\-Ablaufverfolgungsquelle in WMI ändern.  Dies kann durch Zugreifen auf die [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)\-Instanz erfolgen, von der folgende boolesche Eigenschaften verfügbar gemacht werden: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages` und `TraceLevel`.  Wenn Sie einen Ablaufverfolgungslistener für die Nachrichtenprotokollierung konfigurieren, diese Optionen in der Konfiguration jedoch auf `false` festlegen, können Sie sie später, wenn die Anwendung ausgeführt wird, zu `true` ändern.  Dadurch wird die Nachrichtenprotokollierung zur Laufzeit aktiviert.  Entsprechend können Sie die Nachrichtenprotokollierung zur Laufzeit mit WMI deaktivieren, wenn Sie sie in der Konfigurationsdatei aktivieren.  
  
 Sind in der Konfigurationsdatei keine Ablaufverfolgungslistener für die Nachrichtenprotokollierung oder keine `System.ServiceModel`\-Ablaufverfolgungslistener angegeben, haben die vorgenommenen Änderungen keinerlei Auswirkungen, obgleich sie von WMI akzeptiert werden.  Weitere Informationen zum ordnungsgemäßen Einrichten der jeweiligen Listener finden Sie unter [Konfigurieren der Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) und [Konfigurieren der Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  Die Ablaufverfolgungsebene aller anderen in der Konfiguration angegebenen Ablaufverfolgungsquellen wird beim Start der Anwendung wirksam und kann nicht geändert werden.  
  
 Von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] wird eine `GetOperationCounterInstanceName`\-Methode für das Skripting verfügbar gemacht.  Wird die Methode mit einem Vorgangsnamen angegeben, wird der Name einer Leistungsindikatorinstanz zurückgegeben.  Die Eingabe wird jedoch nicht überprüft.  Aus diesem Grund wird bei Angabe eines falschen Vorgangsnamens auch ein falscher Indikatorname zurückgegeben.  
  
 Von der `OutgoingChannel`\-Eigenschaft der `Service`\-Instanz werden keine Channels gezählt, die von einem Dienst zum Herstellen einer Verbindung mit einem anderen Dienst geöffnet wurden, wenn der [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Client für den Zieldienst nicht innerhalb der `Service`\-Methode erstellt wird.  
  
 **Vorsicht** Von WMI wird nur ein <xref:System.TimeSpan>\-Wert mit maximal 3Dezimalstellen unterstützt.  Beispiel: Wird eine der Eigenschaften des Diensts auf <xref:System.TimeSpan.MaxValue> festgelegt, wird der Wert beim Anzeigen in WMI nach 3Dezimalstellen abgeschnitten.  
  
## Sicherheit  
 Da der [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-WMI\-Anbieter das Erkennen von Diensten in einer Umgebung ermöglicht, sollten Sie beim Gewähren von Zugriff auf den Anbieter äußerste Vorsicht walten lassen.  Durch Lockern des standardmäßig auf Administratoren beschränkten Zugriffs erhalten möglicherweise weniger vertrauenswürdige Parteien Zugriff auf sensible Daten der Umgebung.  Genauer gesagt: Durch eine Lockerung der Berechtigungen für den Remote\-WMI\-Zugriff erhöht sich das Risiko für Überlastungsangriffe.  Wird ein Prozess von einer Vielzahl von WMI\-Anforderungen regelrecht überschwemmt, hat dies eine Beeinträchtigung der Leistung zur Folge.  
  
 Werden die Zugriffsberechtigungen für die MOF\-Datei gelockert, haben weniger vertrauenswürdige Parteien die Möglichkeit zum Manipulieren des WMI\-Verhaltens sowie zum Ändern der im WMI\-Schema geladenen Objekte.  So können beispielsweise Felder entfernt werden, was dazu führen kann, dass dem Administrator wichtige Daten nicht mehr zur Verfügung stehen oder der Datei Felder hinzugefügt werden, die nicht ausgefüllt werden oder Ausnahmen auslösen.  
  
 Standardmäßig werden Administratoren vom [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-WMI\-Anbieter Berechtigungen vom Typ "execute method", "provider write" und "enable account" gewährt. Für ASP.NET, den lokalen Dienst und den Netzwerkdienst wird die Berechtigung "enable account" gewährt.  Auf Nicht\-[!INCLUDE[wv](../../../../../includes/wv-md.md)]\-Plattformen besitzt das ASP.NET\-Konto Lesezugriff auf den WMI\-ServiceModel\-Namespace.  Sollen diese Rechte einer bestimmten Benutzergruppe vorenthalten werden, deaktivieren Sie entweder den WMI\-Anbieter \(ist standardmäßig deaktiviert\), oder deaktivieren Sie den Zugriff für die gewünschte Benutzergruppe.  
  
 Darüber hinaus kann WMI beim Versuch, WMI mithilfe der Konfiguration zu aktivieren, möglicherweise aufgrund unzureichender Benutzerberechtigungen nicht aktiviert werden.  Es wird jedoch kein Ereignis in das Ereignisprotokoll aufgenommen, um diesen Fehler zu protokollieren.  
  
 Gehen Sie zum Ändern der Benutzerberechtigungsebenen folgendermaßen vor:  
  
1.  Klicken Sie auf Start, klicken Sie auf Ausführen, und geben Sie **compmgmt.msc** ein.  
  
2.  Klicken Sie mit der rechten Maustaste auf **Dienste und Anwendungen\/WMI\-Steuerelemente**, und wählen Sie **Eigenschaften**.  
  
3.  Klicken Sie auf die Registerkarte **Sicherheit**, und navigieren Sie zum Namespace **Root\/ServiceModel**.  Klicken Sie auf die Schaltfläche **Sicherheit**.  
  
4.  Wählen Sie die Gruppe oder den Benutzer aus, für die oder den der Zugriff gesteuert werden soll, und konfigurieren Sie mithilfe des Kontrollkästchens **Zulassen** oder **Verweigern** die gewünschten Berechtigungen.  
  
## Gewähren von WCF WMI\-Registrierungsberechtigungen für zusätzliche Benutzer  
 WCF macht Verwaltungsdaten für WMI verfügbar.  Hierzu wird ein prozessinternen WMI\-Anbieter gehostet, der mitunter als "entkoppelter Anbieter" bezeichnet wird.  Damit die Verwaltungsdaten verfügbar gemacht werden können, muss das Konto, das diesen Anbieter registriert, über die erforderlichen Berechtigungen verfügen.  Unter Windows kann standardmäßig nur eine kleine Gruppe von berechtigten Konten entkoppelte Anbieter registrieren. Dies ist ein Problem, da Benutzer im Allgemeinen die WMI\-Daten von einem WCF\-Dienst verfügbar machen möchten, der unter einem Konto ausgeführt wird, das nicht im Standardsatz enthalten ist.  
  
 Um diesen Zugriff bereitzustellen, muss ein Administrator den zusätzlichen Konten die folgenden Berechtigungen in der angegebenen Reihenfolge erteilen:  
  
1.  Berechtigung für den Zugriff auf den WCF WMI\-Namespace.  
  
2.  Berechtigung zum Registrieren des entkoppelten WCF WMI\-Anbieters.  
  
#### So gewähren Sie eine Zugriffsberechtigung für den WMI\-Namespace  
  
1.  Führen Sie das folgende PowerShell\-Skript aus.  
  
    ```powershell  
    write-host “”  
    write-host “Granting Access to root/servicemodel WMI namespace to built in users group”  
    write-host “”  
  
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
    write-host “”  
  
    ```  
  
     Dieses PowerShell\-Skript verwendet SDDL \(Security Descriptor Definition Language\), um der integrierten Gruppe "Benutzer" Zugriff auf den "root\/servicemodel"\-WMI\-Namespace zu gewähren.  Folgende ACLs werden angegeben:  
  
    -   Integriertes Administratorkonto \(Built\-In Administrator, BA\) \- Hatte bereits Zugriff.  
  
    -   Netzwerkdienst \(Network Service, NS\) \- Hatte bereits Zugriff.  
  
    -   Lokales Systemkonto \(Local System, LS\) \- Hatte bereits Zugriff.  
  
    -   Integrierte Gruppe "Benutzer" \- Die Gruppe, für die der Zugriff erteilt wird.  
  
#### So gewähren Sie Zugriff für die Anbieterregistrierung  
  
1.  Führen Sie das folgende PowerShell\-Skript aus.  
  
    ```powershell  
    write-host “”  
    write-host “Granting WCF provider registration access to built in users group”  
    write-host “”  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host “”  
  
    ```  
  
### Gewähren von Zugriff für beliebige Benutzer oder Gruppen  
 Mit dem Beispiel in diesem Abschnitt werden allen lokalen Benutzern Berechtigungen für die WMI\-Anbieterregistrierung gewährt.  Wenn Sie nicht integrierten Benutzern oder Gruppen Zugriff gewähren möchten, müssen Sie die Sicherheits\-ID \(SID\) des Benutzers oder der Gruppe abrufen.  Es gibt keine einfache Möglichkeit, die SID für einen beliebigen Benutzer abzurufen.  Eine Methode besteht darin, sich als der gewünschte Benutzer anzumelden und dann den folgenden Shellbefehl auszuführen.  
  
```  
Whoami /user  
```  
  
 Dieser Befehl stellt die SID des aktuellen Benutzers bereit, aber diese Methode kann nicht verwendet werden, um die SID für einen beliebigen Benutzer abzurufen.  Eine weitere Methode zum Abrufen der SID ist die Verwendung des Tools [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) aus den [Windows 2000 Resource Kit\-Tools für administrative Aufgaben](http://go.microsoft.com/fwlink/?LinkId=178660).  Dieses Tool vergleicht die SID von zwei Benutzern \(lokal oder Domäne\) und gibt als Nebeneffekt die beiden SIDs in der Befehlszeile aus.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Bekannte SIDs](http://go.microsoft.com/fwlink/?LinkId=186468).  
  
## Zugreifen auf Remote\-WMI\-Objektinstanzen  
 Zum Zugreifen auf die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-WMI\-Instanzen eines Remotecomputers muss für die zum Zugreifen verwendeten Tools die Paketsicherheit aktiviert werden.  Im folgenden Abschnitt wird die hierzu erforderliche Vorgehensweise für WMI CIM Studio, das Testprogramm für Windows\-Verwaltungsinstrumentation und .NET SDK 2.0 beschrieben.  
  
### WMI CIM Studio  
 Ist die [WMI\-Verwaltung](http://go.microsoft.com/fwlink/?LinkId=95185) installiert, kann der Zugriff auf WMI\-Instanzen mithilfe von WMI CIM Studio erfolgen.  Die Tools befinden sich im folgenden Ordner:  
  
 **%windir%\\Programme\\WMI Tools\\**  
  
1.  Geben Sie im Fenster für die Namespaceverbindung den Text **root\\ServiceModel** ein, und klicken Sie anschließend auf **OK**.  
  
2.  Klicken Sie im Anmeldefenster für WMI CIM Studio auf die Schaltfläche **Optionen \>\>**, um das Fenster zu erweitern.  Wählen Sie unter **Authentifizierungsebene** die Option **Paketsicherheit** aus, und klicken Sie anschließend auf **OK**.  
  
### Testprogramm für Windows\-Verwaltungsinstrumentation  
 Dieses Tool wird von Windows installiert.  Starten Sie zum Ausführen des Tools eine Befehlskonsole, indem Sie im Dialogfeld **Starten\/Ausführen** den Befehl cmd.exe eingeben, und klicken Sie anschließend auf **OK**.  Geben Sie im Befehlsfenster den Befehl wbemtest.exe ein.  Das Testprogramm für Windows\-Verwaltungsinstrumentation wird gestartet.  
  
1.  Klicken Sie in der rechten oberen Fensterecke auf die Schaltfläche **Verbinden**.  
  
2.  Geben Sie im neuen Fenster im Feld **Namespace** die Zeichenfolge **root\\ServiceModel** ein, und wählen Sie unter **Authentifizierungsebene** die Option Paketsicherheit aus.  Klicken Sie auf **Verbinden**.  
  
### Verwenden von verwaltetem Code  
 Der Zugriff auf Remote\-WMI\-Instanzen kann auch programmgesteuert erfolgen. Verwenden Sie hierzu die vom <xref:System.Management>\-Namespace bereitgestellten Klassen.  Die erforderliche Vorgehensweise wird im folgenden Codebeispiel veranschaulicht:  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```