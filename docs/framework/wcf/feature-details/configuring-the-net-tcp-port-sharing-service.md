---
title: Konfigurieren des Net.TCP-Portfreigabediensts
ms.date: 03/30/2017
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
ms.openlocfilehash: 9bc625f9e998f27b6227a5951f11c7d85220ae7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585522"
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
 Im Allgemeinen sollten Sie vorsichtig sein, wenn Sie den Inhalt der Datei SMSvcHost.exe.config ändern, weil jede in dieser Datei angegebene Konfigurationseinstellung alle Dienste eines Computers betrifft, die den Net.TCP-Portfreigabedienst verwenden. Dies schließt Anwendungen unter [!INCLUDE[wv](../../../../includes/wv-md.md)] ein, die die TCP-Aktivierungsfunktionen von WAS (Windows Process Activation Service) verwenden.  
  
 Sie müssen jedoch möglicherweise manchmal die Standardkonfiguration für den Net.TCP-Portfreigabedienst ändern. Beispielsweise ist der Standardwert für `maxPendingAccepts` 4 * Anzahl von Prozessoren. Auf Servern, die eine große Anzahl von Diensten hosten, die die Portfreigabe verwenden, kann dieser Wert erhöht werden, um einen höheren Maximaldurchsatz zu erzielen. Der Standardwert von `maxPendingConnections` ist 100. Sie können diesen Wert auch erhöhen, wenn der Dienst von mehreren Clients gleichzeitig aufgerufen wird und Clientverbindungen verloren gehen.  
  
 SMSvcHost.exe.config enthält auch Informationen über die Prozessidentitäten, die möglicherweise den Anschlussfreigabedienst nutzen. Wenn ein Prozess eine Verbindung zu einem Anschlussfreigabedienst herstellt, um einen freigegebenen TCP-Anschluss zu verwenden, wird die Prozessidentität des verbindenden Prozesses mit einer Liste der Identitäten verglichen, die den Anschlussfreigabedienst verwenden dürfen. Diese Identitäten werden als Sicherheits-IDs (SIDs) angegeben, der \<AllowAccounts >-Abschnitt der Datei "SMSvcHost.exe.config". Die Berechtigung, den Anschlussfreigabedienst verwenden zu dürfen, wird standardmäßig Systemkonten (LocalService, LocalSystem und NetworkService) sowie Mitgliedern der Administratorgruppe gewährt. Anwendungen, die einem Prozess erlauben, mit einer anderen Identität (beispielsweise einer Benutzeridentität) die Verbindung mit dem Anschlussfreigabedienst herzustellen, müssen die entsprechende SID explizit in die Datei SMSvcHost.exe.config aufnehmen (diese Änderungen werden erst durch einen Neustart des SMSvc.exe-Prozesses wirksam).  
  
> [!NOTE]
>  Auf [!INCLUDE[wv](../../../../includes/wv-md.md)]-Systemen, auf denen die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, benötigen lokale Benutzer erweiterte Berechtigungen, auch wenn ihr Konto Mitglied der Administratorgruppe ist. Diese Benutzer stellen können Verwendung des anschlussfreigabediensts ohne, die SID des Benutzers (oder die SID einer Gruppe, in denen der Benutzer Mitglied ist) muss explizit hinzugefügt werden, um die \<AllowAccounts > im Abschnitt "SMSvcHost.exe.config".  
  
> [!WARNING]
>  In der Standarddatei SMSvcHost.exe.config wird eine benutzerdefinierte `etwProviderId` angeben, um zu verhindern, dass Konflikte zwischen der SMSvcHost.exe-Ablaufverfolgung und Dienstablaufverfolgungen auftreten.  
  
## <a name="see-also"></a>Siehe auch
- [\<net.tcp>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
