---
title: Routen nach Text
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: c3f4b19e646a6a9716d2264a3969b339208c60a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144187"
---
# <a name="route-by-body"></a>Routen nach Text
In diesem Beispiel wird das Implementieren eines Diensts veranschaulicht, der Nachrichtenobjekte mit einer beliebigen SOAP-Aktion annimmt. Dieses Beispiel basiert auf dem [Ersten Schritte,](../../../../docs/framework/wcf/samples/getting-started-sample.md) der einen Rechnerdienst implementiert. Der Dienst implementiert einen einzelnen `Calculate`-Vorgang, der einen <xref:System.ServiceModel.Channels.Message>-Anforderungsparameter annimmt und eine <xref:System.ServiceModel.Channels.Message>-Antwort zurückgibt.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird in IIS gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im Beispiel wird das Senden von Nachrichten auf Grundlage des Textinhalts veranschaulicht. Der integrierte Windows Communication Foundation (WCF)-Dienstmodell-Nachrichtendispatchmechanismus basiert auf Nachrichtenaktionen. Es gibt jedoch viele vorhandene Webdienste, die alle Vorgänge mit Action="" definieren. Es ist nicht möglich, einen Dienst auf Grundlage von WSDL zu erstellen, der weiter Anforderungsnachrichten auf Grundlage von Action-Informationen sendet. In diesem Beispiel wird ein Dienstvertrag veranschaulicht, der auf WSDL basiert (WSDL in der im Beispiel eingeschlossenen Datei Service.wsdl). Der Servicevertrag ist Rechner, ähnlich dem, der in [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md)verwendet wird. `[OperationContract]` gibt jedoch `Action=""` für alle Vorgänge an.  
  
```csharp  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 Wenn ein Vertrag vorliegt, erfordert ein Dienst das benutzerdefinierte Sendeverhalten `DispatchByBodyBehavior`, damit die Nachrichten zwischen Vorgängen gesendet werden können. Dieses Dispatch-Verhalten initialisiert den `DispatchByBodyElementOperationSelector` benutzerdefinierten Vorgangsselektor mit einer Tabelle der Vorgangsnamen, die durch QName der jeweiligen Wrapperelemente bezeichnet werden. `DispatchByBodyElementOperationSelector` prüft das Starttag des ersten untergeordneten Elements von Body und wählt den Vorgang anhand der zuvor erwähnten Tabelle aus.  
  
 Der Client verwendet einen automatisch aus der WSDL generierten Proxy, der vom Dienst mithilfe des [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)exportiert wird.  
  
```console  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 Dass die Aktionen aller Vorgänge leer sind, hat keine Auswirkungen auf den Clientcode, mit Ausnahme der Action-Parameter im automatisch generierten Proxy.  
  
 Der Clientcode führt mehrere Berechnungen aus. Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die Lösung zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
