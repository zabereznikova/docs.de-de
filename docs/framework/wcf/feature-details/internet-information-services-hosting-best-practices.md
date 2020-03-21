---
title: Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 3be9d4c81f891ad898099ba9041a09b16388b7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184721"
---
# <a name="internet-information-services-hosting-best-practices"></a>Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
In diesem Thema werden einige bewährte Methoden zum Hosten von Windows Communication Foundation (WCF)-Diensten beschrieben.  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementieren von WCF-Diensten als DLLs  
 Durch das Implementieren eines WCF-Dienstes als DLL, die im Verzeichnis von 'bin' einer Webanwendung bereitgestellt wird, können Sie den Dienst außerhalb des Webanwendungsmodells wiederverwenden, z. B. in einer Testumgebung, in der möglicherweise keine Internetinformationsdienste (Internet Information Services, IIS) bereitgestellt werden.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Diensthosts in IIS-gehosteten Anwendungen  
 Verwenden Sie die imperativen Selbsthost-APIs nicht zum Erstellen neuer Diensthosts, die Netzwerktransporte abhören, die nicht nativ von der IIS-Hostingumgebung unterstützt werden (z. B. IIS 6.0 zum Hosten von TCP-Diensten, da TCP-Kommunikation auf IIS 6.0 nicht nativ unterstützt wird). Diese Vorgehensweise ist nicht empfehlenswert. Imperativ erstellte Diensthosts sind innerhalb der IIS-Hostumgebung nicht bekannt. Die Schwierigkeit liegt darin, dass Verarbeitungen, die von imperativ erstellten Diensten ausgeführt werden, von IIS bei der Ermittlung, ob der Hostanwendungspool im Leerlauf ist, nicht berücksichtigt werden. Das Ergebnis ist, dass Anwendungen, die über solche imperativ erstellten Diensthosts verfügen, sich in einer IIS-Hostumgebung befinden, die IIS-Hostprozesse aggressiv freigibt.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URIs und IIS-gehostete Endpunkte  
 Endpunkte für einen IIS-gehosteten Dienst sollten mit relativen URIs (Uniform Resource Identifier) statt mit absoluten Adressen konfiguriert werden. Dadurch wird sichergestellt, dass die Endpunktadresse innerhalb des Satzes von URI-Adressen liegt, die zur Hostanwendung gehören und dafür sorgen, dass die nachrichtenbasierte Aktivierung wie erwartet ausgeführt wird.  
  
## <a name="state-management-and-process-recycling"></a>Zustandsverwaltung und Prozesswiederverwendung  
 Die IIS-Hostumgebung ist für Dienste optimiert, die keinen lokalen Zustand im Arbeitsspeicher speichern. IIS verwendet den Hostprozess als Reaktion auf verschiedene externe und interne Ereignisse wieder, was dazu führt, dass Daten, die ausschließlich im Arbeitsspeicher im flüchtigen Zustand gespeichert werden, verloren gehen. In IIS gehostete Dienste sollten ihren Status prozessextern speichern (beispielsweise in einer Datenbank) oder in einem speicherinternen Cache, der einfach wiederhergestellt werden kann, wenn ein Wiederverwendungsereignis für eine Anwendung eintritt.  
  
> [!NOTE]
> Die Protokolle, die WCF für die Zuverlässigkeit und Sicherheit von Nachrichtenebenen verwendet, nutzen den flüchtigen In-Memory-Zustand. WCF-zuverlässige Sitzungen und Sicherheitssitzungen werden möglicherweise aufgrund von Anwendungsrecyclings unerwartet beendet. IIS-gehostete Anwendungen, die diese Protokolle verwenden, sollten entweder von etwas anderem als dem von WCF bereitgestellten Sitzungsschlüssel für die Korrelation des Anwendungsschichtstatus abhängen (z. B. ein Anwendungsschichtkonstrukt oder einen benutzerdefinierten Korrelationsheader) oder deaktivieren IIS-Prozessrecycling für die gehostete Anwendung.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimieren der Leistung in Szenarien der mittleren Ebene  
 Für eine optimale Leistung in einem *Szenario der mittleren Ebene*– einem Dienst, der als Reaktion auf eingehende Nachrichten an andere Dienste abruft – instanziiert der WCF-Dienstclient einmal an den Remotedienst und verwendet ihn über mehrere eingehende Anforderungen hinweg. Das Instanziieren von WCF-Dienstclients ist ein teurer Vorgang im Vergleich zum Ausführen eines Dienstaufrufs auf einer bereits vorhandenen Clientinstanz, und Szenarien der mittleren Ebene führen zu deutlichen Leistungssteigerungen, indem Remoteclients über Anforderungen hinweg zwischengesteuert werden. WCF-Dienstclients sind threadsicher, daher ist es nicht erforderlich, den Zugriff auf einen Client über mehrere Threads hinweg zu synchronisieren.  
  
 Szenarien der mittleren Ebene erzeugen außerdem Leistungssteigerungen durch Verwendung von asynchronen, von der `svcutil /a`-Option generierten APIs. Die `/a` Option bewirkt, dass das [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Methoden für jeden Dienstvorgang generiert, `BeginXXX/EndXXX` wodurch potenziell lang andauernde Aufrufe von Remotediensten in Hintergrundthreads ausgeführt werden können.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in Szenarien mit mehreren Adressen oder mehreren Namen  
 Sie können WCF-Dienste innerhalb einer IIS-Webfarm bereitstellen, bei der eine `http://www.contoso.com`Gruppe von Computern einen gemeinsamen externen `http://www.contoso.com` Namen (z. B. `http://machine1.internal.contoso.com` `http://machine2.internal.contoso.com`) verwendet, aber einzeln von verschiedenen Hostnamen adressiert wird (z. B. kann Datenverkehr an zwei verschiedene Computer mit dem Namen und weiterleiten). Dieses Bereitstellungsszenario wird vollständig von WCF unterstützt, erfordert jedoch eine spezielle Konfiguration der IIS-Website, die WCF-Dienste hostet, um den richtigen (externen) Hostnamen in den Metadaten des Dienstes anzuzeigen (Web Services Description Language).  
  
 Um sicherzustellen, dass der richtige Hostname in den Dienstmetadaten angezeigt wird, die WCF generiert, konfigurieren Sie die Standardidentität für die IIS-Website, die WCF-Dienste hostet, um einen expliziten Hostnamen zu verwenden. Computer, die sich innerhalb `www.contoso.com` der Farm befinden, sollten beispielsweise eine IIS-Sitebindung von *:80:www.contoso.com für HTTP und \*:443:www.contoso.com für HTTPS verwenden.  
  
 Sie können IIS-Websitebindungen konfigurieren, indem Sie das IIS-Snap-In der Microsoft Management Console (MMC) verwenden.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, überschreiben Assemblys anderer Konten im temporären Ordner.  
 Um sicherzustellen, dass Anwendungspools, die in verschiedenen Benutzerkontexten ausgeführt werden, Assemblys von anderen Konten im Ordner temporary ASP.NET Dateien nicht überschreiben können, verwenden Sie unterschiedliche Identitäten und temporäre Ordner für verschiedene Anwendungen. Wenn Sie beispielsweise zwei virtuelle Anwendungen /Application1 und /Application2 haben, können Sie zwei Anwendungspools (A und B) mit zwei unterschiedlichen Identitäten erstellen. Der Anwendungspool A kann unter einer Benutzeridentität ausgeführt werden (user1), während der Anwendungspool B unter einer anderen Benutzeridentität (user2) ausgeführt wird. Konfigurieren Sie /Application1 zur Verwendung von A und /Application2 zur Verwendung von B.  
  
 In Web.config können Sie den \< system.web/compilation/@tempFolder temporären Ordner mithilfe von> konfigurieren. Für /Application1 kann es sich um "c:-tempForUser1" und für Application2 um "c:-tempForUser2" erfreuen. Gewähren Sie den beiden Identitäten die entsprechende Schreibberechtigung für diese Ordner.  
  
 Dann kann user2 den Codegenerierungsordner für /application2 (unter c:\tempForUser1) nicht ändern.  
  
## <a name="enabling-asynchronous-processing"></a>Aktivieren der asynchronen Verarbeitung  
 Standardmäßig werden Nachrichten, die an einen WCF-Dienst gesendet werden, der unter IIS 6.0 und früher gehostet wird, synchron verarbeitet. ASP.NET ruft WCF in einem eigenen Thread auf (der ASP.NET Arbeitsthread), und WCF verwendet einen anderen Thread, um die Anforderung zu verarbeiten. WCF hält die Verbindung zum ASP.NET-Arbeitsthread aufrecht, bis die Verarbeitung abgeschlossen ist. Dies hat die synchrone Verarbeitung von Anforderungen zur Folge. Die asynchrone Verarbeitung von Anforderungen ermöglicht eine größere Skalierbarkeit, da die Anzahl der Threads reduziert wird, die zum Verarbeiten einer Anforderung erforderlich sind – WCF hält während der Verarbeitung der Anforderung nicht am ASP.NET Thread fest. Die Verwendung asynchronen Verhaltens wird für Computer, auf denen IIS 6.0 ausgeführt wird, nicht empfohlen, da es keine Möglichkeit gibt, eingehende Anforderungen zu drosseln, die den Server für DOS-Angriffe *(Denial Of Service)* öffnen. Ab IIS 7.0 wurde eine gleichzeitige Anforderungsdrosselung eingeführt: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Aufgrund dieser neuen Drosselung kann die asynchrone Verarbeitung nun gefahrlos eingesetzt werden.  In IIS 7.0 werden der asynchrone Handler und das Modul standardmäßig registriert. Wenn dies deaktiviert wurde, können Sie die asynchrone Verarbeitung von Anforderungen in der Datei Web.config der Anwendung manuell aktivieren. Die verwendeten Einstellungen richten sich nach Ihrer `aspNetCompatibilityEnabled`-Einstellung. Wenn `aspNetCompatibilityEnabled` auf `false` festgelegt ist, konfigurieren Sie `System.ServiceModel.Activation.ServiceHttpModule` wie im folgenden Konfigurationsausschnitt dargestellt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Service-Hosting-Beispiele](../samples/hosting.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
