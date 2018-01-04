---
title: "Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8593b9ceb579f33ba3b37975d88b37f3f5ab628
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="internet-information-services-hosting-best-practices"></a>Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
In diesem Thema werden einige empfohlene Vorgehensweisen für das Hosten von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensten beschrieben.  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementieren von WCF-Diensten als DLLs  
 Die Implementierung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts als DLL, die im \bin-Verzeichnis einer Webanwendung bereitgestellt wird, ermöglicht es Ihnen, den Dienst außerhalb des Webanwendungsmodells wiederzuverwenden, beispielsweise in einer Testumgebung, für die Internetinformationsdienste (IIS) möglicherweise nicht bereitgestellt wurden.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Diensthosts in IIS-gehosteten Anwendungen  
 Verwenden Sie keine imperativen Selbsthosting-APIs zur Erstellung neuer Diensthosts, die bei Netzwerktransporten lauschen, die nicht systemseitig von der IIS-Hostumgebung unterstützt werden (z. B. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] zum Hosten von TCP-Diensten, da die TCP-Kommunikation nicht systemseitig von [!INCLUDE[iis601](../../../../includes/iis601-md.md)] unterstützt wird). Diese Vorgehensweise ist nicht empfehlenswert. Imperativ erstellte Diensthosts sind innerhalb der IIS-Hostumgebung nicht bekannt. Die Schwierigkeit liegt darin, dass Verarbeitungen, die von imperativ erstellten Diensten ausgeführt werden, von IIS bei der Ermittlung, ob der Hostanwendungspool im Leerlauf ist, nicht berücksichtigt werden. Das Ergebnis ist, dass Anwendungen, die über solche imperativ erstellten Diensthosts verfügen, sich in einer IIS-Hostumgebung befinden, die IIS-Hostprozesse aggressiv freigibt.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URIs und IIS-gehostete Endpunkte  
 Endpunkte für einen IIS-gehosteten Dienst sollten mit relativen URIs (Uniform Resource Identifier) statt mit absoluten Adressen konfiguriert werden. Dadurch wird sichergestellt, dass die Endpunktadresse innerhalb des Satzes von URI-Adressen liegt, die zur Hostanwendung gehören und dafür sorgen, dass die nachrichtenbasierte Aktivierung wie erwartet ausgeführt wird.  
  
## <a name="state-management-and-process-recycling"></a>Zustandsverwaltung und Prozesswiederverwendung  
 Die IIS-Hostumgebung ist für Dienste optimiert, die keinen lokalen Zustand im Arbeitsspeicher speichern. IIS verwendet den Hostprozess als Reaktion auf verschiedene externe und interne Ereignisse wieder, was dazu führt, dass Daten, die ausschließlich im Arbeitsspeicher im flüchtigen Zustand gespeichert werden, verloren gehen. In IIS gehostete Dienste sollten ihren Status prozessextern speichern (beispielsweise in einer Datenbank) oder in einem speicherinternen Cache, der einfach wiederhergestellt werden kann, wenn ein Wiederverwendungsereignis für eine Anwendung eintritt.  
  
> [!NOTE]
>  Die Protokolle, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] für die Zuverlässigkeit und Sicherheit auf Nachrichtenebene verwendet, nutzen den flüchtigen speicherinternen Status. Zuverlässige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sitzungen und -Sicherheitssitzungen können unter Umständen aufgrund von Anwendungswiederverwendungen unerwartet beendet werden. In IIS gehostete Anwendungen, die diese Protokolle verwenden, sollten sich beim Korrelieren des Anwendungsschichtstatus entweder nach etwas anderem als dem von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Sitzungsschlüssel richten (beispielsweise einem Anwendungsschichtkonstrukt oder einem benutzerdefinierten Korrelationsheader) oder die Wiederverwendung von IIS-Prozessen für die gehostete Anwendung deaktivieren.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimieren der Leistung in Szenarien der mittleren Ebene  
 Für eine optimale Leistung einer *Szenario der mittleren Ebene*– ein Dienst, der Reaktion auf eingehende Nachrichten andere Dienste aufruft – Instanziieren der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienstclient einmal für den Remotedienst und für mehrere wiederverwenden eingehende Anforderungen. Im Vergleich zum Ausführen eines Dienstaufrufs für eine bereits vorhandene Clientinstanz ist die Instanziierung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstclients ein aufwendiger Vorgang, und Szenarien der mittleren Ebene erbringen durch das anforderungsübergreifende Caching von Remoteclients deutliche Leistungssteigerungen. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstclients sind threadsicher, weshalb der Zugriff auf einen Client nicht über mehrere Threads hinweg synchronisiert werden muss.  
  
 Szenarien der mittleren Ebene erzeugen außerdem Leistungssteigerungen durch Verwendung von asynchronen, von der `svcutil /a`-Option generierten APIs. Die `/a` -Option bewirkt, dass die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generieren `BeginXXX/EndXXX` Methoden für jeden Dienstvorgang, wodurch potenziell langer Aufrufe Remotedienste auf vorgenommen werden Hintergrundthreads ausgeführt.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in Szenarien mit mehreren Adressen oder mehreren Namen  
 Sie können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste innerhalb einer IIS-Webfarm bereitstellen, in der ein Satz Computer einen gemeinsamen externen Namen hat (z.&#160;B. http://www.contoso.com), jedoch einzeln über einen individuellen Hostnamen adressiert wird (z.&#160;B. könnte http://www.contoso.com Datenverkehr an zwei verschiedene Computer mit den Namen http://machine1.internal.contoso.com und http://machine2.internal.contoso.com leiten). Dieses Bereitstellungsszenario wird vollständig von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt. Jedoch muss die IIS-Website, die die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste hostet, speziell konfiguriert werden, damit der richtige (externe) Hostname in den Metadaten des Diensts angezeigt wird (Web Services Description Language).  
  
 Um sicherzustellen, dass der richtige Hostname in den von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generierten Metadaten des Diensts angezeigt wird, konfigurieren Sie die Standardidentität für die IIS-Website, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste hostet, zur Verwendung eines expliziten Hostnamens. Z. B. Computer, die innerhalb der Webfarm www.contoso.com befinden zu verwendende eine IIS-sitebindung *: 80: www.contoso.com für HTTP und \*: 443:www.contoso.com für HTTPS.  
  
 Sie können IIS-Websitebindungen konfigurieren, indem Sie das IIS-Snap-In der Microsoft Management Console (MMC) verwenden.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, überschreiben Assemblys anderer Konten im temporären Ordner.  
 Um sicherzustellen, dass Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, keine Assemblys anderer Konten im temporären [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Dateiordner überschreiben können, verwenden Sie unterschiedliche Identitäten und unterschiedliche Ordner für unterschiedliche Anwendungen. Wenn Sie beispielsweise zwei virtuelle Anwendungen /Application1 und /Application2 haben, können Sie zwei Anwendungspools (A und B) mit zwei unterschiedlichen Identitäten erstellen. Der Anwendungspool A kann unter einer Benutzeridentität ausgeführt werden (user1), während der Anwendungspool B unter einer anderen Benutzeridentität (user2) ausgeführt wird. Konfigurieren Sie /Application1 zur Verwendung von A und /Application2 zur Verwendung von B.  
  
 In der Datei "Web.config", können Sie konfigurieren, den temporären Ordner mit \< system.web/compilation/@tempFolder>. Für/Application1 kann es "c:\tempForUser1" sein kann, und für/application2 kann es "c:\tempForUser2" sein. Gewähren Sie den beiden Identitäten die entsprechende Schreibberechtigung für diese Ordner.  
  
 Dann kann user2 den Codegenerierungsordner für /application2 (unter c:\tempForUser1) nicht ändern.  
  
## <a name="enabling-asynchronous-processing"></a>Aktivieren der asynchronen Verarbeitung  
 Standardmäßig werden Nachrichten, die an einen von IIS 6.0 und früher gehosteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst gesendet werden, synchron verarbeitet. ASP.NET ruft in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen eigenen Thread (den ASP.NET-Arbeitsthread) auf, und von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird zum Verarbeiten der Anforderung ein anderer Thread verwendet. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hält die Verbindung mit dem ASP.NET-Arbeitsthread aufrecht, bis die Verarbeitung abgeschlossen ist. Dies hat die synchrone Verarbeitung von Anforderungen zur Folge. Die asynchrone Verarbeitung von Anforderungen schafft größere Skalierbarkeit, da so die Anzahl der zur Verarbeitung einer Anforderung erforderlichen Threads reduziert wird. Während der Verarbeitung der Anforderung wird von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Verbindung zum ASP.NET-Thread nicht aufrecht erhalten. Verwendung des asynchronen Verhaltens wird nicht empfohlen, für Computer mit IIS 6.0, da es keine Möglichkeit für die Beschränkung von eingehender Anforderungen, die Sicherung des Servers zu öffnen *Denial-Of-Service-* -Angriffe (DOS). Beginnend mit IIS 7.0, eine gleichzeitige Anforderungen Drosselung wurde eingeführt: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Aufgrund dieser neuen Drosselung kann die asynchrone Verarbeitung nun gefahrlos eingesetzt werden.  In IIS 7.0 werden der asynchrone Handler und das Modul standardmäßig registriert. Wenn dies deaktiviert wurde, können Sie die asynchrone Verarbeitung von Anforderungen in der Datei Web.config der Anwendung manuell aktivieren. Die verwendeten Einstellungen richten sich nach Ihrer `aspNetCompatibilityEnabled`-Einstellung. Wenn `aspNetCompatibilityEnabled` auf `false` festgelegt ist, konfigurieren Sie `System.ServiceModel.Activation.ServiceHttpModule` wie im folgenden Konfigurationsausschnitt dargestellt.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="false" />      
  </system.serviceModel>  
  <system.webServer>  
    <modules>  
      <remove name="ServiceModel"/>  
      <add name="ServiceModel"   
           preCondition="integratedMode,runtimeVersionv2.0"   
           type="System.ServiceModel.Activation.ServiceHttpModule, System.ServiceModel,Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
    </modules>  
    </system.webServer>  
```  
  
 Wenn `aspNetCompatibilityEnabled` auf `true` festgelegt ist, konfigurieren Sie `System.ServiceModel.Activation.ServiceHttpHandlerFactory` wie im folgenden Konfigurationsausschnitt dargestellt.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />      
  </system.serviceModel>  
  <system.webServer>  
    <handlers>  
          <clear/>  
          <add name="TestAsyncHttpHandler"   
               path="*.svc"   
               verb="*"   
               type="System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"           
               />  
    </handlers>      
  </system.webServer>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dienst-Hosting-Beispiele](http://msdn.microsoft.com/en-us/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
