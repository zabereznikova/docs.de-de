---
title: Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 119f14df9d46883a33272903558d83128501b293
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="internet-information-services-hosting-best-practices"></a>Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
Dieses Thema beschreibt einige bewährten Methoden für das Hosten von Windows Communication Foundation (WCF)-Dienste an.  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementieren von WCF-Diensten als DLLs  
 Implementieren einen WCF ermöglicht Dienst als eine DLL, die in das Verzeichnis "\bin" einer Webanwendung bereitgestellt wird, dass Sie den Dienst außerhalb des webanwendungsmodells, z. B. in einer testumgebung wiederverwenden, die möglicherweise keine Internet Information Services (IIS) bereitgestellt.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Diensthosts in IIS-gehosteten Anwendungen  
 Verwenden Sie keine imperativen Selbsthosting-APIs zur Erstellung neuer Diensthosts, die bei Netzwerktransporten lauschen, die nicht systemseitig von der IIS-Hostumgebung unterstützt werden (z. B. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] zum Hosten von TCP-Diensten, da die TCP-Kommunikation nicht systemseitig von [!INCLUDE[iis601](../../../../includes/iis601-md.md)] unterstützt wird). Diese Vorgehensweise ist nicht empfehlenswert. Imperativ erstellte Diensthosts sind innerhalb der IIS-Hostumgebung nicht bekannt. Die Schwierigkeit liegt darin, dass Verarbeitungen, die von imperativ erstellten Diensten ausgeführt werden, von IIS bei der Ermittlung, ob der Hostanwendungspool im Leerlauf ist, nicht berücksichtigt werden. Das Ergebnis ist, dass Anwendungen, die über solche imperativ erstellten Diensthosts verfügen, sich in einer IIS-Hostumgebung befinden, die IIS-Hostprozesse aggressiv freigibt.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URIs und IIS-gehostete Endpunkte  
 Endpunkte für einen IIS-gehosteten Dienst sollten mit relativen URIs (Uniform Resource Identifier) statt mit absoluten Adressen konfiguriert werden. Dadurch wird sichergestellt, dass die Endpunktadresse innerhalb des Satzes von URI-Adressen liegt, die zur Hostanwendung gehören und dafür sorgen, dass die nachrichtenbasierte Aktivierung wie erwartet ausgeführt wird.  
  
## <a name="state-management-and-process-recycling"></a>Zustandsverwaltung und Prozesswiederverwendung  
 Die IIS-Hostumgebung ist für Dienste optimiert, die keinen lokalen Zustand im Arbeitsspeicher speichern. IIS verwendet den Hostprozess als Reaktion auf verschiedene externe und interne Ereignisse wieder, was dazu führt, dass Daten, die ausschließlich im Arbeitsspeicher im flüchtigen Zustand gespeichert werden, verloren gehen. In IIS gehostete Dienste sollten ihren Status prozessextern speichern (beispielsweise in einer Datenbank) oder in einem speicherinternen Cache, der einfach wiederhergestellt werden kann, wenn ein Wiederverwendungsereignis für eine Anwendung eintritt.  
  
> [!NOTE]
>  Die Protokolle für nachrichtenebenen-Zuverlässigkeit und Sicherheit WCF vornehmen Verwenden des flüchtigen speicherinternen Status. Zuverlässige WCF--Sitzungen und-sicherheitssitzungen möglicherweise aufgrund von anwendungswiederverwendungen unerwartet beendet. IIS-gehosteten Anwendungen stellen diese Protokolle verwenden entweder auf einen anderen Wert als den bereitgestellten WCF Sitzungsschlüssel für das Korrelieren von Anwendungsschicht Status (z. B. eine Anwendung oder einem benutzerdefinierten korrelationsheader) oder deaktivieren abhängen sollen IIS-Prozess für die gehostete Anwendung wiederverwenden.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimieren der Leistung in Szenarien der mittleren Ebene  
 Für eine optimale Leistung einer *Szenario der mittleren Ebene*– ein Dienst, der Reaktion auf eingehende Nachrichten andere Dienste aufruft – einmal, die WCF-Dienst-Client an den Remotedienst zu instanziieren und diesen über mehrere eingehende wiederverwenden, Anforderungen. Instanziieren von WCF-Webdienstclients ist ein teurer Vorgang relativ zum Erstellen eines Diensts in einer bereits vorhandene Clientinstanz aufrufen und Szenarien der mittleren Ebene erzeugen deutliche Leistungssteigerungen durch Remoteclients anforderungsübergreifend Zwischenspeichern. WCF-Dienstclients sind threadsicher, daher ist es nicht notwendig, die Zugriff auf einen Client über mehrere Threads hinweg synchronisiert.  
  
 Szenarien der mittleren Ebene erzeugen außerdem Leistungssteigerungen durch Verwendung von asynchronen, von der `svcutil /a`-Option generierten APIs. Die `/a` -Option bewirkt, dass die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generieren `BeginXXX/EndXXX` Methoden für jeden Dienstvorgang, wodurch potenziell langer Aufrufe Remotedienste auf vorgenommen werden Hintergrundthreads ausgeführt.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in Szenarien mit mehreren Adressen oder mehreren Namen  
 Sie können WCF-Dienste innerhalb einer IIS-Webfarm, eine Gruppe von Computern freigeben, in einen gemeinsamen externen Namen bereitstellen (z. B. http://www.contoso.com) jedoch einzeln von Hostnamen adressiert wird (z. B. http://www.contoso.com möglicherweise Weiterleitung von Datenverkehr an zwei verschiedenen Computern mit dem Namen http://machine1.internal.contoso.com und http://machine2.internal.contoso.com). Bei diesem Bereitstellungsszenario wird vollständig von WCF unterstützt, erfordert jedoch spezielle Konfiguration für die IIS-Website zum Hosten von WCF-Diensten für der richtige (externe) Hostname in den Dienstmetadaten (Web Services Description Language) angezeigt.  
  
 Um sicherzustellen, dass der richtige Hostname in den Dienstmetadaten WCF wird generiert, konfigurieren die Standardidentität für die IIS-Website, die WCF-Diensten für die Verwendung eines expliziten Hostnamens hostet. Z. B. Computer, die innerhalb der Webfarm www.contoso.com befinden zu verwendende eine IIS-sitebindung *: 80: www.contoso.com für HTTP und \*: 443:www.contoso.com für HTTPS.  
  
 Sie können IIS-Websitebindungen konfigurieren, indem Sie das IIS-Snap-In der Microsoft Management Console (MMC) verwenden.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, überschreiben Assemblys anderer Konten im temporären Ordner.  
 Um sicherzustellen, dass Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, keine Assemblys anderer Konten im temporären [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Dateiordner überschreiben können, verwenden Sie unterschiedliche Identitäten und unterschiedliche Ordner für unterschiedliche Anwendungen. Wenn Sie beispielsweise zwei virtuelle Anwendungen /Application1 und /Application2 haben, können Sie zwei Anwendungspools (A und B) mit zwei unterschiedlichen Identitäten erstellen. Der Anwendungspool A kann unter einer Benutzeridentität ausgeführt werden (user1), während der Anwendungspool B unter einer anderen Benutzeridentität (user2) ausgeführt wird. Konfigurieren Sie /Application1 zur Verwendung von A und /Application2 zur Verwendung von B.  
  
 In der Datei "Web.config", können Sie konfigurieren, den temporären Ordner mit \< system.web/compilation/@tempFolder>. Für/Application1 kann es "c:\tempForUser1" sein kann, und für/application2 kann es "c:\tempForUser2" sein. Gewähren Sie den beiden Identitäten die entsprechende Schreibberechtigung für diese Ordner.  
  
 Dann kann user2 den Codegenerierungsordner für /application2 (unter c:\tempForUser1) nicht ändern.  
  
## <a name="enabling-asynchronous-processing"></a>Aktivieren der asynchronen Verarbeitung  
 Standardmäßig werden an einen unter IIS 6.0 und früher gehosteten WCF-Dienst gesendete Nachrichten synchron verarbeitet. ASP.NET ruft in WCF in einem eigenen Thread (den ASP.NET-Arbeitsthread) und WCF verwendet einen anderen Thread zum Verarbeiten der Anforderung. WCF hält die Verbindung zum ASP.NET-Arbeitsthread aufrecht, bis die Verarbeitung abgeschlossen ist. Dies hat die synchrone Verarbeitung von Anforderungen zur Folge. Verarbeitung von Anforderungen schafft ermöglicht größere Skalierbarkeit, das er reduziert die Anzahl der Threads zum Verarbeiten einer Anforderung, die – WCF nicht zum ASP.NET-Thread aufrecht beim Verarbeiten der Anforderung erhalten werden erforderlich. Verwendung des asynchronen Verhaltens wird nicht empfohlen, für Computer mit IIS 6.0, da es keine Möglichkeit für die Beschränkung von eingehender Anforderungen, die Sicherung des Servers zu öffnen *Denial-Of-Service-* -Angriffe (DOS). Beginnend mit IIS 7.0, eine gleichzeitige Anforderungen Drosselung wurde eingeführt: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Aufgrund dieser neuen Drosselung kann die asynchrone Verarbeitung nun gefahrlos eingesetzt werden.  In IIS 7.0 werden der asynchrone Handler und das Modul standardmäßig registriert. Wenn dies deaktiviert wurde, können Sie die asynchrone Verarbeitung von Anforderungen in der Datei Web.config der Anwendung manuell aktivieren. Die verwendeten Einstellungen richten sich nach Ihrer `aspNetCompatibilityEnabled`-Einstellung. Wenn `aspNetCompatibilityEnabled` auf `false` festgelegt ist, konfigurieren Sie `System.ServiceModel.Activation.ServiceHttpModule` wie im folgenden Konfigurationsausschnitt dargestellt.  
  
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
 [Dienst-Hosting-Beispiele](http://msdn.microsoft.com/library/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
