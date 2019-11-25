---
title: Duale WS-Http-Verbindung
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 44fdf6f0b27e15c486afa32f67668e9fd6eeac10
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138675"
---
# <a name="ws-dual-http"></a>Duale WS-Http-Verbindung

Im Beispiel zur dualen Http-Verbindung wird veranschaulicht, wie die `WSDualHttpBinding`-Bindung konfiguriert wird. Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll). Der Dienst implementiert einen Duplexvertrag. Der Vertrag wird von der `ICalculatorDuplex`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht. In diesem Beispiel kann der Client durch die `ICalculatorDuplex`-Schnittstelle mathematische Operationen ausführen (Berechnen eines aktuellen Ergebnisses über die Sitzung). Unabhängig davon gibt der Dienst Ergebnisse auf der `ICalculatorDuplexCallback`-Schnittstelle zurück. Ein Duplexvertrag erfordert eine Sitzung, da ein Kontext eingerichtet werden muss, um die zwischen Client und Dienst gesendeten Nachrichten in Beziehung zu setzen. Die `WSDualHttpBinding`-Bindung unterstützt Duplexkommunikation.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`

Legen Sie zum Konfigurieren eines Dienstendpunkts mit der `WSDualHttpBinding` die Bindung in der Endpunktkonfiguration wie folgt fest.

```xml
<endpoint address=""
         binding="wsDualHttpBinding"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
```

Auf dem Client muss, wie in der folgenden Beispielkonfiguration dargestellt, eine Adresse konfiguriert werden, über die der Server eine Verbindung mit dem Client herstellen kann.

```xml
<system.serviceModel>
  <client>
    <endpoint address=
         "http://localhost/servicemodelsamples/service.svc"
         binding="wsDualHttpBinding"
         bindingConfiguration="Binding1"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
  </client>

  <bindings>
    <!-- Configure a WSDualHttpBinding that supports duplex -->
    <!-- communication. -->
    <wsDualHttpBinding>
      <binding name="Binding1"
               clientBaseAddress="http://localhost:8000/myClient/"
               useDefaultWebProxy="true"
               bypassProxyOnLocal="false">
      </binding>
    </wsDualHttpBinding>
  </bindings>
</system.serviceModel>
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
Press <ENTER> to terminate client once the output is displayed.

Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

Wenn Sie das Beispiel ausführen, werden die vom Client zurückgegebenen Nachrichten in der vom Dienst gesendeten Rückrufschnittstelle angezeigt. Alle Zwischenergebnisse werden angezeigt, gefolgt von der ganzen Formel nach Abschluss aller Vorgänge. Drücken Sie die EINGABETASTE, um den Client zu schließen.

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

    > [!IMPORTANT]
    > Beim Ausführen des Clients in einer Computer übergreifenden Konfiguration müssen Sie "localhost" sowohl im `address`-Attribut des [\<-Endpunkts > \<Client >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Elements als auch im `clientBaseAddress`-Attribut der [\<Bindung ersetzen >](../../configure-apps/file-schema/wcf/bindings.md) -Element des [\<WSDualHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) Element mit dem Namen des entsprechenden Computers, wie hier gezeigt:

    ```xml
    <client>
        <endpoint name = ""
          address=
         "http://service_machine_name/servicemodelsamples/service.svc"
        />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress=
            "http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```
