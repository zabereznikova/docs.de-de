---
title: Duplex
ms.date: 03/30/2017
helpviewer_keywords:
- Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
ms.openlocfilehash: 54b941541ae0da4900608e61f08f4ed99c9ea472
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804119"
---
# <a name="duplex"></a>Duplex
Im Duplexbeispiel wird das Definieren und Implementieren eines Duplexvertrags veranschaulicht. Duplexkommunikation findet statt, wenn ein Client eine Sitzung mit einem Dienst einrichtet und dem Dienst einen Kanal bereitstellt, über den der Dienst Nachrichten zurück an den Client senden kann. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md). Ein Duplexvertrag wird als Paar von Schnittstellen definiert: eine primäre Schnittstelle vom Client zum Dienst und eine Rückrufschnittstelle vom Dienst zum Client. In diesem Beispiel kann der Client durch die `ICalculatorDuplex`-Schnittstelle mathematische Operationen ausführen (Berechnen eines Ergebnisses über eine Sitzung). Der Dienst gibt Ergebnisse auf der `ICalculatorDuplexCallback`-Schnittstelle zurück. Ein Duplexvertrag erfordert eine Sitzung, da ein Kontext eingerichtet werden muss, um die zwischen dem Client und dem Dienst gesendeten Nachrichten in Beziehung zu setzen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet. Der Duplexvertrag wird wie folgt definiert:  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,  
                 CallbackContract=typeof(ICalculatorDuplexCallback))]  
public interface ICalculatorDuplex  
{  
    [OperationContract(IsOneWay = true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
}  
  
public interface ICalculatorDuplexCallback  
{  
    [OperationContract(IsOneWay = true)]  
    void Result(double result);  
    [OperationContract(IsOneWay = true)]  
    void Equation(string eqn);  
}  
```  
  
 Die `CalculatorService`-Klasse implementiert die primäre `ICalculatorDuplex`-Schnittstelle. Der Dienst verwendet den <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanzmodus, um die Ergebnisse für die einzelnen Sitzungen zu pflegen. Die private `Callback`-Eigenschaft wird zum Zugriff auf den Rückrufkanal zum Client verwendet. Der Dienst verwendet den Rückruf, um über die Rückrufschnittstelle Nachrichten zurück an den Client zu senden.  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorDuplex  
{  
    double result = 0.0D;  
    string equation;  
  
    public CalculatorService()  
    {  
        equation = result.ToString();  
    }  
  
    public void Clear()  
    {  
        Callback.Equation(equation + " = " + result.ToString());  
        equation = result.ToString();  
    }  
  
    public void AddTo(double n)  
    {  
        result += n;  
        equation += " + " + n.ToString();  
        Callback.Result(result);  
    }  
    ...  
    ICalculatorDuplexCallback Callback  
    {  
        get  
        {  
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();  
        }  
    }  
}  
```  
  
 Damit Nachrichten vom Dienst empfangen werden können, muss der Client eine Klasse bereitstellen, die die Rückrufschnittstelle des Duplexvertrags implementiert. Im Beispiel wird eine `CallbackHandler`-Klasse definiert, um die `ICalculatorDuplexCallback`-Schnittstelle zu implementieren.  
  
```  
public class CallbackHandler : ICalculatorDuplexCallback  
{  
   public void Result(double result)  
   {  
      Console.WriteLine("Result({0})", result);  
   }  
  
   public void Equation(string equation)  
   {  
      Console.WriteLine("Equation({0}", equation);  
   }  
}  
```  
  
 Für den für einen Duplexvertrag erzeugten Proxy muss ein <xref:System.ServiceModel.InstanceContext> bei der Erstellung bereitgestellt werden. Dieser <xref:System.ServiceModel.InstanceContext> wird als Standort für ein Objekt verwendet, das die Rückrufschnittstelle implementiert und die vom Dienst zurückgesendeten Nachrichten verarbeitet. Ein <xref:System.ServiceModel.InstanceContext> wird mit einer Instanz der `CallbackHandler`-Klasse erstellt. Dieses Objekt verarbeitet die vom Dienst über die Rückrufschnittstelle an den Client gesendeten Nachrichten.  
  
```  
// Construct InstanceContext to handle messages on callback interface.  
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());  
  
// Create a client.  
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);  
  
Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");  
Console.WriteLine();  
  
// Call the AddTo service operation.  
double value = 100.00D;  
client.AddTo(value);  
  
// Call the SubtractFrom service operation.  
value = 50.00D;  
client.SubtractFrom(value);  
  
// Call the MultiplyBy service operation.  
value = 17.65D;  
client.MultiplyBy(value);  
  
// Call the DivideBy service operation.  
value = 2.00D;  
client.DivideBy(value);  
  
// Complete equation.  
client.Clear();  
  
Console.ReadLine();  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 Die Konfiguration muss so geändert werden, dass eine Bindung bereitgestellt wird, die sowohl eine Sitzungskommunikation als auch eine Duplexkommunikation unterstützt. `wsDualHttpBinding` unterstützt die sitzungsbasierte Kommunikation und ermöglicht durch Bereitstellung dualer HTTP-Verbindungen (eine Verbindung pro Richtung) auch eine Duplexkommunikation. Auf dem Dienst ist der einzige Unterschied in der Konfiguration die verwendete Bindung. Auf dem Client muss, wie in der folgenden Beispielkonfiguration dargestellt, eine Adresse konfiguriert werden, über die der Server eine Verbindung mit dem Client herstellen kann.  
  
```xml  
<client>  
  <endpoint name=""  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="wsDualHttpBinding"   
            bindingConfiguration="DuplexBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
</client>  
  
<bindings>  
  <!-- Configure a binding that support duplex communication. -->  
  <wsDualHttpBinding>  
    <binding name="DuplexBinding"   
             clientBaseAddress="http://localhost:8000/myClient/">  
    </binding>  
  </wsDualHttpBinding>  
</bindings>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die auf dem Client zurückgegebenen Nachrichten in der vom Dienst gesendeten Rückrufschnittstelle angezeigt. Alle Zwischenergebnisse werden angezeigt, gefolgt von der ganzen Formel nach Abschluss aller Vorgänge. Drücken Sie die EINGABETASTE, um den Client zu schließen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#-, C++ oder Visual Basic .NET .NET-Edition der Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!IMPORTANT]
    >  Beim Ausführen des Clients in einer computerübergreifenden Konfiguration müssen ersetzen Sie "Localhost" sowohl die `address` Attribut der [Endpunkt](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) Element und die `clientBaseAddress` Attribut der [ \< Binden von >](../../../../docs/framework/misc/binding.md) Element der [ \<WsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) Element mit dem Namen des entsprechenden Computers, wie im folgenden gezeigt:  
  
    ```xml  
    <client>  
    <endpoint name = ""  
    address="http://service_machine_name/servicemodelsamples/service.svc"  
    ... />  
    </client>  
    ...  
    <wsDualHttpBinding>  
    <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">  
    </binding>  
    </wsDualHttpBinding>  
    ```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`  
  
## <a name="see-also"></a>Siehe auch
