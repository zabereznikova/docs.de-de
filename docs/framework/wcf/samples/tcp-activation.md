---
title: TCP-Aktivierung
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: 3627307c74604f30c77927067d302baf41b1c536
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tcp-activation"></a>TCP-Aktivierung
In diesem Beispiel wird das Hosten eines Diensts veranschaulicht, der Windows Process Activation Services (WAS) zum Aktivieren eines Diensts verwendet, der über das net.tcp-Protokoll kommuniziert. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`  
  
 Das Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer in einem von WAS aktivierten Arbeitsprozess gehosteten Dienstbibliothek (.dll). Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
 Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht, wie im folgenden Beispielcode dargestellt:  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück:  
  
```  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 Im Beispiel wird eine Variation der net.tcp-Bindung mit aktivierter TCP-Portfreigabe und deaktivierter Sicherheit verwendet. Wenn Sie eine gesicherte TCP-Bindung verwenden möchten, ändern Sie den Sicherheitsmodus des Servers in die gewünschte Einstellung, und führen Sie Svcutil.exe erneut auf dem Client aus, um eine aktualisierte Clientkonfigurationsdatei zu generieren.  
  
 Das folgende Beispiel zeigt den Konfigurationscode für den Dienst:  
  
```xml  
<system.serviceModel>  
  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->  
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexTcpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="PortSharingBinding" portSharingEnabled="true">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 Der Endpunkt des Clients wird wie im folgenden Beispielcode dargestellt konfiguriert:  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <netTcpBinding>  
          <binding name="NetTcpBinding_ICalculator">  
            <security mode="None"/>  
          </binding>  
        </netTcpBinding>  
    </bindings>  
    <client>  
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"  
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />  
    </client>  
</system.serviceModel>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass [!INCLUDE[iisver](../../../../includes/iisver-md.md)] installiert ist. [!INCLUDE[iisver](../../../../includes/iisver-md.md)] ist für die WAS-Aktivierung erforderlich.  
  
2.  Achten Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
     Außerdem müssen Sie die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Aktivierungskomponenten für andere Protokolle als HTTP installieren:  
  
    1.  Aus der **starten** Menü wählen **Systemsteuerung**.  
  
    2.  Wählen Sie **Programme und Funktionen**.  
  
    3.  Klicken Sie auf **aktivieren oder Deaktivieren von Windows-Komponenten**.  
  
    4.  Erweitern Sie die **Microsoft .NET Framework 3.0** Knoten, und überprüfen Sie die **Windows Communication Foundation-nicht-HTTP-Aktivierung** Funktion.  
  
3.  Konfigurieren Sie WAS für die Unterstützung der TCP-Aktivierung.  
  
     Zur Vereinfachung sind die folgenden beiden Schritte in der Batchdatei AddNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.  
  
    1.  Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden. Dies kann mit "Appcmd.exe" erfolgen. Diese Datei wird mit Internetinformationsdienste (IIS) 7.0 installiert. Führen Sie an einer Eingabeaufforderung auf Administratorebene den folgenden Befehl aus:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!TIP]
        >  Dieser Befehl ist eine einzelne Textzeile. Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Port 808 mit jedem beliebigen Hostnamen überwacht.  
  
    2.  Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren. Um net.tcp für die Anwendung /servicemodelsamples zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile. Dieser Befehl aktiviert die Anwendung/servicemodelsamples darauf zugegriffen werden beide http://localhost/servicemodelsamples und TCP://localhost//servicemodelsamples.  
  
4.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
5.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
     Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.  
  
     Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.  
  
    1.  Entfernen Sie net.tcp aus der Liste der aktivierten Protokolle, indem Sie den folgenden Befehl an einer Eingabeaufforderung auf Administratorebene ausführen:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl muss als eine Textzeile eingegeben werden.  
  
    2.  Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl an einer Eingabeaufforderung auf Administratorebene ausführen.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl muss als eine Textzeile eingegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
