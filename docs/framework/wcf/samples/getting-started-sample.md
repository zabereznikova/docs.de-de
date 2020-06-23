---
title: Beispiel 'Erste Schritte'
description: Erfahren Sie, wie Sie einen typischen Dienst und einen typischen Client mithilfe von WCF implementieren. Es dient als Grundlage für alle anderen grundlegenden Technologiebeispiele.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: b23be1b33f227154b916429c063ec4106229bb3c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246232"
---
# <a name="getting-started-sample"></a>Beispiel 'Erste Schritte'

Das Beispiel "Getting Started" veranschaulicht, wie ein typischer Dienst und ein typischer Client mithilfe von Windows Communication Foundation (WCF) implementiert werden. Es dient als Grundlage für alle anderen grundlegenden Technologiebeispiele.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

Der Dienst beschreibt die Vorgänge, die er in einem Dienstvertrag ausführt, den er öffentlich als Metadaten verfügbar macht. Der Dienst enthält auch den Code, um die Vorgänge zu implementieren.

Der Client enthält eine Definition des Dienstvertrags und eine Proxyklasse zum Zugreifen auf den Dienst. Der Proxy Code wird aus den Dienst Metadaten mit dem Service [Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert.

Unter Windows Vista wird der-Dienst im Windows-Aktivierungs Dienst (was) gehostet. Unter Windows XP und Windows Server 2003 wird Sie von Internetinformationsdienste (IIS) und ASP.net gehostet. Durch das Hosten eines Diensts in IIS oder WAS kann der Dienst beim ersten Zugriff automatisch aktiviert werden.

> [!NOTE]
> Wenn Sie lieber mit einem Beispiel beginnen möchten, das den Dienst in einer Konsolenanwendung anstelle von IIS hostet, finden Sie weitere Informationen unter [Self-Host-](self-host.md) Beispiel.

Der Dienst und der Client legen in den Einstellungen der Konfigurationsdatei Zugriffsdetails fest, die zum Zeitpunkt der Bereitstellung Flexibilität bieten. Dazu gehört eine Endpunktdefinition, die eine Adresse, eine Bindung und einen Vertrag angibt. Die Bindung gibt Transport- und Sicherheitsdetails für den Zugriff auf den Dienst an.

Der Dienst konfiguriert ein Laufzeitverhalten, um seine Metadaten zu veröffentlichen.

Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht. Der Client stellt Anforderungen an eine angegebene mathematische Operation, und der Dienst antwortet mit dem Ergebnis. Der Dienst implementiert einen `ICalculator`-Vertrag, der im folgenden Code definiert wird.

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

```csharp
// Define a service contract.
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

Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück, wie im folgenden Beispielcode dargestellt.

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

```csharp
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

Der Dienst macht einen Endpunkt zur Kommunikation mit dem Dienst verfügbar. Dieser Endpunkt wird mit einer Konfigurationsdatei (Web.config) definiert, wie in der folgenden Beispielkonfiguration gezeigt.

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

Der Dienst macht den Endpunkt bei der vom IIS-Host oder WAS-Host bereitgestellten Basisadresse verfügbar. Die Bindung ist mit einer standardmäßigen <xref:System.ServiceModel.WSHttpBinding> konfiguriert, die HTTP-Kommunikation und standardmäßige Webdienstprotokolle für die Adressierung und Sicherheit bietet. Bei dem Vertrag handelt es sich um den vom Dienst implementierten `ICalculator`.

Wie konfiguriert, kann `http://localhost/servicemodelsamples/service.svc` von einem Client auf dem gleichen Computer auf den Dienst zugegriffen werden. Bei Clients auf Remotecomputern muss für den Dienstzugriff anstelle von localhost ein vollqualifizierter Domänenname angegeben werden.

Standardmäßig macht das Framework keine Metadaten verfügbar. Daher wird der-Dienst eingeschaltet und macht <xref:System.ServiceModel.Description.ServiceMetadataBehavior> einen MEX-Endpunkt (Metadata Exchange) unter verfügbar `http://localhost/servicemodelsamples/service.svc/mex` . Dies wird in der folgenden Konfiguration veranschaulicht.

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

Der Client kommuniziert mithilfe eines angegebenen Vertrags Typs mithilfe einer Client Klasse, die vom [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert wird. Dieser generierte Client ist in der Datei "generatedClient.cs" oder der Datei "generatedClient.vb" enthalten. Dieses Hilfsprogramm ruft Metadaten für einen angegebenen Dienst ab und generiert einen Client, den die Clientanwendung zur Kommunikation mithilfe eines angegebenen Vertragstyps verwenden kann. Der gehostete Dienst muss zur Generierung des Clientcodes verfügbar sein, da der Dienst zum Abrufen der aktualisierten Metadaten verwendet wird.

 Führen Sie den folgenden Befehl an der SDK-Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren:

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

Geben Sie zum Generieren des Clients in Visual Basic die folgende Zeichenfolge an der SDK-Eingabeaufforderung ein:

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

Wenn der generierte Client verwendet wird, kann der Client auf einen bestimmten Endpunkt zugreifen, indem er die entsprechende Adresse und Bindung konfiguriert. Wie auch der Dienst gibt der Client den Endpunkt, mit dem er kommunizieren möchte, mithilfe einer Konfigurationsdatei (App.config) an. Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag, wie im folgenden Beispiel gezeigt.

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

Die Clientimplementierung instanziiert den Client und verwendet die typisierte Schnittstelle, um die Kommunikation mit dem Dienst zu beginnen, wie im folgenden Codebeispiel gezeigt.

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

Im Beispiel "Erste Schritte" wird der Standard zum Erstellen eines Diensts oder Clients veranschaulicht. Der andere [grundlegende](basic-sample.md) Build in diesem Beispiel, um bestimmte Produkt Features zu veranschaulichen.

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
