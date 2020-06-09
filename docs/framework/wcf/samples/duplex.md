---
title: Duplex
ms.date: 03/30/2017
helpviewer_keywords:
- Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
ms.openlocfilehash: 77eab6a4975fc67c20558a53f399c7e709215587
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575198"
---
# <a name="duplex"></a>Duplex

Im Duplexbeispiel wird das Definieren und Implementieren eines Duplexvertrags veranschaulicht. Duplexkommunikation findet statt, wenn ein Client eine Sitzung mit einem Dienst einrichtet und dem Dienst einen Kanal bereitstellt, über den der Dienst Nachrichten zurück an den Client senden kann. Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten. Ein Duplexvertrag wird als Paar von Schnittstellen definiert: eine primäre Schnittstelle vom Client zum Dienst und eine Rückrufschnittstelle vom Dienst zum Client. In diesem Beispiel kann der Client durch die `ICalculatorDuplex`-Schnittstelle mathematische Operationen ausführen (Berechnen eines Ergebnisses über eine Sitzung). Der Dienst gibt Ergebnisse auf der `ICalculatorDuplexCallback`-Schnittstelle zurück. Ein Duplexvertrag erfordert eine Sitzung, da ein Kontext eingerichtet werden muss, um die zwischen dem Client und dem Dienst gesendeten Nachrichten in Beziehung zu setzen.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet. Der Duplexvertrag wird wie folgt definiert:

```csharp
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

```csharp
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
        Callback.Equation($"{equation} = {result}");
        equation = result.ToString();
    }

    public void AddTo(double n)
    {
        result += n;
        equation += $" + {n}";
        Callback.Result(result);
    }

    //...

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

```csharp
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

```csharp
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

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die c#-, C++-oder Visual Basic .NET-Edition der Projekt Mappe zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md).

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

    > [!IMPORTANT]
    > Beim Ausführen des Clients in einer Computer übergreifenden Konfiguration müssen Sie "localhost" sowohl im `address` -Attribut des [ \<endpoint> \<client> ](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Elements als auch im-Attribut des-Elements des-Elements `clientBaseAddress` [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) durch den Namen des entsprechenden Computers ersetzen, wie im folgenden dargestellt:

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
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`
