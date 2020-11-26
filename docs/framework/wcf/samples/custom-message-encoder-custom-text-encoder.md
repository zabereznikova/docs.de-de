---
title: 'Benutzerdefinierter Nachrichtenencoder: Benutzerdefinierter Textencoder'
description: Verwenden Sie dieses Beispiel, um einen benutzerdefinierten Textnachrichten Encoder mithilfe von WCF zu implementieren. Dieser Encoder unterstützt alle von der Plattform unterstützten Zeichen Codierungen für die Interoperabilität.
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 89f0bf09ba6408e24f642a67f2e7ac8243608dcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240965"
---
# <a name="custom-message-encoder-custom-text-encoder"></a>Benutzerdefinierter Nachrichtenencoder: Benutzerdefinierter Textencoder

In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Textnachrichten Encoder mithilfe von Windows Communication Foundation (WCF) implementiert wird.

> [!WARNING]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`

Der <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> von WCF unterstützt nur die Unicode-Codierungen UTF-8, UTF-16 und Big--Dian. Der benutzerdefinierte Textnachrichten Encoder in diesem Beispiel unterstützt alle von der Plattform unterstützten Zeichen Codierungen, die möglicherweise für die Interoperabilität erforderlich sind. Das Beispiel besteht aus einem Client Konsolenprogramm (. exe), einer von Internetinformationsdienste (IIS) gehosteten Dienst Bibliothek (. dll) und einer Textnachrichten Encoder-Bibliothek (. dll). Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht. Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und der Dienst antwortet mit dem Ergebnis. Sowohl Client als auch Dienst verwenden den `CustomTextMessageEncoder` anstelle des Standard-<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.

Die Implementierung für den benutzerdefinierten Encoder besteht aus einer Nachrichtenencoder-Factory, einem Nachrichtenencoder, einem Nachrichtencodierungs-Bindungselement und einem Konfigurationshandler. Es wird Folgendes veranschaulicht:

- Das Erstellen eines benutzerdefinierten Encoders und einer Encoder-Factory.

- Das Erstellen eines Bindungselements für einen benutzerdefinierten Encoder.

- Das Verwenden der benutzerdefinierten Bindungskonfiguration zum Integrieren von benutzerdefinierten Bindungselementen.

- Das Entwickeln eines benutzerdefinierten Konfigurationshandlers, um die Dateikonfiguration eines benutzerdefinierten Bindungselements zu ermöglichen.

## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

3. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

## <a name="message-encoder-factory-and-the-message-encoder"></a>Nachrichtenencoder-Factory und der Nachrichtenencoder

Wenn der <xref:System.ServiceModel.ServiceHost> oder der Clientkanal geöffnet wird, erstellt die Entwurfszeit-Komponente `CustomTextMessageBindingElement` die `CustomTextMessageEncoderFactory`. Die Factory erstellt den `CustomTextMessageEncoder`. Der Nachrichtenencoder operiert sowohl im Streamingmodus als auch im Puffermodus. Er verwendet den <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> zum Schreiben bzw. Lesen der Nachrichten. Im Gegensatz zu den optimierten XML-Readern und-Writern von WCF, die nur UTF-8-, UTF-16-und Big-in-Unicode unterstützen, unterstützen diese Reader und Writer alle Platt Form gestützten Codierungen.

Das folgende Codebeispiel zeigt den benutzerdefinierten Textnachrichtenencoder (CustomTextMessageEncoder).

```csharp
public class CustomTextMessageEncoder : MessageEncoder
{
    private CustomTextMessageEncoderFactory factory;
    private XmlWriterSettings writerSettings;
    private string contentType;

    public CustomTextMessageEncoder(CustomTextMessageEncoderFactory factory)
    {
        this.factory = factory;

        this.writerSettings = new XmlWriterSettings();
        this.writerSettings.Encoding = Encoding.GetEncoding(factory.CharSet);
        this.contentType = $"{this.factory.MediaType}; charset={this.writerSettings.Encoding.HeaderName}";
    }

    public override string ContentType
    {
        get
        {
            return this.contentType;
        }
    }

    public override string MediaType
    {
        get
        {
            return factory.MediaType;
        }
    }

    public override MessageVersion MessageVersion
    {
        get
        {
            return this.factory.MessageVersion;
        }
    }

    public override Message ReadMessage(ArraySegment<byte> buffer, BufferManager bufferManager, string contentType)
    {
        byte[] msgContents = new byte[buffer.Count];
        Array.Copy(buffer.Array, buffer.Offset, msgContents, 0, msgContents.Length);
        bufferManager.ReturnBuffer(buffer.Array);

        MemoryStream stream = new MemoryStream(msgContents);
        return ReadMessage(stream, int.MaxValue);
    }

    public override Message ReadMessage(Stream stream, int maxSizeOfHeaders, string contentType)
    {
        XmlReader reader = XmlReader.Create(stream);
        return Message.CreateMessage(reader, maxSizeOfHeaders, this.MessageVersion);
    }

    public override ArraySegment<byte> WriteMessage(Message message, int maxMessageSize, BufferManager bufferManager, int messageOffset)
    {
        MemoryStream stream = new MemoryStream();
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);
        message.WriteMessage(writer);
        writer.Close();

        byte[] messageBytes = stream.GetBuffer();
        int messageLength = (int)stream.Position;
        stream.Close();

        int totalLength = messageLength + messageOffset;
        byte[] totalBytes = bufferManager.TakeBuffer(totalLength);
        Array.Copy(messageBytes, 0, totalBytes, messageOffset, messageLength);

        ArraySegment<byte> byteArray = new ArraySegment<byte>(totalBytes, messageOffset, messageLength);
        return byteArray;
    }

    public override void WriteMessage(Message message, Stream stream)
    {
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);
        message.WriteMessage(writer);
        writer.Close();
    }
}
```

Im folgenden Codebeispiel wird gezeigt, wie die Nachrichtenencoder-Factory erstellt wird.

```csharp
public class CustomTextMessageEncoderFactory : MessageEncoderFactory
{
    private MessageEncoder encoder;
    private MessageVersion version;
    private string mediaType;
    private string charSet;

    internal CustomTextMessageEncoderFactory(string mediaType, string charSet,
        MessageVersion version)
    {
        this.version = version;
        this.mediaType = mediaType;
        this.charSet = charSet;
        this.encoder = new CustomTextMessageEncoder(this);
    }

    public override MessageEncoder Encoder
    {
        get
        {
            return this.encoder;
        }
    }

    public override MessageVersion MessageVersion
    {
        get
        {
            return this.version;
        }
    }

    internal string MediaType
    {
        get
        {
            return this.mediaType;
        }
    }

    internal string CharSet
    {
        get
        {
            return this.charSet;
        }
    }
}
```

## <a name="message-encoding-binding-element"></a>Nachrichtencodierungs-Bindungselement

Die Bindungs Elemente ermöglichen die Konfiguration des WCF-Lauf Zeit Stapels. Um den benutzerdefinierten Nachrichten Encoder in einer WCF-Anwendung zu verwenden, ist ein Bindungs Element erforderlich, das die nachrichtenencoderfactory mit den entsprechenden Einstellungen auf der entsprechenden Ebene im Lauf Zeit Stapel erstellt.

`CustomTextMessageBindingElement` wird von der Basisklasse <xref:System.ServiceModel.Channels.BindingElement> abgeleitet und erbt von der <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>-Klasse. Dies ermöglicht anderen WCF-Komponenten, dieses Bindungs Element als Bindungs Element für die Nachrichten Codierung zu erkennen. Die Implementierung von <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> gibt eine Instanz der entsprechenden Nachrichtenencoder-Factory mit entsprechenden Einstellungen zurück.

`CustomTextMessageBindingElement` macht Einstellungen für `MessageVersion`, `ContentType` und `Encoding` durch Eigenschaften verfügbar. Der Encoder unterstützt sowohl die Soap11Addressing- als auch die Soap12Addressing1-Version. Als Standard ist Soap11Addressing1 eingestellt. Der Standardwert von `ContentType` lautet "text/xml". Die `Encoding`-Eigenschaft ermöglicht es Ihnen, den Wert der gewünschten Zeichencodierung festzulegen. Der Beispiel Client und der Dienst verwenden die ISO-8859-1 (Latin1)-Zeichencodierung, die von WCF nicht unterstützt wird <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> .

Im folgenden Code wird gezeigt, wie die Bindung programmgesteuert mithilfe des benutzerdefinierten Textnachrichtenencoders erstellt wird.

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();
bindingElements.Add(textBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
```

## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a>Hinzufügen von Metadaten-Unterstützung zum Nachrichtencodierungs-Bindungselement

Jeder Typ, der aus <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> abgeleitet wird, ist für die Aktualisierung der Version der SOAP-Bindung im für den Dienst generierten WSDL-Dokument verantwortlich. Dies erfolgt durch Implementierung der `ExportEndpoint`-Methode in der <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle und anschließende Änderung des generierten WSDL. In diesem Beispiel verwendet `CustomTextMessageBindingElement` die WSDL-Exportlogik aus `TextMessageEncodingBindingElement`.

Für dieses Beispiel wird die Clientkonfiguration per Hand konfiguriert. Sie können Svcutil.exe nicht zur Generierung der Clientkonfiguration verwenden, da `CustomTextMessageBindingElement` keine Richtlinienassertion zur Beschreibung seines Verhaltens exportiert. Sie sollten im Allgemeinen die <xref:System.ServiceModel.Description.IPolicyExportExtension>-Schnittstelle auf einem benutzerdefinierten Bindungselement implementieren, um eine benutzerdefinierte Richtlinienassertion zu exportieren, die das Verhalten oder die Funktion beschreibt, die vom Bindungselement implementiert wurde. Ein Beispiel für den Export einer Richtlinien Assertion für ein benutzerdefiniertes Bindungs Element finden Sie unter [Transport: UDP](transport-udp.md) Sample.

## <a name="message-encoding-binding-configuration-handler"></a>Bindungskonfigurationshandler zur Nachrichtencodierung

Im vorherigen Abschnitt wird gezeigt, wie der benutzerdefinierte Textnachrichtenencoder programmgesteuert verwendet wird. `CustomTextMessageEncodingBindingSection` implementiert einen Konfigurationshandler, der es Ihnen ermöglicht, die Verwendung eines benutzerdefinierten Textnachrichtenencoders innerhalb einer Konfigurationsdatei festzulegen. Die `CustomTextMessageEncodingBindingSection` -Klasse wird aus der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> -Klasse abgeleitet. Die `BindingElementType`-Eigenschaft informiert das Konfigurationssystem über den Typ des für diesen Abschnitt zu erstellenden Bindungselements.

Alle von `CustomTextMessageBindingElement` definierten Einstellungen werden als Eigenschaften in `CustomTextMessageEncodingBindingSection` verfügbar gemacht. Wenn <xref:System.Configuration.ConfigurationPropertyAttribute> nicht festgelegt wird, hilft dieses Attribut bei der Zuordnung der Konfigurationselementattribute zu den Eigenschaften und Einstellungsstandardwerten. Nachdem die Werte aus der Konfiguration geladen und auf die Eigenschaften des Typs angewendet wurden, wird die <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>-Methode aufgerufen, die die Eigenschaften in eine konkrete Instanz eines Bindungselements konvertiert.

Dieser Konfigurationshandler ordnet die folgende Darstellung in der App.config oder Web.config für den Dienst oder Client zu.

```xml
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />
```

In diesem Beispiel wird die ISO-8859-1-Codierung verwendet.

Um diesen Konfigurationshandler zu verwenden, muss er mithilfe des folgenden Konfigurationselements registriert werden.

```xml
<extensions>
    <bindingElementExtensions>
        <add name="customTextMessageEncoding" type="
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection,
                  CustomTextMessageEncoder" />
    </bindingElementExtensions>
</extensions>
```
