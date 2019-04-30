---
title: Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: a4312a9affc1103f613f3f8ffd9a14696f9d4bcc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972613"
---
# <a name="internet-information-services-hosting-best-practices"></a>Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
Dieses Thema beschreibt einige bewährten Methoden zum Hosten von Diensten für Windows Communication Foundation (WCF).  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementieren von WCF-Diensten als DLLs  
 Implementieren eines WCFS ermöglicht Service als DLL, die in das Verzeichnis "\bin" von einer Webanwendung bereitgestellt wird, dass Sie den Dienst außerhalb des webanwendungsmodells, z. B. in einer testumgebung wiederverwenden, die möglicherweise nicht über Internet Information Services (IIS) bereitgestellt haben.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Diensthosts in IIS-gehosteten Anwendungen  
 Verwenden Sie keine imperativen Selbsthosting-APIs zur Erstellung neuer Diensthosts, die bei Netzwerktransporten lauschen, die nicht systemseitig von der IIS-Hostumgebung unterstützt werden (z. B. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] zum Hosten von TCP-Diensten, da die TCP-Kommunikation nicht systemseitig von [!INCLUDE[iis601](../../../../includes/iis601-md.md)] unterstützt wird). Diese Vorgehensweise ist nicht empfehlenswert. Imperativ erstellte Diensthosts sind innerhalb der IIS-Hostumgebung nicht bekannt. Die Schwierigkeit liegt darin, dass Verarbeitungen, die von imperativ erstellten Diensten ausgeführt werden, von IIS bei der Ermittlung, ob der Hostanwendungspool im Leerlauf ist, nicht berücksichtigt werden. Das Ergebnis ist, dass Anwendungen, die über solche imperativ erstellten Diensthosts verfügen, sich in einer IIS-Hostumgebung befinden, die IIS-Hostprozesse aggressiv freigibt.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URIs und IIS-gehostete Endpunkte  
 Endpunkte für einen IIS-gehosteten Dienst sollten mit relativen URIs (Uniform Resource Identifier) statt mit absoluten Adressen konfiguriert werden. Dadurch wird sichergestellt, dass die Endpunktadresse innerhalb des Satzes von URI-Adressen liegt, die zur Hostanwendung gehören und dafür sorgen, dass die nachrichtenbasierte Aktivierung wie erwartet ausgeführt wird.  
  
## <a name="state-management-and-process-recycling"></a>Zustandsverwaltung und Prozesswiederverwendung  
 Die IIS-Hostumgebung ist für Dienste optimiert, die keinen lokalen Zustand im Arbeitsspeicher speichern. IIS verwendet den Hostprozess als Reaktion auf verschiedene externe und interne Ereignisse wieder, was dazu führt, dass Daten, die ausschließlich im Arbeitsspeicher im flüchtigen Zustand gespeichert werden, verloren gehen. In IIS gehostete Dienste sollten ihren Status prozessextern speichern (beispielsweise in einer Datenbank) oder in einem speicherinternen Cache, der einfach wiederhergestellt werden kann, wenn ein Wiederverwendungsereignis für eine Anwendung eintritt.  
  
> [!NOTE]
>  Die Protokolle für die Message Layer-Zuverlässigkeit und Sicherheit des WCF-verwendet, nutzen den flüchtigen speicherinternen Zustand. Zuverlässige WCF--Sitzungen und-sicherheitssitzungen können aufgrund von anwendungswiederverwendungen unerwartet beendet. IIS-gehosteten Anwendungen sorgen dafür, diese Protokolle verwenden entweder einen anderen Wert als der von WCF bereitgestellter Sitzungsschlüssel für das Korrelieren der Anwendungsschicht-Zustand (z. B. eine Anwendungsschicht-Konstrukt oder benutzerdefinierten korrelationsheader) oder deaktivieren abhängen soll IIS-Prozess für die gehostete Anwendung wiederverwenden.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimieren der Leistung in Szenarien der mittleren Ebene  
 Für eine optimale Leistung in einer *Szenario der mittleren Ebene*– ein Dienst, der die anderen Dienste als Reaktion auf eingehende Nachrichten aufruft, den WCF-Dienst-Client an den Remotedienst einmal instanziiert und über mehrere eingehende wiederzuverwenden Anforderungen. Instanziieren von WCF-Dienstclients ein aufwendiger Vorgang im Vergleich zum Tätigen eines Dienstaufrufs für eine bereits vorhandene Clientinstanz ist, und Szenarien der mittleren Ebene deutliche Leistungssteigerungen durch die Zwischenspeicherung von Remoteclients auf Anforderungen. WCF-Dienstclients sind threadsicher, daher es nicht erforderlich ist, um Zugriff auf einen Client über mehrere Threads zu synchronisieren.  
  
 Szenarien der mittleren Ebene erzeugen außerdem Leistungssteigerungen durch Verwendung von asynchronen, von der `svcutil /a`-Option generierten APIs. Die `/a` -Option bewirkt, dass die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generieren `BeginXXX/EndXXX` Methoden für jeden Dienstvorgang, wodurch potenziell zeitintensive Aufrufe an Remotedienste auf Hintergrundthreads.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in Szenarien mit mehreren Adressen oder mehreren Namen  
 Können Sie WCF-Dienste innerhalb einer IIS-Webfarm, die einen gemeinsamen externen Namen zum Weiterleiten von einer Gruppe von Computern bereitstellen (z. B. `http://www.contoso.com`) jedoch einzeln mithilfe der verschiedenen Hostnamen adressiert sind (z. B. `http://www.contoso.com` möglicherweise Weiterleitung von Datenverkehr an zwei verschiedenen Computern mit dem Namen `http://machine1.internal.contoso.com` und `http://machine2.internal.contoso.com`). Bei diesem Bereitstellungsszenario wird vollständig von WCF unterstützt, erfordert jedoch spezielle Konfiguration der IIS-Website Hosten von WCF-Dienste, um die richtige (externe) Hostname in den Dienstmetadaten (Web Services Description Language) anzuzeigen.  
  
 Um sicherzustellen, dass der richtige Hostname in den Metadaten des WCF wird generiert, konfigurieren die Standardidentität für die IIS-Website, die WCF-Diensten für die Verwendung eines expliziten Hostnamens hostet. Z. B. Computer, die sich innerhalb des befinden die `www.contoso.com` Farm sollte verwenden Sie eine IIS-sitebindung *: 80: www.contoso.com für HTTP und \*: 443:www.contoso.com für HTTPS.  
  
 Sie können IIS-Websitebindungen konfigurieren, indem Sie das IIS-Snap-In der Microsoft Management Console (MMC) verwenden.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, überschreiben Assemblys anderer Konten im temporären Ordner.  
 Um sicherzustellen, dass Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, keine Assemblys anderer Konten im temporären [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Dateiordner überschreiben können, verwenden Sie unterschiedliche Identitäten und unterschiedliche Ordner für unterschiedliche Anwendungen. Wenn Sie beispielsweise zwei virtuelle Anwendungen /Application1 und /Application2 haben, können Sie zwei Anwendungspools (A und B) mit zwei unterschiedlichen Identitäten erstellen. Der Anwendungspool A kann unter einer Benutzeridentität ausgeführt werden (user1), während der Anwendungspool B unter einer anderen Benutzeridentität (user2) ausgeführt wird. Konfigurieren Sie /Application1 zur Verwendung von A und /Application2 zur Verwendung von B.  
  
 In der Datei "Web.config", können Sie konfigurieren, den temporären Ordner mit \< system.web/compilation/@tempFolder>. Für/Application1 kann es "c:\tempForUser1" sein kann, und für/application2 kann es "c:\tempForUser2" sein. Gewähren Sie den beiden Identitäten die entsprechende Schreibberechtigung für diese Ordner.  
  
 Dann kann user2 den Codegenerierungsordner für /application2 (unter c:\tempForUser1) nicht ändern.  
  
## <a name="enabling-asynchronous-processing"></a>Aktivieren der asynchronen Verarbeitung  
 Standardmäßig werden Nachrichten an einen WCF-Dienst gehostet wird unter IIS 6.0 und früher auf synchrone Weise verarbeitet. ASP.NET ruft in WCF in einem eigenen Thread (den ASP.NET-Arbeitsthread) auf und WCF verwendet einen anderen Thread zum Verarbeiten der Anforderung. WCF hält die Verbindung zum ASP.NET-Arbeitsthread aufrecht, bis die Verarbeitung abgeschlossen ist. Dies hat die synchrone Verarbeitung von Anforderungen zur Folge. Größere Skalierbarkeit asynchron verarbeiten von Anforderungen ermöglicht werden, da es die Anzahl von Threads zum Verarbeiten einer Anforderung, die verringert – WCF nicht zum ASP.NET-Thread aufrecht beim Verarbeiten der Anforderung erhalten werden erforderlich. Verwendung asynchronen Verhaltens wird nicht empfohlen, für Computer mit IIS 6.0, da es keine Möglichkeit gibt, eingehende Anforderungen zu drosseln, die der Server öffnen *Denial-Of-Service-* Angriffe (DOS). Ab IIS 7.0, eine parallele abfragedrosselung wurde eingeführt: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Aufgrund dieser neuen Drosselung kann die asynchrone Verarbeitung nun gefahrlos eingesetzt werden.  In IIS 7.0 werden der asynchrone Handler und das Modul standardmäßig registriert. Wenn dies deaktiviert wurde, können Sie die asynchrone Verarbeitung von Anforderungen in der Datei Web.config der Anwendung manuell aktivieren. Die verwendeten Einstellungen richten sich nach Ihrer `aspNetCompatibilityEnabled`-Einstellung. Wenn `aspNetCompatibilityEnabled` auf `false` festgelegt ist, konfigurieren Sie `System.ServiceModel.Activation.ServiceHttpModule` wie im folgenden Konfigurationsausschnitt dargestellt.  
  
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

- [Beispiele für Diensthosting](../samples/hosting.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
