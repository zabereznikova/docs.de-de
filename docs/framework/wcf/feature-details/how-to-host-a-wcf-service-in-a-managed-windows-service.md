---
title: "Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst
In diesem Thema werden die grundlegenden Schritte vorgestellt, die für die Erstellung eines durch einen Windows\-Dienst gehosteten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Diensts erforderlich sind.Das Szenario wird durch die Hostingoption des verwalteten Windows\-Diensts ermöglicht. Die Option ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst mit langer Laufzeit, der außerhalb der Internetinformationsdienste \(IIS\) in einer sicheren, nicht nachrichtenaktivierten Umgebung gehostet wird.Die Lebensdauer des Diensts wird stattdessen vom Betriebssystem gesteuert.Diese Hostingoption ist in allen Windows\-Versionen verfügbar.  
  
 Windows\-Dienste können mit Microsoft.ManagementConsole.SnapIn in Microsoft Management Console \(MMC\) verwaltet und so konfiguriert werden, dass sie beim Systemstart automatisch gestartet werden.Diese Hostingoption registriert die Anwendungsdomäne \(AppDomain\), die einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst als verwalteten Windows\-Dienst hostet, sodass die Prozesslebensdauer des Diensts von den Diensten des Dienststeuerungs\-Managers für Windows gesteuert wird.  
  
 Der Dienstcode enthält eine Dienstimplementierung des Dienstvertrags, eine Windows\-Dienstklasse und eine Installerklasse.Die Dienstimplementierungsklasse, `CalculatorService`, ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst.`CalculatorWindowsService` ist ein Windows\-Dienst.Damit sich die Klasse als Windows\-Dienst eignet, erbt sie von `ServiceBase` und implementiert die `OnStart`\-Methode und die `OnStop`\-Methode.In `OnStart` wird <xref:System.ServiceModel.ServiceHost> für den `CalculatorService`\-Typ erstellt und geöffnet.In `OnStop` wird der Dienst beendet und verworfen.Der Host ist außerdem für die Bereitstellung einer Basisadresse für den Diensthost verantwortlich, die in den Anwendungseinstellungen konfiguriert wurde.Durch die Installerklasse, die von <xref:System.Configuration.Install.Installer> erbt, kann das Programm mit dem Tool "Installutil.exe" als Windows\-Dienst installiert werden.  
  
### Erstellen des Diensts und Bereitstellen des Hostcodes  
  
1.  Erstellen Sie ein neues Visual Studio\-Konsolenanwendungsprojekt namens "Service".  
  
2.  Benennen Sie "Program.cs" in "Service.cs" um.  
  
3.  Ändern Sie den Namespace in "Microsoft.ServiceModel.Samples".  
  
4.  Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceProcess.dll  
  
    -   System.Configuration.Install.dll  
  
5.  Fügen Sie der Datei "Service.cs" die folgenden using\-Anweisungen hinzu.  
  
     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]  
  
6.  Definieren Sie den `ICalculator`\-Dienstvertrag, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]  
  
7.  Implementieren Sie den Dienstvertrag in einer Klasse namens `CalculatorService`, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]  
  
8.  Erstellen Sie eine neue Klasse namens `CalculatorWindowsService`, die von der <xref:System.ServiceProcess.ServiceBase>\-Klasse erbt.Fügen Sie eine lokale Variable namens `serviceHost` hinzu, die auf die <xref:System.ServiceModel.ServiceHost>\-Instanz verweist.Definieren Sie die `Main`\-Methode, die `ServiceBase.Run(new CalculatorWindowsService)` aufruft.  
  
     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]  
  
9. Überschreiben Sie die [OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>\-Methode, indem Sie eine neue <xref:System.ServiceModel.ServiceHost>\-Instanz erstellen und öffnen, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]  
  
10. Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>\-Methode, indem Sie <xref:System.ServiceModel.ServiceHost> schließen, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]  
  
11. Erstellen Sie eine neue Klasse namens `ProjectInstaller`, die von <xref:System.Configuration.Install.Installer> erbt und die mit dem auf `true` festgelegten <xref:System.ComponentModel.RunInstallerAttribute> gekennzeichnet ist.Dies ermöglicht die Installation des Tools "Installutil.exe" durch den Windows\-Dienst.  
  
     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]  
  
12. Entfernen Sie die `Service`\-Klasse, die beim Erstellen des Projekts generiert wurde.  
  
13. Fügen Sie dem Projekt eine Anwendungskonfigurationsdatei hinzu.Ersetzen Sie den Inhalt der Datei durch das folgende Konfigurations\-XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>    <services>  
          <!-- This section is optional with the new configuration model  
               introduced in .NET Framework 4. -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                   behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceMetadata httpGetEnabled="true"/>  
              <serviceDebug includeExceptionDetailInFaults="False"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die App.config\-Datei, und wählen Sie **Eigenschaften** aus.Wählen Sie unter **In Ausgabeverzeichnis kopieren** die Option **Kopieren, wenn neuer** aus.  
  
     In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben.Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt.Da in diesem Beispiel das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> des Diensts auf `true` festgelegt ist, ist für den Dienst auch die Veröffentlichung von Metadaten aktiviert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
### Installieren Sie den Dienst, und führen Sie ihn aus.  
  
1.  Erstellen Sie die Projektmappe, um `Service.exe` zu erstellen.  
  
2.  Öffnen Sie das [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Eingabeaufforderungsfenster, und navigieren Sie zum Projektverzeichnis.Geben Sie an der Eingabeaufforderung `installutil bin\service.exe` ein, um den Windows\-Dienst zu installieren.  
  
    > [!NOTE]
    >  Wenn Sie die [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Eingabeaufforderung nicht verwenden, stellen Sie sicher, dass sich das `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>`\-Verzeichnis im Systempfad befindet.  
  
     Geben Sie an der Eingabeaufforderung `services.msc` ein, um auf den Dienststeuerungs\-Manager \(SCM\) zuzugreifen.Der Windows\-Dienst müsste unter "Dienste" als "WCFWindowsServiceSample" angezeigt werden.Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst kann Clients nur dann antworten, wenn der Windows\-Dienst ausgeführt wird.Um den Dienst zu starten, klicken Sie mit der rechten Maustaste in den Dienststeuerungs\-Manager, und wählen Sie "Starten" aus, oder geben Sie an der Eingabeaufforderung **net start WCFWindowsServiceSample** ein.  
  
3.  Wenn Sie Änderungen am Dienst vornehmen, müssen Sie ihn zuerst stoppen und dann deinstallieren.Um den Dienst zu stoppen, klicken Sie mit der rechten Maustaste auf den Dienst im Dienststeuerungs\-Manager, und wählen Sie "Beenden" aus, oder geben Sie an der Eingabeaufforderung **type net stop WCFWindowsServiceSample** ein.Wenn Sie den Windows\-Dienst beenden und anschließend einen Client ausführen, tritt eine Ausnahme vom Typ <xref:System.ServiceModel.EndpointNotFoundException> auf, wenn ein Client versucht, auf den Dienst zuzugreifen.Um den Windows\-Dienst zu deinstallieren, geben Sie an der Eingabeaufforderung **installutil \/u bin\\service.exe** ein.  
  
## Beispiel  
 In Folgenden finden Sie eine vollständige Liste des in diesem Thema verwendeten Codes:  
  
 [!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
 [!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]  
  
 Wie bei der Option für das "Selbsthosting" muss auch bei der Hostumgebung des Windows\-Diensts ein Teil des Hostcodes eine Komponente der Anwendung sein.Der Dienst wird als eine Konsolenanwendung implementiert und enthält seinen eigenen Hostingcode.In anderen Hostumgebungen, z. B. WAS \(Windows Process Activation Service, Windows\-Prozessaktivierungsdienst\) in IIS \(Internet Information Services, Internetinformationsdienste\), müssen Entwickler keinen Hostcode schreiben.  
  
## Siehe auch  
 [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)   
 [Hosten in einer verwalteten Anwendung](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)   
 [Hosting\-Dienste](../../../../docs/framework/wcf/hosting-services.md)   
 [Windows Server AppFabric\-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)