---
title: 'Benutzerdefinierter Nachrichtenencoder: Komprimierungsencoder'
ms.date: 03/30/2017
ms.assetid: 57450b6c-89fe-4b8a-8376-3d794857bfd7
ms.openlocfilehash: db20ec20579d6fcb0ec202920db0d7781b0676df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600619"
---
# <a name="custom-message-encoder-compression-encoder"></a>Benutzerdefinierter Nachrichtenencoder: Komprimierungsencoder

In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Encoder mithilfe der Windows Communication Foundation (WCF)-Plattform implementiert wird.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`

## <a name="sample-details"></a>Beispieldetails

Das Beispiel besteht aus einem Clientkonsolenprogramm (.exe), einem selbst gehosteten Dienstkonsolenprogramm (.exe) und einer Komprimierungsnachrichtenencoder-Bibliothek (.dll). Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird durch die `ISampleServer`-Schnittstelle definiert, die allgemeine Zeichenfolgen-Echovorgänge (`Echo` und `BigEcho`) verfügbar macht. Der Client stellt synchrone Anforderungen an einen angegebenen Vorgang, und der Dienst antwortet dem Client, indem er die Nachricht wiederholt. Client- und Dienstaktivität sind in den Konsolenfenstern sichtbar. Das Beispiel soll zeigen, wie ein benutzerdefinierter Encoder geschrieben wird und wie sich das Komprimieren einer Nachricht auf das Netzwerk auswirkt. Sie können dem Komprimierungsnachrichtenencoder eine Instrumentierung zum Berechnen der Nachrichtengröße und/oder der Verarbeitungszeit hinzufügen.

> [!NOTE]
> In der .NET Framework 4 wurde die automatische Dekomprimierung auf einem WCF-Client aktiviert, wenn der Server eine komprimierte Antwort sendet (erstellt mit einem Algorithmus wie z. b. gzip oder deflate). Bei einem im Internet über Internet Information Server (IIS) gehosteten Dienst kann IIS so konfiguriert werden, dass der Dienst eine komprimierte Antwort sendet. Dieses Beispiel kann verwendet werden, wenn die Komprimierung und Dekomprimierung für den Client und für den Dienst durchgeführt werden müssen oder wenn der Dienst selbst gehostet wird.

Das Beispiel veranschaulicht, wie ein benutzerdefinierter Nachrichten Encoder erstellt und in eine WCF-Anwendung integriert wird. Die Bibliothek "GZipEncoder.dll" wird sowohl mit dem Client als auch mit dem Dienst bereitgestellt. Das Beispiel zeigt auch, wie sich das Komprimieren von Nachrichten auswirkt. Der Code in der "GZipEncoder.dll" zeigt Folgendes:

- Das Erstellen eines benutzerdefinierten Encoders und einer Encoder-Factory.

- Das Entwickeln eines Bindungselements für einen benutzerdefinierten Encoder.

- Das Verwenden der benutzerdefinierten Bindungskonfiguration zum Integrieren von benutzerdefinierten Bindungselementen.

- Das Entwickeln eines benutzerdefinierten Konfigurationshandlers, um die Dateikonfiguration eines benutzerdefinierten Bindungselements zu ermöglichen.

Wie schon erwähnt, gibt es mehrere Ebenen, die in einem benutzerdefinierten Encoder implementiert werden. Um die Beziehungen zwischen den einzelnen Ebenen besser veranschaulichen zu können, enthält die folgende Liste eine vereinfachte Abfolge der Ereignisse beim Starten des Diensts.

1. Der Server startet.

2. Die Konfigurationsinformationen werden gelesen.

    1. Die Dienstkonfiguration registriert den benutzerdefinierten Konfigurationshandler.

    2. Der Diensthost wird erstellt und geöffnet.

    3. Das benutzerdefinierte Konfigurationselement erstellt das benutzerdefinierte Bindungselement und gibt es zurück.

    4. Das benutzerdefinierte Bindungselement erstellt eine Nachrichtenencoder-Factory und gibt sie zurück.

3. Eine Nachricht wird empfangen.

4. Die Nachrichtenencoder-Factory gibt einen Nachrichtenencoder zum Lesen der Nachricht und Schreiben der Antwort zurück.

5. Die Encoderebene wird in Form einer Klassenfactory implementiert. Nur die Encoderklassenfactory muss für den benutzerdefinierten Encoder öffentlich verfügbar gemacht werden. Das Factoryobjekt wird vom Bindungselement zurückgegeben, wenn das <xref:System.ServiceModel.ServiceHost>-Objekt oder das <xref:System.ServiceModel.ChannelFactory%601>-Objekt erstellt wird. Nachrichtenencoder können im Puffermodus oder im Streamingmodus arbeiten. In diesem Beispiel werden sowohl der Puffermodus als auch der Streamingmodus veranschaulicht.

Für jeden Modus gibt es eine zugehörige `ReadMessage`- und `WriteMessage`-Methode in der abstrakten `MessageEncoder`-Klasse. In diesen Methoden findet der größte Teil der Codierungsarbeit statt. Das Beispiel schließt die vorhandenen Text- und Binärnachrichtenencoder ein. Auf diese Weise kann es das Lesen und Schreiben der Übertragungsdarstellung von Nachrichten an den inneren Encoder delegieren, und die Ergebnisse können vom Komprimierungsencoder komprimiert oder dekomprimiert werden. Da keine Pipeline für die Nachrichten Codierung vorhanden ist, ist dies das einzige Modell für die Verwendung mehrerer Encoder in WCF. Nachdem die Nachricht dekomprimiert wurde, wird die resultierende Nachricht an den Stapel weitergegeben, um vom Kanalstapel verarbeitet zu werden. Während der Komprimierung wird die resultierende komprimierte Nachricht direkt in den bereitgestellten Stream geschrieben.

In diesem Beispiel werden Hilfsmethoden (`CompressBuffer` und `DecompressBuffer`) verwendet, um die Konvertierung von Puffern in Streams zum Verwenden der `GZipStream`-Klasse auszuführen.

Die gepufferten `ReadMessage`-Klasse und `WriteMessage`-Klasse machen von der `BufferManager`-Klasse Gebrauch. Auf den Encoder kann nur über die Encoder-Factory zugegriffen werden. Die abstrakte `MessageEncoderFactory`-Klasse bietet zum Zugreifen auf den aktuellen Encoder eine Eigenschaft namens `Encoder` und zum Erstellen eines Encoders, der Sitzungen unterstützt, eine Methode namens `CreateSessionEncoder`. Ein solcher Encoder kann in Situationen verwendet werden, in denen der Kanal Sitzungen unterstützt, geordnet und zuverlässig ist. In diesem Szenario ist in jeder Sitzung, in der Daten zur Übertragung geschrieben werden, eine Optimierung möglich. Wenn dies nicht erwünscht ist, sollte die Basismethode nicht überladen werden. Die `Encoder`-Eigenschaft bietet einen Mechanismus zum Zugreifen auf den sitzungslosen Encoder, und der Wert der Eigenschaft wird von der Standardimplementierung der `CreateSessionEncoder`-Methode zurückgegeben. Da das Beispiel einen vorhandenen Encoder einschließt, um Komprimierung zu ermöglichen, akzeptiert die `MessageEncoderFactory`-Implementierung eine `MessageEncoderFactory`, die die innere Encoder-Factory darstellt.

Nun, da der Encoder und die Encoderfactory definiert sind, können Sie mit einem WCF-Client und-Dienst verwendet werden. Allerdings müssen diese Encoder dem Kanalstapel hinzugefügt werden. Zum manuellen Hinzufügen dieser Encoder-Factory können Sie Klassen von der <xref:System.ServiceModel.ServiceHost>-Klasse und der <xref:System.ServiceModel.ChannelFactory%601>-Klasse ableiten und die `OnInitialize`-Methoden überschreiben. Sie können die Encoder-Factory auch über ein benutzerdefiniertes Bindungselement verfügbar machen.

Zum Erstellen eines neuen benutzerdefinierten Bindungselements leiten Sie eine Klasse von der <xref:System.ServiceModel.Channels.BindingElement>-Klasse ab. Es gibt jedoch mehrere Typen von Bindungselementen. Um sicherzustellen, dass das benutzerdefinierte Bindungselement als ein Nachrichtencodierungs-Bindungselement erkannt wird, müssen Sie auch das <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> implementieren. Das <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> macht eine Methode zum Erstellen einer neuen Nachrichtenencoder-Factory verfügbar (`CreateMessageEncoderFactory`), die so implementiert ist, dass sie eine Instanz der übereinstimmenden Nachrichtenencoder-Factory zurückgibt. Außerdem besitzt das <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> eine Eigenschaft zum Angeben der Adressierungsversion. Da dieses Beispiel die vorhandenen Encoder einschließt, schließt die Implementierung des Beispiels auch die vorhandenen Encoderbindungselemente ein und nimmt ein inneres Encoderbindungselement als Parameter für den Konstruktor entgegen, das es über eine Eigenschaft verfügbar macht. Das folgende Codebeispiel zeigt die Implementierung der `GZipMessageEncodingBindingElement`-Klasse.

```csharp
public sealed class GZipMessageEncodingBindingElement
                        : MessageEncodingBindingElement //BindingElement
                        , IPolicyExportExtension
{

    //We use an inner binding element to store information
    //required for the inner encoder.
    MessageEncodingBindingElement innerBindingElement;

        //By default, use the default text encoder as the inner encoder.
        public GZipMessageEncodingBindingElement()
            : this(new TextMessageEncodingBindingElement()) { }

    public GZipMessageEncodingBindingElement(MessageEncodingBindingElement messageEncoderBindingElement)
    {
        this.innerBindingElement = messageEncoderBindingElement;
    }

    public MessageEncodingBindingElement InnerMessageEncodingBindingElement
    {
        get { return innerBindingElement; }
        set { innerBindingElement = value; }
    }

    //Main entry point into the encoder binding element.
    // Called by WCF to get the factory that creates the
    //message encoder.
    public override MessageEncoderFactory CreateMessageEncoderFactory()
    {
        return new
GZipMessageEncoderFactory(innerBindingElement.CreateMessageEncoderFactory());
    }

    public override MessageVersion MessageVersion
    {
        get { return innerBindingElement.MessageVersion; }
        set { innerBindingElement.MessageVersion = value; }
    }

    public override BindingElement Clone()
    {
        return new
        GZipMessageEncodingBindingElement(this.innerBindingElement);
    }

    public override T GetProperty<T>(BindingContext context)
    {
        if (typeof(T) == typeof(XmlDictionaryReaderQuotas))
        {
            return innerBindingElement.GetProperty<T>(context);
        }
        else
        {
            return base.GetProperty<T>(context);
        }
    }

    public override IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.BuildInnerChannelFactory<TChannel>();
    }

    public override IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.BuildInnerChannelListener<TChannel>();
    }

    public override bool CanBuildChannelListener<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.CanBuildInnerChannelListener<TChannel>();
    }

    void IPolicyExportExtension.ExportPolicy(MetadataExporter exporter, PolicyConversionContext policyContext)
    {
        if (policyContext == null)
        {
            throw new ArgumentNullException("policyContext");
        }
       XmlDocument document = new XmlDocument();
       policyContext.GetBindingAssertions().Add(document.CreateElement(
            GZipMessageEncodingPolicyConstants.GZipEncodingPrefix,
            GZipMessageEncodingPolicyConstants.GZipEncodingName,
            GZipMessageEncodingPolicyConstants.GZipEncodingNamespace));
    }
}
```

Beachten Sie, dass die `GZipMessageEncodingBindingElement`-Klasse die `IPolicyExportExtension`-Schnittstelle implementiert, sodass dieses Bindungselement als Richtlinie in Metadaten exportiert werden kann, wie im folgenden Beispiel gezeigt.

```xml
<wsp:Policy wsu:Id="BufferedHttpSampleServer_ISampleServer_policy">
    <wsp:ExactlyOne>
      <wsp:All>
        <gzip:text xmlns:gzip=
        "http://schemas.microsoft.com/ws/06/2004/mspolicy/netgzip1" />
       <wsaw:UsingAddressing />
     </wsp:All>
   </wsp:ExactlyOne>
</wsp:Policy>
```

Die `GZipMessageEncodingBindingElementImporter`-Klasse implementiert die `IPolicyImportExtension`-Schnittstelle, diese Klasse importiert die Richtlinie für `GZipMessageEncodingBindingElement`. Zum Importieren von Richtlinien in die Konfigurationsdatei kann das Tool "Svcutil.exe" verwendet werden. Zum Umgang mit `GZipMessageEncodingBindingElement` sollte der "Svcutil.exe.config" Folgendes hinzugefügt werden.

```xml
<configuration>
  <system.serviceModel>
    <extensions>
      <bindingElementExtensions>
        <add name="gzipMessageEncoding"
          type=
            "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
      </bindingElementExtensions>
    </extensions>
    <client>
      <metadata>
        <policyImporters>
          <remove type=
"System.ServiceModel.Channels.MessageEncodingBindingElementImporter, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
          <extension type=
"Microsoft.ServiceModel.Samples.GZipMessageEncodingBindingElementImporter, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </policyImporters>
      </metadata>
    </client>
  </system.serviceModel>
</configuration>
```

Nachdem nun ein passendes Bindungselement für den Komprimierungsencoder vorhanden ist, kann dieser programmgesteuert als Hook in den Dienst oder Client eingesetzt werden, indem ein neues benutzerdefiniertes Bindungsobjekt erstellt und dem benutzerdefinierten Bindungselement hinzugefügt wird, wie im folgenden Beispielcode gezeigt.

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
GZipMessageEncodingBindingElement compBindingElement = new GZipMessageEncodingBindingElement ();
bindingElements.Add(compBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
binding.Name = "SampleBinding";
binding.Namespace = "http://tempuri.org/bindings";
```

Obwohl dies für die meisten Benutzerszenarios ausreichen sollte, ist die Unterstützung einer Dateikonfiguration wichtig, wenn der Dienst im Web gehostet werden soll. Zur Unterstützung des Webhostszenarios müssen Sie einen benutzerdefinierten Konfigurationshandler erstellen, damit ein benutzerdefiniertes Bindungselement in einer Datei konfiguriert werden kann.

Sie können einen Konfigurations Handler für das Bindungs Element zusätzlich zum Konfigurationssystem erstellen. Der Konfigurationshandler für das Bindungselement muss von der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>-Klasse abgeleitet sein. Der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType> informiert das Konfigurationssystem über den Typ des Bindungs Elements, das für diesen Abschnitt erstellt werden soll. Sämtliche Aspekte des `BindingElement`, die festgelegt werden können, sollten in der abgeleiteten <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>-Klasse als Eigenschaften zugänglich gemacht werden. Der unter <xref:System.Configuration.ConfigurationPropertyAttribute> stützt das Mapping der Konfigurationselement Attribute zu den Eigenschaften und das Festlegen von Standardwerten, wenn Attribute fehlen. Nachdem die Werte aus der Konfiguration geladen und auf die Eigenschaften angewendet wurden, wird die <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType>-Methode aufgerufen, die die Eigenschaften in eine konkrete Instanz eines Bindungselements konvertiert. Die- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> Methode wird verwendet, um die Eigenschaften in der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> abgeleiteten Klasse in die Werte zu konvertieren, die für das neu erstellte Bindungs Element festgelegt werden sollen.

Das folgenden Codebeispiel zeigt die Implementierung des `GZipMessageEncodingElement`.

```csharp
public class GZipMessageEncodingElement : BindingElementExtensionElement
{
    public GZipMessageEncodingElement()
    {
    }

//Called by the WCF to discover the type of binding element this
//config section enables
    public override Type BindingElementType
    {
        get { return typeof(GZipMessageEncodingBindingElement); }
    }

    //The only property we need to configure for our binding element is
    //the type of inner encoder to use. Here, we support text and
    //binary.
    [ConfigurationProperty("innerMessageEncoding",
                         DefaultValue = "textMessageEncoding")]
    public string InnerMessageEncoding
    {
        get { return (string)base["innerMessageEncoding"]; }
        set { base["innerMessageEncoding"] = value; }
    }

    //Called by the WCF to apply the configuration settings (the
    //property above) to the binding element
    public override void ApplyConfiguration(BindingElement bindingElement)
    {
        GZipMessageEncodingBindingElement binding =
                (GZipMessageEncodingBindingElement)bindingElement;
        PropertyInformationCollection propertyInfo =
                    this.ElementInformation.Properties;
        if (propertyInfo["innerMessageEncoding"].ValueOrigin !=
                                     PropertyValueOrigin.Default)
        {
            switch (this.InnerMessageEncoding)
            {
                case "textMessageEncoding":
                    binding.InnerMessageEncodingBindingElement =
                      new TextMessageEncodingBindingElement();
                    break;
                case "binaryMessageEncoding":
                    binding.InnerMessageEncodingBindingElement =
                         new BinaryMessageEncodingBindingElement();
                    break;
            }
        }
    }

    //Called by the WCF to create the binding element
    protected override BindingElement CreateBindingElement()
    {
        GZipMessageEncodingBindingElement bindingElement =
                new GZipMessageEncodingBindingElement();
        this.ApplyConfiguration(bindingElement);
        return bindingElement;
    }
}
```

Dieser Konfigurationshandler ordnet die folgende Darstellung in der App.config oder Web.config für den Dienst oder Client zu.

```xml
<gzipMessageEncoding innerMessageEncoding="textMessageEncoding" />
```

Um diesen Konfigurations Handler zu verwenden, muss er innerhalb des- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Elements registriert werden, wie in der folgenden Beispielkonfiguration gezeigt.

```xml
<extensions>
    <bindingElementExtensions>
       <add
           name="gzipMessageEncoding"
           type=
           "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement,
           GZipEncoder, Version=1.0.0.0, Culture=neutral,
           PublicKeyToken=null" />
      </bindingElementExtensions>
</extensions>
```

Beim Ausführen des Servers werden die Vorgangsanforderungen und -antworten im Konsolenfenster angezeigt. Drücken Sie im Fenster die EINGABETASTE, um den Server zu schließen.

```console
Press Enter key to Exit.

        Server Echo(string input) called:
        Client message: Simple hello

        Server BigEcho(string[] input) called:
        64 client messages
```

Beim Ausführen des Clients werden die Vorgangsanforderungen und -antworten im Konsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
Calling Echo(string):
Server responds: Simple hello Simple hello

Calling BigEcho(string[]):
Server responds: Hello 0

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl:

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

3. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`
