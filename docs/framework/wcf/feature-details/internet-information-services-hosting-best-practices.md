---
title: Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: c875920ed70ea8bd35642d0b7725b2dfad08f2b1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558874"
---
# <a name="internet-information-services-hosting-best-practices"></a>Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten
In diesem Thema werden einige bewährte Methoden für das Hosting von Windows Communication Foundation (WCF)-Diensten beschrieben.  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementieren von WCF-Diensten als DLLs  
 Durch das Implementieren eines WCF-Diensts als DLL, die im Verzeichnis "\bin" einer Webanwendung bereitgestellt wird, können Sie den Dienst außerhalb des Webanwendungs Modells wieder verwenden, z. b. in einer Testumgebung, in der möglicherweise keine Internetinformationsdienste (IIS) bereitgestellt ist.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Diensthosts in IIS-gehosteten Anwendungen  
 Verwenden Sie nicht die imperativen Self-Host-APIs, um neue Dienst Hosts zu erstellen, die Netzwerk Transporte lauschen, die nicht nativ von der IIS-Hostingumgebung unterstützt werden (z. b. IIS 6,0 zum Hosten von TCP-Diensten, da die TCP-Kommunikation auf IIS 6,0 nicht nativ unterstützt Diese Vorgehensweise wird nicht empfohlen. Imperativ erstellte Diensthosts sind innerhalb der IIS-Hostumgebung nicht bekannt. Die Schwierigkeit liegt darin, dass Verarbeitungen, die von imperativ erstellten Diensten ausgeführt werden, von IIS bei der Ermittlung, ob der Hostanwendungspool im Leerlauf ist, nicht berücksichtigt werden. Das Ergebnis ist, dass Anwendungen, die über solche imperativ erstellten Diensthosts verfügen, sich in einer IIS-Hostumgebung befinden, die IIS-Hostprozesse aggressiv freigibt.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URIs und IIS-gehostete Endpunkte  
 Endpunkte für einen IIS-gehosteten Dienst sollten mit relativen URIs (Uniform Resource Identifier) statt mit absoluten Adressen konfiguriert werden. Dadurch wird sichergestellt, dass die Endpunktadresse innerhalb des Satzes von URI-Adressen liegt, die zur Hostanwendung gehören und dafür sorgen, dass die nachrichtenbasierte Aktivierung wie erwartet ausgeführt wird.  
  
## <a name="state-management-and-process-recycling"></a>Zustandsverwaltung und Prozesswiederverwendung  
 Die IIS-Hostumgebung ist für Dienste optimiert, die keinen lokalen Zustand im Arbeitsspeicher speichern. IIS verwendet den Hostprozess als Reaktion auf verschiedene externe und interne Ereignisse wieder, was dazu führt, dass Daten, die ausschließlich im Arbeitsspeicher im flüchtigen Zustand gespeichert werden, verloren gehen. In IIS gehostete Dienste sollten ihren Status prozessextern speichern (beispielsweise in einer Datenbank) oder in einem speicherinternen Cache, der einfach wiederhergestellt werden kann, wenn ein Wiederverwendungsereignis für eine Anwendung eintritt.  
  
> [!NOTE]
> Die Protokolle, die von WCF für die Zuverlässigkeit und Sicherheit der Nachrichten Ebene verwendet werden, nutzen den flüchtigen Speicher internen Status. Zuverlässige WCF-Sitzungen und-Sicherheits Sitzungen können aufgrund von Anwendungs Wiederverwendungen unerwartet beendet werden. IIS-gehostete Anwendungen, die diese Protokolle verwenden, sollten sich entweder von einem anderen als dem von WCF bereitgestellten Sitzungsschlüssel zum Korrelieren des Zustands der Anwendungsschicht (z. b. einem Anwendungsschicht Konstrukt oder einer benutzerdefinierten Korrelations Kopfzeile) oder der Deaktivierung der IIS-Prozess Wiederverwendung für die gehostete Anwendung unterscheidet.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Optimieren der Leistung in Szenarien der mittleren Ebene  
 Für eine optimale Leistung in einem *Szenario der mittleren Ebene*– ein Dienst, der andere Dienste als Reaktion auf eingehende Nachrichten aufruft – den WCF-Dienst Client einmal mit dem Remote Dienst instanziieren und ihn über mehrere eingehende Anforderungen hinweg wieder verwenden. Das Instanziieren von WCF-Dienst Clients ist ein aufwendiger Vorgang im Verhältnis zum Durchführen eines Dienst Aufrufens für eine bereits vorhandene Client Instanz, und Szenarien der mittleren Ebene führen zu unterschiedlichen Leistungssteigerungen, indem Remote Clients über Anforderungen hinweg zwischengespeichert werden. WCF-Dienst Clients sind Thread sicher, sodass der Zugriff auf einen Client nicht über mehrere Threads hinweg synchronisiert werden muss.  
  
 Szenarien der mittleren Ebene erzeugen außerdem Leistungssteigerungen durch Verwendung von asynchronen, von der `svcutil /a`-Option generierten APIs. Die- `/a` Option bewirkt, dass das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) `BeginXXX/EndXXX` Methoden für jeden Dienst Vorgang generiert, wodurch möglicherweise Aufrufe von Remote Diensten mit langer Ausführungszeit für Hintergrundthreads ausgeführt werden.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in Szenarien mit mehreren Adressen oder mehreren Namen  
 Sie können WCF-Dienste in einer IIS-Webfarm bereitstellen, in der eine Gruppe von Computern einen gemeinsamen externen Namen (z. b.) gemeinsam nutzen, `http://www.contoso.com` aber von anderen Hostnamen einzeln adressiert wird (z. b. `http://www.contoso.com` kann Datenverkehr an zwei verschiedene Computer mit dem Namen und weiterleiten `http://machine1.internal.contoso.com` `http://machine2.internal.contoso.com` ) Dieses Bereitstellungs Szenario wird von WCF vollständig unterstützt, erfordert jedoch eine spezielle Konfiguration der IIS-Website, auf der WCF-Dienste gehostet werden, um den korrekten (externen) Hostnamen in den Metadaten des Diensts (Web Services Description Language) anzuzeigen.  
  
 Um sicherzustellen, dass der richtige Hostname in den von WCF generierten Dienst Metadaten angezeigt wird, konfigurieren Sie die Standard Identität für die IIS-Website, die WCF-Dienste hostet, um einen expliziten Hostnamen zu verwenden. Beispielsweise sollten Computer, die sich in der `www.contoso.com` Farm befinden, eine IIS-Site Bindung von *: 80: www. Configuration. com für http und \* : 443: www. Configuration. com für HTTPS verwenden.  
  
 Sie können IIS-Websitebindungen konfigurieren, indem Sie das IIS-Snap-In der Microsoft Management Console (MMC) verwenden.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, überschreiben Assemblys anderer Konten im temporären Ordner.  
 Um sicherzustellen, dass Anwendungs Pools, die in unterschiedlichen Benutzer Kontexten ausgeführt werden, keine Assemblys anderer Konten im temporären Ordner ASP.NET Files überschreiben können, verwenden Sie unterschiedliche Identitäten und temporäre Ordner für verschiedene Anwendungen. Wenn Sie beispielsweise zwei virtuelle Anwendungen /Application1 und /Application2 haben, können Sie zwei Anwendungspools (A und B) mit zwei unterschiedlichen Identitäten erstellen. Der Anwendungspool A kann unter einer Benutzeridentität ausgeführt werden (user1), während der Anwendungspool B unter einer anderen Benutzeridentität (user2) ausgeführt wird. Konfigurieren Sie /Application1 zur Verwendung von A und /Application2 zur Verwendung von B.  
  
 In Web.config können Sie den temporären Ordner mit konfigurieren \<system.web/compilation/@tempFolder> . Für/application1 kann es "c:\tempForUser1" lauten, und für Taste zweiten Anwendung kann es "c:\tempForUser2" lauten. Gewähren Sie den beiden Identitäten die entsprechende Schreibberechtigung für diese Ordner.  
  
 Dann kann user2 den Codegenerierungsordner für /application2 (unter c:\tempForUser1) nicht ändern.  
  
## <a name="enabling-asynchronous-processing"></a>Aktivieren der asynchronen Verarbeitung  
 Standardmäßig werden Nachrichten, die an einen WCF-Dienst gesendet werden, der unter IIS 6,0 und früheren Versionen gehostet wird, synchron verarbeitet. ASP.NET ruft WCF in einem eigenen Thread (dem ASP.net-Arbeits Thread) auf, und WCF verwendet einen anderen Thread, um die Anforderung zu verarbeiten. WCF hält die Verbindung zum ASP.NET-Arbeitsthread aufrecht, bis die Verarbeitung abgeschlossen ist. Dies hat die synchrone Verarbeitung von Anforderungen zur Folge. Die asynchrone Verarbeitung von Anforderungen ermöglicht eine größere Skalierbarkeit, da dadurch die Anzahl der Threads reduziert wird, die für die Verarbeitung einer Anforderung erforderlich sind – WCF hält den ASP.net-Thread bei der Verarbeitung der Anforderung nicht an. Die Verwendung des asynchronen Verhaltens wird für Computer, auf denen IIS 6,0 ausgeführt wird, nicht empfohlen, da es keine Möglichkeit gibt, eingehende Anforderungen zu drosseln, die den Server zu *Denial-of-Service* -Angriffen (DOS) öffnen. Ab IIS 7,0 wurde eine Drosselung gleichzeitiger Anforderungen eingeführt: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu` . Aufgrund dieser neuen Drosselung kann die asynchrone Verarbeitung nun gefahrlos eingesetzt werden.  In IIS 7.0 werden der asynchrone Handler und das Modul standardmäßig registriert. Wenn dies deaktiviert wurde, können Sie die asynchrone Verarbeitung von Anforderungen in der Datei Web.config der Anwendung manuell aktivieren. Die verwendeten Einstellungen richten sich nach Ihrer `aspNetCompatibilityEnabled`-Einstellung. Wenn `aspNetCompatibilityEnabled` auf `false` festgelegt ist, konfigurieren Sie `System.ServiceModel.Activation.ServiceHttpModule` wie im folgenden Konfigurationsausschnitt dargestellt.  
  
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

- [Beispiele für Dienst Hosting](../samples/hosting.md)
- [Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))
