---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst'
description: Erfahren Sie, wie Sie einen WCF-Dienst erstellen, der von einem Windows-Dienst gehostet wird. Diese Hostingoption ist in allen Windows-Versionen verfügbar.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 4e07aa7aac82fae5cfd1bfc759ef724cf87a873a
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246935"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst

In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um einen von einem Windows-Dienst gehosteten Windows Communication Foundation (WCF)-Dienst zu erstellen. Das Szenario wird durch die Hostingoption des verwalteten Windows-Diensts aktiviert, bei der es sich um einen WCF-Dienst mit langer Ausführungszeit handelt, der außerhalb von Internetinformationsdienste (IIS) in einer sicheren Umgebung gehostet wird, die nicht Die Lebensdauer des Diensts wird stattdessen vom Betriebssystem gesteuert. Diese Hostingoption ist in allen Windows-Versionen verfügbar.

Windows-Dienste können mit Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) verwaltet und so konfiguriert werden, dass sie beim Systemstart automatisch gestartet werden. Diese Hostingoption besteht darin, die Anwendungsdomäne (AppDomain), die einen WCF-Dienst hostet, als verwalteten Windows-Dienst zu registrieren, sodass die Prozess Lebensdauer des Diensts vom Dienststeuerungs-Manager (SCM) für Windows-Dienste gesteuert wird.

Der Dienstcode enthält eine Dienstimplementierung des Dienstvertrags, eine Windows-Dienstklasse und eine Installerklasse. Die Dienst Implementierungs Klasse, `CalculatorService` , ist ein WCF-Dienst. `CalculatorWindowsService` ist ein Windows-Dienst. Damit sich die Klasse als Windows-Dienst eignet, erbt sie von `ServiceBase` und implementiert die `OnStart`-Methode und die `OnStop`-Methode. In `OnStart` wird <xref:System.ServiceModel.ServiceHost> für den `CalculatorService`-Typ erstellt und geöffnet. In `OnStop` wird der Dienst beendet und verworfen. Der Host ist außerdem für die Bereitstellung einer Basisadresse für den Diensthost verantwortlich, die in den Anwendungseinstellungen konfiguriert wurde. Durch die Installerklasse, die von <xref:System.Configuration.Install.Installer> erbt, kann das Programm mit dem Tool "Installutil.exe" als Windows-Dienst installiert werden.

## <a name="construct-the-service-and-provide-the-hosting-code"></a>Erstellen des Diensts und Bereitstellen des Hostcodes

1. Erstellen Sie ein neues Visual Studio- **Konsolen-App** -Projekt namens **Service**.

2. Benennen Sie "Program.cs" in "Service.cs" um.

3. Ändern Sie den-Namespace in `Microsoft.ServiceModel.Samples` .

4. Fügen Sie Verweise auf die folgenden Assemblys hinzu:

    - System.ServiceModel.dll

    - System.ServiceProcess.dll

    - System.Configuration.Install.dll

5. Fügen Sie der Datei "Service.cs" die folgenden using-Anweisungen hinzu.

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. Definieren Sie den `ICalculator`-Dienstvertrag, wie im folgenden Code gezeigt.

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. Implementieren Sie den Dienstvertrag in einer Klasse namens `CalculatorService`, wie im folgenden Code gezeigt.

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. Erstellen Sie eine neue Klasse namens `CalculatorWindowsService`, die von der <xref:System.ServiceProcess.ServiceBase>-Klasse erbt. Fügen Sie eine lokale Variable namens `serviceHost` hinzu, die auf die <xref:System.ServiceModel.ServiceHost>-Instanz verweist. Definieren Sie die `Main`-Methode, die `ServiceBase.Run(new CalculatorWindowsService)` aufruft.

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>-Methode, indem Sie eine neue <xref:System.ServiceModel.ServiceHost>-Instanz erstellen und öffnen, wie im folgenden Code gezeigt.

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. Überschreiben Sie die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Methode, indem Sie <xref:System.ServiceModel.ServiceHost> schließen, wie im folgenden Code gezeigt.

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. Erstellen Sie eine neue Klasse namens `ProjectInstaller`, die von <xref:System.Configuration.Install.Installer> erbt und die mit dem auf <xref:System.ComponentModel.RunInstallerAttribute> festgelegten `true` gekennzeichnet ist. Dies ermöglicht die Installation des Tools "Installutil.exe" durch den Windows-Dienst.

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. Entfernen Sie die `Service`-Klasse, die beim Erstellen des Projekts generiert wurde.

13. Fügen Sie dem Projekt eine Anwendungskonfigurationsdatei hinzu. Ersetzen Sie den Inhalt der Datei durch das folgende Konfigurations-XML.

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

     Klicken Sie mit der rechten Maustaste auf die Datei App.config im **Projektmappen-Explorer** und wählen Sie **Eigenschaften**aus. Wählen Sie unter **in Ausgabeverzeichnis kopieren die** Option **kopieren, wenn neuer**aus.

     In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben. Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt. Da in diesem Beispiel das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> des Diensts auf `true` festgelegt ist, ist für den Dienst auch die Veröffentlichung von Metadaten aktiviert. Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../samples/simplified-configuration-for-wcf-services.md).

## <a name="install-and-run-the-service"></a>Installieren Sie den Dienst, und führen Sie ihn aus.

1. Erstellen Sie die Projektmappe, um `Service.exe` zu erstellen.

2. Öffnen Sie Developer-Eingabeaufforderung für Visual Studio, und navigieren Sie zum Projektverzeichnis. Geben Sie an der Eingabeaufforderung `installutil bin\service.exe` ein, um den Windows-Dienst zu installieren.

     Geben Sie an der Eingabeaufforderung `services.msc` ein, um auf den Dienststeuerungs-Manager (SCM) zuzugreifen. Der Windows-Dienst müsste unter "Dienste" als "WCFWindowsServiceSample" angezeigt werden. Der WCF-Dienst kann nur auf Clients antworten, wenn der Windows-Dienst ausgeführt wird. Um den Dienst zu starten, klicken Sie im SCM mit der rechten Maustaste darauf, und wählen Sie "Start", oder geben Sie an der Eingabeaufforderung **net Start wcfwindowsservicesample** ein.

3. Wenn Sie Änderungen am Dienst vornehmen, müssen Sie ihn zuerst stoppen und dann deinstallieren. Um den Dienst zu unterbinden, klicken Sie im SCM mit der rechten Maustaste auf den Dienst, und wählen Sie "Abbrechen" aus, oder geben Sie an der Eingabeaufforderung **net stoppwcfwindowsservicesample** ein. Wenn Sie den Windows-Dienst beenden und anschließend einen Client ausführen, tritt eine Ausnahme vom Typ <xref:System.ServiceModel.EndpointNotFoundException> auf, wenn ein Client versucht, auf den Dienst zuzugreifen. Um den Windows-Diensttyp " **installutil/u bin\service.exe** an der Eingabeaufforderung zu deinstallieren.

## <a name="example"></a>Beispiel

Im folgenden finden Sie eine komplette Liste des in diesem Thema verwendeten Codes:

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

Wie bei der Option für das "Selbsthosting" muss auch bei der Hostumgebung des Windows-Diensts ein Teil des Hostcodes eine Komponente der Anwendung sein. Der Dienst wird als eine Konsolenanwendung implementiert und enthält seinen eigenen Hostingcode. In anderen Hostumgebungen, z. B. WAS (Windows Process Activation Service, Windows-Prozessaktivierungsdienst) in IIS (Internet Information Services, Internetinformationsdienste), müssen Entwickler keinen Hostcode schreiben.

## <a name="see-also"></a>Weitere Informationen

- [Vereinfachte Konfiguration](../simplified-configuration.md)
- [Hosten in einer verwalteten Anwendung](hosting-in-a-managed-application.md)
- [Hosting-Dienste](../hosting-services.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
