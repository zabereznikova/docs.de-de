---
title: "Empfohlene Vorgehensweisen f&#252;r das Hosten in Internetinformationsdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# Empfohlene Vorgehensweisen f&#252;r das Hosten in Internetinformationsdiensten
In diesem Thema werden einige empfohlene Vorgehensweisen für das Hosten von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Diensten beschrieben.  
  
## Implementieren von WCF\-Diensten als DLLs  
 Die Implementierung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts als DLL, die im \\bin\-Verzeichnis einer Webanwendung bereitgestellt wird, ermöglicht es Ihnen, den Dienst außerhalb des Webanwendungsmodells wiederzuverwenden, beispielsweise in einer Testumgebung, für die Internetinformationsdienste \(IIS\) möglicherweise nicht bereitgestellt wurden.  
  
## Diensthosts in IIS\-gehosteten Anwendungen  
 Verwenden Sie keine imperativen Selbsthosting\-APIs zur Erstellung neuer Diensthosts, die bei Netzwerktransporten lauschen, die nicht systemseitig von der IIS\-Hostumgebung unterstützt werden \(z. B. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] zum Hosten von TCP\-Diensten, da die TCP\-Kommunikation nicht systemseitig von [!INCLUDE[iis601](../../../../includes/iis601-md.md)] unterstützt wird\).Diese Vorgehensweise ist nicht empfehlenswert.Imperativ erstellte Diensthosts sind innerhalb der IIS\-Hostumgebung nicht bekannt.Die Schwierigkeit liegt darin, dass Verarbeitungen, die von imperativ erstellten Diensten ausgeführt werden, von IIS bei der Ermittlung, ob der Hostanwendungspool im Leerlauf ist, nicht berücksichtigt werden.Das Ergebnis ist, dass Anwendungen, die über solche imperativ erstellten Diensthosts verfügen, sich in einer IIS\-Hostumgebung befinden, die IIS\-Hostprozesse aggressiv freigibt.  
  
## URIs und IIS\-gehostete Endpunkte  
 Endpunkte für einen IIS\-gehosteten Dienst sollten mit relativen URIs \(Uniform Resource Identifier\) statt mit absoluten Adressen konfiguriert werden.Dadurch wird sichergestellt, dass die Endpunktadresse innerhalb des Satzes von URI\-Adressen liegt, die zur Hostanwendung gehören und dafür sorgen, dass die nachrichtenbasierte Aktivierung wie erwartet ausgeführt wird.  
  
## Zustandsverwaltung und Prozesswiederverwendung  
 Die IIS\-Hostumgebung ist für Dienste optimiert, die keinen lokalen Zustand im Arbeitsspeicher speichern.IIS verwendet den Hostprozess als Reaktion auf verschiedene externe und interne Ereignisse wieder, was dazu führt, dass Daten, die ausschließlich im Arbeitsspeicher im flüchtigen Zustand gespeichert werden, verloren gehen.In IIS gehostete Dienste sollten ihren Status prozessextern speichern \(beispielsweise in einer Datenbank\) oder in einem speicherinternen Cache, der einfach wiederhergestellt werden kann, wenn ein Wiederverwendungsereignis für eine Anwendung eintritt.  
  
> [!NOTE]
>  Die Protokolle, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] für die Zuverlässigkeit und Sicherheit der Nachrichtenschicht verwendet, nutzen den flüchtigen speicherinternen Status.Zuverlässige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzungen und \-Sicherheitssitzungen können unter Umständen aufgrund von Anwendungswiederverwendungen unerwartet beendet werden.In IIS gehostete Anwendungen, die diese Protokolle verwenden, sollten sich beim Korrelieren des Anwendungsschichtstatus entweder nach etwas anderem als dem von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Sitzungsschlüssel richten \(beispielsweise einem Anwendungsschichtkonstrukt oder einem benutzerdefinierten Korrelationsheader\) oder die Wiederverwendung von IIS\-Prozessen für die gehostete Anwendung deaktivieren.  
  
## Optimieren der Leistung in Szenarien der mittleren Ebene  
 Um optimale Leistung in einem *Szenario der mittleren Ebene* zu erreichen – einem Dienst, der als Reaktion auf eingehende Nachrichten andere Dienste aufruft –, instanziieren Sie den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstclient einmal für den Remotedienst, und verwenden Sie ihn dann in mehreren eingehenden Anforderungen wieder.Die Instanziierung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstclients ist ein kostspieliger Vorgang im Vergleich zum Tätigen eines Dienstaufrufs für eine bereits existierende Clientinstanz, und Szenarien der mittleren Ebene erbringen deutliche Leistungssteigerungen durch die anforderungsübergreifende Zwischenspeicherung von Remoteclients.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstclients sind threadsicher, weshalb der Zugriff auf einen Client nicht über mehrere Threads hinweg synchronisiert werden muss.  
  
 Szenarien der mittleren Ebene erzeugen außerdem Leistungssteigerungen durch Verwendung von asynchronen, von der `svcutil /a`\-Option generierten APIs.Die `/a`\-Option führt dazu, dass das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)`BeginXXX/EndXXX`\-Methoden für jeden Dienstvorgang generiert. Dadurch wird es ermöglicht, potenziell zeitintensive Aufrufe von Remotediensten in Hintergrundthreads durchzuführen.  
  
## WCF in Szenarien mit mehreren Adressen oder mehreren Namen  
 Sie können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste innerhalb einer IIS\-Webfarm bereitstellen, in der ein Satz Computer einen gemeinsamen externen Namen hat \(z. B. http:\/\/www.contoso.com\), jedoch einzeln über einen individuellen Hostnamen adressiert wird \(z. B. könnte http:\/\/www.contoso.com Datenverkehr an zwei verschiedene Computer mit den Namen http:\/\/machine1.internal.contoso.com und http:\/\/machine2.internal.contoso.com leiten\).Dieses Bereitstellungsszenario wird vollständig von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt. Jedoch muss die IIS\-Website, die die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste hostet, speziell konfiguriert werden, damit der richtige \(externe\) Hostname in den Metadaten des Diensts angezeigt wird \(Web Services Description Language\).  
  
 Um sicherzustellen, dass der richtige Hostname in den von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generierten Metadaten des Diensts angezeigt wird, konfigurieren Sie die Standardidentität für die IIS\-Website, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste hostet, zur Verwendung eines expliziten Hostnamens.Beispiel: Computer, die sich innerhalb der Webfarm www.contoso.com befinden, sollten die IIS\-Sitebindung \*:80:www.contoso.com für HTTP und \*:443:www.contoso.com für HTTPS verwenden.  
  
 Sie können IIS\-Websitebindungen konfigurieren, indem Sie das IIS\-Snap\-In der Microsoft Management Console \(MMC\) verwenden.  
  
## Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, überschreiben Assemblys anderer Konten im temporären Ordner.  
 Um sicherzustellen, dass Anwendungspools, die in unterschiedlichen Benutzerkontexten ausgeführt werden, keine Assemblys anderer Konten im temporären [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Dateiordner überschreiben können, verwenden Sie unterschiedliche Identitäten und unterschiedliche Ordner für unterschiedliche Anwendungen.Wenn Sie beispielsweise zwei virtuelle Anwendungen \/Application1 und \/Application2 haben, können Sie zwei Anwendungspools \(A und B\) mit zwei unterschiedlichen Identitäten erstellen.Der Anwendungspool A kann unter einer Benutzeridentität ausgeführt werden \(user1\), während der Anwendungspool B unter einer anderen Benutzeridentität \(user2\) ausgeführt wird. Konfigurieren Sie \/Application1 zur Verwendung von A und \/Application2 zur Verwendung von B.  
  
 In Web.config können Sie den temporären Ordner mit \<system.web\/compilation\/@tempFolder\> konfigurieren.Für \/Application1 kann es "c:\\tempForUser1" sein, und für \/Application2 kann es "c:\\tempForUser2" sein.Gewähren Sie den beiden Identitäten die entsprechende Schreibberechtigung für diese Ordner.  
  
 Dann kann user2 den Codegenerierungsordner für \/application2 \(unter c:\\tempForUser1\) nicht ändern.  
  
## Aktivieren der asynchronen Verarbeitung  
 Standardmäßig werden Nachrichten, die an einen von IIS 6.0 und früher gehosteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst gesendet werden, synchron verarbeitet.ASP.NET ruft in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] seinen eigenen Thread \(der ASP.NET\-Arbeitsthread\) auf, und von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird zum Verarbeiten der Anforderung ein anderer Thread verwendet.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hält die Verbindung zum ASP.NET\-Arbeitsthread aufrecht, bis die Verarbeitung abgeschlossen ist.Dies hat die synchrone Verarbeitung von Anforderungen zur Folge.Die asynchrone Verarbeitung von Anforderungen schafft größere Skalierbarkeit, da so die Anzahl der zur Verarbeitung einer Anforderung erforderlichen Threads reduziert wird. Während der Verarbeitung der Anforderung wird von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Verbindung zum ASP.NET\-Thread nicht aufrecht erhalten.Die Verwendung asynchronen Verhaltens wird für Computer mit IIS 6.0 nicht empfohlen, da so eingehende Anforderungen, durch die der Server *Denial Of Service* \(DOS\)\-Attacken ausgesetzt ist, nicht gedrosselt werden können.Ab IIS 7.0 steht eine parallele Abfragedrosselung zur Verfügung: `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]“MaxConcurrentRequestsPerCpu`.Aufgrund dieser neuen Drosselung kann die asynchrone Verarbeitung nun gefahrlos eingesetzt werden.In IIS 7.0 werden der asynchrone Handler und das Modul standardmäßig registriert.Wenn dies deaktiviert wurde, können Sie die asynchrone Verarbeitung von Anforderungen in der Datei Web.config der Anwendung manuell aktivieren.Die verwendeten Einstellungen richten sich nach Ihrer `aspNetCompatibilityEnabled`\-Einstellung.Wenn `aspNetCompatibilityEnabled` auf `false` festgelegt ist, konfigurieren Sie <xref:System.ServiceModel.Activation.ServiceHttpModule> wie im folgenden Konfigurationsausschnitt dargestellt.  
  
```  
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
  
 Wenn `aspNetCompatibilityEnabled` auf `true` festgelegt ist, konfigurieren Sie <xref:System.ServiceModel.Activation.ServiceHttpHandlerFactory> wie im folgenden Konfigurationsausschnitt dargestellt.  
  
```  
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
  
## Siehe auch  
 [Service Hosting Samples](http://msdn.microsoft.com/de-de/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)   
 [Windows Server AppFabric\-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)