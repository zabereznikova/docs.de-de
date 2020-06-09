---
title: ASMX-Client mit einem WCF-Dienst
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: fd13d4907f1be09440387a36e14ecdc4926ba7e7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594776"
---
# <a name="asmx-client-with-a-wcf-service"></a>ASMX-Client mit einem WCF-Dienst

In diesem Beispiel wird veranschaulicht, wie ein Dienst mithilfe von Windows Communication Foundation (WCF) erstellt und dann von einem nicht-WCF-Client (z. b. einem ASMX-Client) auf den Dienst zugegriffen wird.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll). Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird durch die `ICalculator`-Schnittstelle definiert, die mathematische Operationen (`Add`, `Subtract`, `Multiply` und `Divide`) verfügbar macht. Der ASMX-Client stellt synchrone Anforderungen an eine mathematische Operation, und der Dienst antwortet mit dem Ergebnis.

Der Dienst implementiert einen `ICalculator`-Vertrag, wie im folgenden Code definiert.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
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

<xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Xml.Serialization.XmlSerializer> ordnen CLR-Typen einer XML-Darstellung zu. Der <xref:System.Runtime.Serialization.DataContractSerializer> übersetzt einige XML-Darstellungen anders als XmlSerializer. Nicht-WCF-Proxy Generatoren, wie z. b. WSDL. exe, generieren bei Verwendung von XmlSerializer eine besser verwendbare Schnittstelle. <xref:System.ServiceModel.XmlSerializerFormatAttribute>Wird auf die- `ICalculator` Schnittstelle angewendet, um sicherzustellen, dass das XmlSerializer-Element für die Zuordnung von CLR-Typen zu XML verwendet wird. Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.

Der Dienst macht einen einzigen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit einer Konfigurationsdatei (Web.conf) definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Der Dienst macht den Endpunkt bei der vom IIS-Host bereitgestellten Basisadresse verfügbar. Das `binding`-Attribut wird auf basicHttpBinding festgelegt, was die HTTP-Kommunikation über SOAP 1.1 ermöglicht, das mit WS-I BasicProfile 1.1 kompatibel ist, wie in der folgenden Beispielkonfiguration dargestellt.

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

Der ASMX-Client kommuniziert mit dem WCF-Dienst mithilfe eines typisierten Proxys, Web Services Description Language der vom WSDL-Hilfsprogramm (WSDL. exe) generiert wird. Der typisierte Proxy ist in der Datei generatedClient.cs enthalten. Das WSDL-Dienstprogramm ruft Metadaten für den angegebenen Dienst ab und generiert einen typisierten Proxy, den ein Client zur Kommunikation verwenden kann. Standardmäßig macht das Framework keine Metadaten verfügbar. Um die zum Generieren des Proxys erforderlichen Metadaten verfügbar zu machen, müssen Sie eine hinzufügen und das zugehörige [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) - `httpGetEnabled` Attribut auf festlegen, `True` wie in der folgenden Konfiguration gezeigt.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

Unter Verwendung des generierten typisierten Proxys kann der Client auf einen bestimmten Endpunkt zugreifen, indem er die entsprechende Adresse konfiguriert. Der Client gibt den Endpunkt, mit dem er kommunizieren möchte, mithilfe einer Konfigurationsdatei (App.config) an.

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

Die Clientimplementierung erstellt eine Instanz des typisierten Proxys, um die Kommunikation mit dem Dienst zu beginnen.

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
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

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

> [!NOTE]
> Weitere Informationen zum übergeben und zurückgeben komplexer Datentypen finden Sie unter: [Datenbindung in einem Windows Forms Client](data-binding-in-a-windows-forms-client.md), [Datenbindung in einem Windows Presentation Foundation Client](data-binding-in-a-wpf-client.md)und [Datenbindung in einem ASP.NET-Client](data-binding-in-an-aspnet-client.md) .

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
