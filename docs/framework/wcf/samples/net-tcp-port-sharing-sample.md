---
title: Beispiel zur Net.TCP-Portfreigabe
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: e7a814dcdc027980f70ec90e384f3ec2f74b364d
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714705"
---
# <a name="nettcp-port-sharing-sample"></a>Beispiel zur Net.TCP-Portfreigabe
Im TCP/IP-Protokoll wird mithilfe einer 16-stelligen Zahl (als Port bezeichnet) zwischen Verbindungen mit mehreren Netzwerkanwendungen unterschieden, die auf demselben Computer ausgeführt werden. Wenn eine Anwendung einen Port überwacht, wird der gesamte TCP-Verkehr für diesen Port an die entsprechende Anwendung geleitet. Andere Anwendungen können nicht gleichzeitig an diesem Port lauschen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 Viele Protokolle verwenden eine Standardportnummer. Das HTTP-Protokoll verwendet beispielsweise in der Regel TCP-Port 80. Internetinformationsdienste (IIS) verfügen über einen Listener, damit mehrere HTTP-Anwendungen gemeinsam einen Port verwenden können. IIS überwacht den Port direkt und leitet Nachrichten an die entsprechende Anwendung weiter. Dies erfolgt auf Grundlage von Informationen im Nachrichtenstream. So können mehrere HTTP-Anwendungen die gleiche Portnummer verwenden, ohne um das Reservieren des Ports für den Nachrichteneingang konkurrieren zu müssen.  
  
 Bei der NetTcp-Port Freigabe handelt es sich um ein Windows Communication Foundation (WCF)-Feature, mit dem mehrere Netzwerkanwendungen einen einzelnen Port gemeinsam nutzen können. Der NetTcp-Portfreigabedienst nimmt Verbindungen mithilfe des net.tcp-Protokolls an und leitet Nachrichten auf Grundlage ihrer Zieladresse weiter.  
  
 Der NetTcp-Portfreigabedienst ist standardmäßig nicht aktiviert. Vor dem Ausführen dieses Beispiels müssen Sie den Dienst manuell aktivieren. Weitere Informationen finden Sie unter Gewusst [wie: Aktivieren des net. TCP-Port Freigabe Dienstanbieter](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md). Wenn der Dienst deaktiviert ist, wird beim Starten der Serveranwendung eine Ausnahme ausgelöst.  
  
```console
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 Die Portfreigabe wird auf dem Server aktiviert, indem die <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>-Eigenschaft der <xref:System.ServiceModel.NetTcpBinding>-Bindung oder des <xref:System.ServiceModel.Channels.TcpTransportBindingElement>-Bindungselements festgelegt wird. Der Client muss nicht wissen, wie die Portfreigabe konfiguriert wurde, um sie auf dem Server zu verwenden.  
  
## <a name="enabling-port-sharing"></a>Aktivieren der Portfreigabe  
 Im folgenden Code wird das Aktivieren der Portfreigabe auf dem Server veranschaulicht. Es wird eine Instanz des `ICalculator`-Diensts auf einem festen Port mit einem zufälligen URI-Pfad gestartet. Zwei Dienste können zwar denselben Port verwenden, ihre allgemeinen Endpunktadressen müssen jedoch eindeutig sein, damit der NetTcp-Portfreigabedienst Nachrichten an die richtige Anwendung weiterleiten kann.  

```csharp
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address = $"net.tcp://localhost:9000/calculator/{salt}";
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```

 Wenn die Portfreigabe aktiviert ist, können Sie den Dienst mehrmals ausführen, ohne dass es zu einem Konflikt aufgrund der Portnummer kommt. Wenn Sie den Code ändern, um die Portfreigabe zu deaktivieren, führt das Starten zweier Kopien des Diensts bei der zweiten Kopie zu einem Fehler mit einer <xref:System.ServiceModel.AddressAlreadyInUseException>.  
  
```console  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  
 Sie können mithilfe des Testclients überprüfen, ob Nachrichten richtig an die Dienste weitergeleitet werden, die den Port gemeinsam verwenden.  

```csharp
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = $"net.tcp://localhost:9000/calculator/{salt}";
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```

 Jede Instanz des Diensts gibt ihre eindeutige Nummer und Adresse aus. Wenn Sie service.exe ausführen, kann beispielsweise der folgende Text angezeigt werden:  
  
```console  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 Geben Sie beim Ausführen von client.exe die hier angegebene Dienstnummer ein.  
  
```console  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 Dieses Beispiel kann in einer Konfiguration mit mehreren Computern ausgeführt werden, indem Sie die vom Client verwendete generierte Adresse ändern. Ändern Sie in Client.cs die Formatzeichenfolge für die Endpunktadresse, sodass sie mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf "localhost" durch die IP-Adresse des Servercomputers. Sie müssen das Beispiel neu kompilieren, nachdem Sie diese Änderung vorgenommen haben.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
3. Aktivieren Sie den NetTcp-Portfreigabedienst wie im Einführungsabschnitt oben beschrieben.  
  
4. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
5. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md). Detaillierte Informationen zum Ausführen finden Sie oben im Abschnitt zum Ausführen des Beispiels.  
