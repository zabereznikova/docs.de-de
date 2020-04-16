---
title: Konfigurieren des Net.TCP-Portfreigabediensts
ms.date: 03/30/2017
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
ms.openlocfilehash: fea2e734099c4c623dcde2a37f4c164cf9ce61ac
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464199"
---
# <a name="configuring-the-nettcp-port-sharing-service"></a><span data-ttu-id="1f3f9-102">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="1f3f9-102">Configuring the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="1f3f9-103">Selbst gehostete Dienste, die den Net.TCP-Transport verwenden, können erweiterte Einstellungen festlegen, etwa `ListenBacklog` und `MaxPendingAccepts`, die das Verhalten des zugrunde liegenden, für die Netzwerkkommunikation verwendeten TCP-Sockets bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-103">Self-hosted services that use the Net.TCP transport can control several advanced settings, such as `ListenBacklog` and `MaxPendingAccepts`, which govern the behavior of the underlying TCP socket used for network communication.</span></span> <span data-ttu-id="1f3f9-104">Diese Einstellungen werden auf Bindungsebene jedoch nur für jeden Socket wirksam, wenn die Transportbindung die standardmäßig aktivierte Anschlussfreigabe deaktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-104">However, these settings for each socket only apply at the binding level if the transport binding has disabled port sharing, which is enabled by default.</span></span>  
  
 <span data-ttu-id="1f3f9-105">Wenn eine Net.TCP-Bindung die Anschlussfreigabe aktiviert (indem für das Transportbindungselement `portSharingEnabled =true` festgelegt wird), erlaubt sie implizit einem externen Prozess (nämlich dem Prozess SMSvcHost.exe, der den Net.TCP-Portfreigabedienst hostet), den TCP-Socket in ihrem Namen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-105">When a net.tcp binding enables port sharing (by setting `portSharingEnabled =true` on the transport binding element), it implicitly allows an external process (namely the SMSvcHost.exe, which hosts the Net.TCP Port Sharing Service) to manage the TCP socket on its behalf.</span></span> <span data-ttu-id="1f3f9-106">Geben Sie zum Beispiel, wenn Sie TCP verwenden, Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="1f3f9-106">For example, when using TCP, specify:</span></span>  
  
```xml  
<tcpTransport portSharingEnabled="true"  />  
```  
  
 <span data-ttu-id="1f3f9-107">Die Einstellungen eines auf diese Weise konfigurierten Sockets, die mit dem Transportbindungselement des Diensts angegeben wurden, werden zugunsten der von SMSvcHost.exe angegebenen Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-107">When configured in this way, any socket settings specified on the service's transport binding element are ignored in favor of the socket settings specified by SMSvcHost.exe.</span></span>  
  
 <span data-ttu-id="1f3f9-108">Erstellen Sie zum Konfigurieren von SMSvcHost.exe eine XML-Konfigurationsdatei mit dem Namen "SmSvcHost.exe.config", und platzieren Sie sie im gleichen physischen Verzeichnis wie die ausführbare Datei "SMSvcHost.exe" (zum Beispiel unter "C:\Windows\Microsoft.NET\Framework\v4.5").</span><span class="sxs-lookup"><span data-stu-id="1f3f9-108">To configure the SMSvcHost.exe, create an XML configuration file named SmSvcHost.exe.config and place it in the same physical directory as the SMSvcHost.exe executable (for example, C:\Windows\Microsoft.NET\Framework\v4.5).</span></span>  
  
 <span data-ttu-id="1f3f9-109">Im folgenden Beispiel wird eine SMSvcHost.exe.config-Datei gezeigt, in der alle konfigurierbaren Werte explizit mit den Standardeinstellungen festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-109">The following example illustrates a sample SMSvcHost.exe.config, with the default settings for all configurable values stated explicitly.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!-- 16 * # of processors -->  
          maxPendingAccepts="4"<!-- 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!-- 30 seconds -->  
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
    </system.serviceModel.activation>
</configuration>  
```  
  
## <a name="when-to-modify-smsvchostexeconfig"></a><span data-ttu-id="1f3f9-110">Wann SMSvcHost.exe.config zu ändern ist</span><span class="sxs-lookup"><span data-stu-id="1f3f9-110">When to Modify SMSvcHost.exe.config</span></span>  
 <span data-ttu-id="1f3f9-111">Im Allgemeinen sollten Sie vorsichtig sein, wenn Sie den Inhalt der Datei SMSvcHost.exe.config ändern, weil jede in dieser Datei angegebene Konfigurationseinstellung alle Dienste eines Computers betrifft, die den Net.TCP-Portfreigabedienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-111">In general, care should be taken when modifying the contents of the SMSvcHost.exe.config file, because any configuration settings specified in this file affect all of the services on a computer that uses the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="1f3f9-112">Dazu gehören Anwendungen unter Windows Vista, die die TCP-Aktivierungsfunktionen des Windows-Prozessaktivierungsdienstes (WINDOWS Process Activation Service, WAS) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-112">This includes applications on Windows Vista that use the TCP Activation features of the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="1f3f9-113">Sie müssen jedoch möglicherweise manchmal die Standardkonfiguration für den Net.TCP-Portfreigabedienst ändern.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-113">However, sometimes you may need to change the default configuration for the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="1f3f9-114">Beispielsweise ist der Standardwert für `maxPendingAccepts` 4 \* Anzahl von Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-114">For example, the default value for `maxPendingAccepts` is 4 \* number of processors.</span></span> <span data-ttu-id="1f3f9-115">Auf Servern, die eine große Anzahl von Diensten hosten, die die Portfreigabe verwenden, kann dieser Wert erhöht werden, um einen höheren Maximaldurchsatz zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-115">Servers that host a large number of services that use port sharing may increase this value to achieve maximum throughput.</span></span> <span data-ttu-id="1f3f9-116">Der Standardwert von `maxPendingConnections` ist 100.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-116">The default value for `maxPendingConnections` is 100.</span></span> <span data-ttu-id="1f3f9-117">Sie können diesen Wert auch erhöhen, wenn der Dienst von mehreren Clients gleichzeitig aufgerufen wird und Clientverbindungen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-117">You should consider increasing this value also if there are multiple concurrent clients calling the service and the service is dropping client connections.</span></span>  
  
 <span data-ttu-id="1f3f9-118">SMSvcHost.exe.config enthält auch Informationen über die Prozessidentitäten, die möglicherweise den Anschlussfreigabedienst nutzen.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-118">SMSvcHost.exe.config also contains information about the process identities that may make use of the port sharing service.</span></span> <span data-ttu-id="1f3f9-119">Wenn ein Prozess eine Verbindung zu einem Anschlussfreigabedienst herstellt, um einen freigegebenen TCP-Anschluss zu verwenden, wird die Prozessidentität des verbindenden Prozesses mit einer Liste der Identitäten verglichen, die den Anschlussfreigabedienst verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-119">When a process connects to the port sharing service to make use of a shared TCP port, the process identity of the connecting process is checked against a list of identities that are permitted to make use of the port sharing service.</span></span> <span data-ttu-id="1f3f9-120">Diese Identitäten werden als Sicherheitskennungen (Security \<Identifiers, SIDs) im Abschnitt allowAccounts> der Datei SMSvcHost.exe.config angegeben.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-120">These identities are specified as security identifiers (SIDs) in the \<allowAccounts> section of the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="1f3f9-121">Die Berechtigung, den Anschlussfreigabedienst verwenden zu dürfen, wird standardmäßig Systemkonten (LocalService, LocalSystem und NetworkService) sowie Mitgliedern der Administratorgruppe gewährt.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-121">By default, permission to use the port sharing service is granted to system accounts (LocalService, LocalSystem, and NetworkService) as well as members of the Administrators group.</span></span> <span data-ttu-id="1f3f9-122">Anwendungen, die einem Prozess erlauben, mit einer anderen Identität (beispielsweise einer Benutzeridentität) die Verbindung mit dem Anschlussfreigabedienst herzustellen, müssen die entsprechende SID explizit in die Datei SMSvcHost.exe.config aufnehmen (diese Änderungen werden erst durch einen Neustart des SMSvc.exe-Prozesses wirksam).</span><span class="sxs-lookup"><span data-stu-id="1f3f9-122">Applications that allow a process running as another identity (for example, a user identity) to connect to the port sharing service must explicitly add the appropriate SID to the SMSvcHost.exe.config (these changes are not applied until the SMSvc.exe process is restarted).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f3f9-123">Auf Windows Vista-Systemen, auf denen die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, benötigen lokale Benutzer erhöhte Berechtigungen, auch wenn ihr Konto Mitglied der Gruppe Administratoren ist.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-123">On Windows Vista systems with User Account Control (UAC) enabled, local users require elevated permissions even if their account is a member of the Administrators group.</span></span> <span data-ttu-id="1f3f9-124">Damit diese Benutzer den Portfreigabedienst ohne Erhöhung nutzen können, muss die SID des Benutzers (oder die SID einer \<Gruppe, in der der Benutzer Mitglied ist) explizit zum> Abschnitt von SMSvcHost.exe.config hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-124">To allow these users to make use of the port sharing service without elevation, the user's SID (or the SID of a group in which the user is a member) must be explicitly added to the \<allowAccounts> section of SMSvcHost.exe.config.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="1f3f9-125">In der Standarddatei SMSvcHost.exe.config wird eine benutzerdefinierte `etwProviderId` angeben, um zu verhindern, dass Konflikte zwischen der SMSvcHost.exe-Ablaufverfolgung und Dienstablaufverfolgungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-125">The default SMSvcHost.exe.config file specifies a custom `etwProviderId` to prevent SMSvcHost.exe tracing from interfering with service traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3f9-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f3f9-126">See also</span></span>

- [<span data-ttu-id="1f3f9-127">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="1f3f9-127">\<net.tcp></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
