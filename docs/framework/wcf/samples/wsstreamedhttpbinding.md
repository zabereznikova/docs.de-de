---
title: WSStreamedHttpBinding
ms.date: 03/30/2017
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
ms.openlocfilehash: 619c7e793ff94efffcb72774cf3e367df377a3a3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600892"
---
# <a name="wsstreamedhttpbinding"></a>WSStreamedHttpBinding

Das Beispiel veranschaulicht, wie eine Bindung erstellt wird, die Streamingszenarios unterstützt, wenn HTTP-Transport verwendet wird.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`

 Zum Erstellen und Konfigurieren einer neuen Standardbindung müssen folgende Schritte ausgeführt werden.

1. Erstellen einer neuen Standardbindung

    Die Standard Bindungen in Windows Communication Foundation (WCF), z. b. BasicHttpBinding und NetTcpBinding, konfigurieren die zugrunde liegenden Transporte und den Kanal Stapel für bestimmte Anforderungen. In diesem Beispiel konfiguriert `WSStreamedHttpBinding` den Kanalstapel, um Streaming zu unterstützen. Standardmäßig werden WS-Sicherheit und zuverlässiges Messaging nicht zum Kanalstapel hinzugefügt, da beide Funktionen nicht vom Streaming unterstützt werden. Die neue Bindung wird in die Klasse `WSStreamedHttpBinding` implementiert, die von <xref:System.ServiceModel.Channels.Binding> abgeleitet ist. `WSStreamedHttpBinding` enthält die folgenden Bindungselemente: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> und <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. Die Klasse stellt eine `CreateBindingElements()`-Methode bereit, um den resultierenden Bindungsstapel zu konfigurieren, wie im folgenden Codebeispiel gezeigt.

    ```csharp
    public override BindingElementCollection CreateBindingElements()
    {
        // return collection of BindingElements
        BindingElementCollection bindingElements = new BindingElementCollection();

        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by
        // the message encoder, and finally the transport at the end
        if (flowTransactions)
        {
            bindingElements.Add(transactionFlow);
        }
        bindingElements.Add(textEncoding);

        // add transport (http or https)
        bindingElements.Add(transport);
        return bindingElements.Clone();
    }
    ```

2. Hinzufügen von Konfigurationsunterstützung

    Im Beispiel werden zwei weitere Klassen – `WSStreamedHttpBindingConfigurationElement` und `WSStreamedHttpBindingSection` – implementiert, um den Transport durch Konfiguration verfügbar zu machen. Die-Klasse `WSStreamedHttpBindingSection` ist eine <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> , die `WSStreamedHttpBinding` für das WCF-Konfigurationssystem verfügbar macht. Der Großteil der Implementierung wird dem `WSStreamedHttpBindingConfigurationElement` übertragen, das von <xref:System.ServiceModel.Configuration.StandardBindingElement> abgeleitet wird. Die Klasse `WSStreamedHttpBindingConfigurationElement` verfügt über Eigenschaften, die mit den Eigenschaften von `WSStreamedHttpBinding` übereinstimmen, sowie über Funktionen, um jedes Konfigurationselement einer Bindung zuzuordnen.

    Registrieren Sie den Handler mit dem Konfigurationssystem, indem Sie den folgenden Abschnitt zur Konfigurationsdatei des Diensts hinzufügen.

    ```xml
    <configuration>
      <system.serviceModel>
        <extensions>
          <bindingExtensions>
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />
          </bindingExtensions>
        </extensions>
      </system.serviceModel>
    </configuration>
    ```

    Auf den Handler kann vom serviceModel-Konfigurationsabschnitt aus verwiesen werden.

    ```xml
    <configuration>
      <system.serviceModel>
        <client>
          <endpoint
                    address="https://localhost/servicemodelsamples/service.svc"
                    bindingConfiguration="Binding"
                    binding="wsStreamedHttpBinding"
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>
        </client>
      </system.serviceModel>
    </configuration>
    ```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Stellen Sie sicher, dass Sie die in [der einmaligen Installation aufgeführten Schritte für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

3. Stellen Sie sicher, dass Sie die [Installationsanweisungen für das Internetinformationsdienste (IIS)-Server Zertifikat](iis-server-certificate-installation-instructions.md)durchgeführt haben.

4. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

5. Befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md), um das Beispiel in einer Computer übergreifenden Konfiguration auszuführen.

6. Wenn das Clientfenster angezeigt wird, geben Sie "Sample.txt" ein. In Ihrem Verzeichnis sollte sich eine Datei "Copy of Sample.txt" befinden.

## <a name="the-wsstreamedhttpbinding-sample-service"></a>Der WSStreamedHttpBinding-Beispieldienst

Der Beispieldienst, der die `WSStreamedHttpBinding` verwendet, befindet sich im Dienstunterverzeichnis. Die Implementierung von `OperationContract` verwendet einen `MemoryStream`, um zuerst alle Daten vom eingehenden Stream abzurufen, bevor der `MemoryStream` zurückgegeben wird. Der Beispieldienst wird von Internetinformationsdiensten (IIS) gehostet.

```csharp
[ServiceContract]
public interface IStreamedEchoService
{
    [OperationContract]
    Stream Echo(Stream data);
}

public class StreamedEchoService : IStreamedEchoService
{
    public Stream Echo(Stream data)
    {
        MemoryStream dataStorage = new MemoryStream();
        byte[] byteArray = new byte[8192];
        int bytesRead = data.Read(byteArray, 0, 8192);
        while (bytesRead > 0)
        {
            dataStorage.Write(byteArray, 0, bytesRead);
            bytesRead = data.Read(byteArray, 0, 8192);
        }
        data.Close();
        dataStorage.Seek(0, SeekOrigin.Begin);

        return dataStorage;
    }
}
```

## <a name="the-wsstreamedhttpbinding-sample-client"></a>Der WSStreamedHttpBinding-Beispielclient

Der Client, der für die Interaktion mit dem Dienst über `WSStreamedHttpBinding` verwendet wird, befindet sich im Clientunterverzeichnis. Da es sich bei dem in diesem Beispiel verwendeten Zertifikat um ein Test Zertifikat handelt, das mit Makecert. exe erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, auf eine HTTPS-Adresse in Ihrem Browser zuzugreifen, z.b. `https://localhost/servicemodelsamples/service.svc` . Damit der WCF-Client mit einem vorhandenen Test Zertifikat arbeiten kann, wurde dem Client zusätzlicher Code hinzugefügt, um die Sicherheitswarnung zu unterdrücken. Der Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.

```csharp
// WARNING: This code is only required for test certificates such as those created by makecert. It is
// not recommended for production code.
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");
```
