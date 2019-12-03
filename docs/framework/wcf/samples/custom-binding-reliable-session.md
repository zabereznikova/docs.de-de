---
title: Benutzerdefiniertes Binden von zuverlässigen Sitzungen
ms.date: 03/30/2017
ms.assetid: c5fcd409-246f-4f3e-b3f1-629506ca4c04
ms.openlocfilehash: c39dc9c57332800628012e88e1b274296556e756
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710946"
---
# <a name="custom-binding-reliable-session"></a>Benutzerdefiniertes Binden von zuverlässigen Sitzungen

Eine benutzerdefinierte Bindung wird durch eine geordnete Liste einzelner Bindungselemente definiert. Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte Bindung mit verschiedenen Transportarten und Nachrichtencodierungselementen insbesondere zur Aktivierung zuverlässiger Sitzungen konfiguriert wird.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSession`

## <a name="sample-details"></a>Beispieldetails

Zuverlässige Sitzungen bieten Funktionen für zuverlässiges Messaging. Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen, wie Prüfung der Nachrichtenreihenfolge beim Eingang, vorgenommen. Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht. Im Beispiel werden Sitzungen zum Aufrechterhalten des Clientstatus implementiert und eine Zustellungszusicherungen anhand der Nachrichtenreihenfolge festgelegt. Das Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird. Die Funktionen für zuverlässige Sitzungen sind in den Anwendungskonfigurationsdateien für Client und Dienst aktiviert und konfiguriert.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Die Reihenfolge der Bindungs Elemente ist beim Definieren einer benutzerdefinierten Bindung wichtig, da jede eine Ebene im Kanal Stapel darstellt (siehe [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)).

Die Dienstkonfiguration des Beispiels wird wie im folgenden Codebeispiel dargestellt definiert.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                     requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous" bypassProxyOnLocal="false"
                        hostNameComparisonMode="StrongWildcard"
                        proxyAuthenticationScheme="Anonymous" realm=""
                        useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

Bei Ausführung in einem computerübergreifenden Szenario müssen Sie die Endpunktadresse des Clients so ändern, dass der Hostname des Diensts widergespiegelt wird.

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl:

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

    > [!IMPORTANT]
    > Beim Ausführen des Clients in einer Computer übergreifenden Konfiguration müssen Sie "localhost" sowohl im `address`-Attribut des [\<Endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) -Elements als auch im `clientBaseAddress`-Attribut des [\<compositeDuplex->](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) durch den Namen des entsprechenden Computers ersetzen, wie im folgenden Beispiel gezeigt.

    ```xml
    <endpoint name = ""
    address="http://service_machine_name/servicemodelsamples/service.svc"
    ... />
    <compositeDuplex clientBaseAddress="http://client_machine_name:8000/myClient/" />
    ```
