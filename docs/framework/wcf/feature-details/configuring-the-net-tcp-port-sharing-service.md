---
title: Konfigurieren des Net.TCP-Portfreigabediensts
ms.date: 03/30/2017
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
ms.openlocfilehash: 2ff622dc97e63bd0ee10f00c7515692be8df09a1
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837453"
---
# <a name="configuring-the-nettcp-port-sharing-service"></a>Konfigurieren des Net.TCP-Portfreigabediensts
Selbst gehostete Dienste, die den Net.TCP-Transport verwenden, können erweiterte Einstellungen festlegen, etwa `ListenBacklog` und `MaxPendingAccepts`, die das Verhalten des zugrunde liegenden, für die Netzwerkkommunikation verwendeten TCP-Sockets bestimmen. Diese Einstellungen werden auf Bindungsebene jedoch nur für jeden Socket wirksam, wenn die Transportbindung die standardmäßig aktivierte Anschlussfreigabe deaktiviert hat.  
  
 Wenn eine Net.TCP-Bindung die Anschlussfreigabe aktiviert (indem für das Transportbindungselement `portSharingEnabled =true` festgelegt wird), erlaubt sie implizit einem externen Prozess (nämlich dem Prozess SMSvcHost.exe, der den Net.TCP-Portfreigabedienst hostet), den TCP-Socket in ihrem Namen zu verwalten. Geben Sie zum Beispiel, wenn Sie TCP verwenden, Folgendes an:  
  
```xml  
<tcpTransport portSharingEnabled="true"  />  
```  
  
 Die Einstellungen eines auf diese Weise konfigurierten Sockets, die mit dem Transportbindungselement des Diensts angegeben wurden, werden zugunsten der von SMSvcHost.exe angegebenen Einstellungen ignoriert.  
  
 Erstellen Sie zum Konfigurieren von SMSvcHost.exe eine XML-Konfigurationsdatei mit dem Namen "SmSvcHost.exe.config", und platzieren Sie sie im gleichen physischen Verzeichnis wie die ausführbare Datei "SMSvcHost.exe" (zum Beispiel unter "C:\Windows\Microsoft.NET\Framework\v4.5").  
  
 Im folgenden Beispiel wird eine SMSvcHost.exe.config-Datei gezeigt, in der alle konfigurierbaren Werte explizit mit den Standardeinstellungen festgelegt wurden.  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!--16 * # of processors -->  
          maxPendingAccepts="4"<!-- 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!--30 seconds -->  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->  
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->  
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
</configuration>  
```  
  
## <a name="when-to-modify-smsvchostexeconfig"></a>Wann SMSvcHost.exe.config zu ändern ist  
 Im Allgemeinen sollten Sie vorsichtig sein, wenn Sie den Inhalt der Datei SMSvcHost.exe.config ändern, weil jede in dieser Datei angegebene Konfigurationseinstellung alle Dienste eines Computers betrifft, die den Net.TCP-Portfreigabedienst verwenden. Dies schließt Anwendungen unter Windows Vista ein, die die TCP-Aktivierungs Funktionen von Windows Process Activation Service (was) verwenden.  
  
 Sie müssen jedoch möglicherweise manchmal die Standardkonfiguration für den Net.TCP-Portfreigabedienst ändern. Beispielsweise ist der Standardwert für `maxPendingAccepts` 4 * Anzahl von Prozessoren. Auf Servern, die eine große Anzahl von Diensten hosten, die die Portfreigabe verwenden, kann dieser Wert erhöht werden, um einen höheren Maximaldurchsatz zu erzielen. Der Standardwert von `maxPendingConnections` ist 100. Sie können diesen Wert auch erhöhen, wenn der Dienst von mehreren Clients gleichzeitig aufgerufen wird und Clientverbindungen getrennt werden.  
  
 SMSvcHost.exe.config enthält auch Informationen über die Prozessidentitäten, die möglicherweise den Anschlussfreigabedienst nutzen. Wenn ein Prozess eine Verbindung zu einem Anschlussfreigabedienst herstellt, um einen freigegebenen TCP-Anschluss zu verwenden, wird die Prozessidentität des verbindenden Prozesses mit einer Liste der Identitäten verglichen, die den Anschlussfreigabedienst verwenden dürfen. Diese Identitäten werden als Sicherheits-IDs (SIDs) im \<allowaccounts > Abschnitt der Datei SMSvcHost. exe. config angegeben. Die Berechtigung, den Anschlussfreigabedienst verwenden zu dürfen, wird standardmäßig Systemkonten (LocalService, LocalSystem und NetworkService) sowie Mitgliedern der Administratorgruppe gewährt. Anwendungen, die einem Prozess erlauben, mit einer anderen Identität (beispielsweise einer Benutzeridentität) die Verbindung mit dem Anschlussfreigabedienst herzustellen, müssen die entsprechende SID explizit in die Datei SMSvcHost.exe.config aufnehmen (diese Änderungen werden erst durch einen Neustart des SMSvc.exe-Prozesses wirksam).  
  
> [!NOTE]
> Auf Windows Vista-Systemen, auf denen die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, benötigen lokale Benutzer erhöhte Berechtigungen, auch wenn Ihr Konto Mitglied der Gruppe "Administratoren" ist. Damit diese Benutzer den Port Freigabe Dienst ohne Rechte Erweiterung nutzen können, muss die SID des Benutzers (oder die SID einer Gruppe, in der der Benutzer Mitglied ist) explizit dem Abschnitt \<allowaccounts > der Datei SMSvcHost. exe. config hinzugefügt werden.  
  
> [!WARNING]
> In der Standarddatei SMSvcHost.exe.config wird eine benutzerdefinierte `etwProviderId` angeben, um zu verhindern, dass Konflikte zwischen der SMSvcHost.exe-Ablaufverfolgung und Dienstablaufverfolgungen auftreten.  
  
## <a name="see-also"></a>Siehe auch

- [\<net.tcp>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
