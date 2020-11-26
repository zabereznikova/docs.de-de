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
# <a name="custom-message-encoder-custom-text-encoder"></a><span data-ttu-id="2cd74-104">Benutzerdefinierter Nachrichtenencoder: Benutzerdefinierter Textencoder</span><span class="sxs-lookup"><span data-stu-id="2cd74-104">Custom Message Encoder: Custom Text Encoder</span></span>

<span data-ttu-id="2cd74-105">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Textnachrichten Encoder mithilfe von Windows Communication Foundation (WCF) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2cd74-105">This sample demonstrates how to implement a custom text message encoder using Windows Communication Foundation (WCF).</span></span>

> [!WARNING]
> <span data-ttu-id="2cd74-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2cd74-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2cd74-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2cd74-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2cd74-108">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cd74-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2cd74-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2cd74-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`

<span data-ttu-id="2cd74-110">Der <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> von WCF unterstützt nur die Unicode-Codierungen UTF-8, UTF-16 und Big--Dian.</span><span class="sxs-lookup"><span data-stu-id="2cd74-110">The <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF supports only the UTF-8, UTF-16 and big-endian Unicode encodings.</span></span> <span data-ttu-id="2cd74-111">Der benutzerdefinierte Textnachrichten Encoder in diesem Beispiel unterstützt alle von der Plattform unterstützten Zeichen Codierungen, die möglicherweise für die Interoperabilität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2cd74-111">The custom text message encoder in this sample supports all platform-supported character encodings that may be required for interoperability.</span></span> <span data-ttu-id="2cd74-112">Das Beispiel besteht aus einem Client Konsolenprogramm (. exe), einer von Internetinformationsdienste (IIS) gehosteten Dienst Bibliothek (. dll) und einer Textnachrichten Encoder-Bibliothek (. dll).</span><span class="sxs-lookup"><span data-stu-id="2cd74-112">The sample consists of a client console program (.exe), a service library (.dll) hosted by Internet Information Services (IIS), and a text message encoder library (.dll).</span></span> <span data-ttu-id="2cd74-113">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="2cd74-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="2cd74-114">Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="2cd74-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="2cd74-115">Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und der Dienst antwortet mit dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="2cd74-115">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="2cd74-116">Sowohl Client als auch Dienst verwenden den `CustomTextMessageEncoder` anstelle des Standard-<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2cd74-116">Both client and service uses the `CustomTextMessageEncoder` instead of the default <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span>

<span data-ttu-id="2cd74-117">Die Implementierung für den benutzerdefinierten Encoder besteht aus einer Nachrichtenencoder-Factory, einem Nachrichtenencoder, einem Nachrichtencodierungs-Bindungselement und einem Konfigurationshandler. Es wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2cd74-117">The custom encoder implementation consists of a message encoder factory, a message encoder, a message encoding binding element and a configuration handler, and demonstrates the following:</span></span>

- <span data-ttu-id="2cd74-118">Das Erstellen eines benutzerdefinierten Encoders und einer Encoder-Factory.</span><span class="sxs-lookup"><span data-stu-id="2cd74-118">Building a custom encoder and encoder factory.</span></span>

- <span data-ttu-id="2cd74-119">Das Erstellen eines Bindungselements für einen benutzerdefinierten Encoder.</span><span class="sxs-lookup"><span data-stu-id="2cd74-119">Creating a binding element for a custom encoder.</span></span>

- <span data-ttu-id="2cd74-120">Das Verwenden der benutzerdefinierten Bindungskonfiguration zum Integrieren von benutzerdefinierten Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-120">Using the custom binding configuration for integrating custom binding elements.</span></span>

- <span data-ttu-id="2cd74-121">Das Entwickeln eines benutzerdefinierten Konfigurationshandlers, um die Dateikonfiguration eines benutzerdefinierten Bindungselements zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-121">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2cd74-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="2cd74-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="2cd74-123">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="2cd74-123">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="2cd74-124">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="2cd74-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="2cd74-125">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="2cd74-126">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2cd74-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="message-encoder-factory-and-the-message-encoder"></a><span data-ttu-id="2cd74-127">Nachrichtenencoder-Factory und der Nachrichtenencoder</span><span class="sxs-lookup"><span data-stu-id="2cd74-127">Message Encoder Factory and the Message Encoder</span></span>

<span data-ttu-id="2cd74-128">Wenn der <xref:System.ServiceModel.ServiceHost> oder der Clientkanal geöffnet wird, erstellt die Entwurfszeit-Komponente `CustomTextMessageBindingElement` die `CustomTextMessageEncoderFactory`.</span><span class="sxs-lookup"><span data-stu-id="2cd74-128">When the <xref:System.ServiceModel.ServiceHost> or the client channel is opened, the design time component `CustomTextMessageBindingElement` creates the `CustomTextMessageEncoderFactory`.</span></span> <span data-ttu-id="2cd74-129">Die Factory erstellt den `CustomTextMessageEncoder`.</span><span class="sxs-lookup"><span data-stu-id="2cd74-129">The factory creates the `CustomTextMessageEncoder`.</span></span> <span data-ttu-id="2cd74-130">Der Nachrichtenencoder operiert sowohl im Streamingmodus als auch im Puffermodus.</span><span class="sxs-lookup"><span data-stu-id="2cd74-130">The message encoder operates both in the streaming mode and the buffered mode.</span></span> <span data-ttu-id="2cd74-131">Er verwendet den <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> zum Schreiben bzw. Lesen der Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2cd74-131">It uses the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to read and write the messages respectively.</span></span> <span data-ttu-id="2cd74-132">Im Gegensatz zu den optimierten XML-Readern und-Writern von WCF, die nur UTF-8-, UTF-16-und Big-in-Unicode unterstützen, unterstützen diese Reader und Writer alle Platt Form gestützten Codierungen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-132">As opposed to the optimized XML readers and writers of WCF that support only UTF-8, UTF-16 and big-endian Unicode, these readers and writers support all platform-supported encoding.</span></span>

<span data-ttu-id="2cd74-133">Das folgende Codebeispiel zeigt den benutzerdefinierten Textnachrichtenencoder (CustomTextMessageEncoder).</span><span class="sxs-lookup"><span data-stu-id="2cd74-133">The following code example shows the CustomTextMessageEncoder.</span></span>

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

<span data-ttu-id="2cd74-134">Im folgenden Codebeispiel wird gezeigt, wie die Nachrichtenencoder-Factory erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2cd74-134">The following code example shows how to build the message encoder factory.</span></span>

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

## <a name="message-encoding-binding-element"></a><span data-ttu-id="2cd74-135">Nachrichtencodierungs-Bindungselement</span><span class="sxs-lookup"><span data-stu-id="2cd74-135">Message Encoding Binding Element</span></span>

<span data-ttu-id="2cd74-136">Die Bindungs Elemente ermöglichen die Konfiguration des WCF-Lauf Zeit Stapels.</span><span class="sxs-lookup"><span data-stu-id="2cd74-136">The binding elements allow the configuration of the WCF run-time stack.</span></span> <span data-ttu-id="2cd74-137">Um den benutzerdefinierten Nachrichten Encoder in einer WCF-Anwendung zu verwenden, ist ein Bindungs Element erforderlich, das die nachrichtenencoderfactory mit den entsprechenden Einstellungen auf der entsprechenden Ebene im Lauf Zeit Stapel erstellt.</span><span class="sxs-lookup"><span data-stu-id="2cd74-137">To use the custom message encoder in a WCF application, a binding element is required that creates the message encoder factory with the appropriate settings at the appropriate level in the run-time stack.</span></span>

<span data-ttu-id="2cd74-138">`CustomTextMessageBindingElement` wird von der Basisklasse <xref:System.ServiceModel.Channels.BindingElement> abgeleitet und erbt von der <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2cd74-138">The `CustomTextMessageBindingElement` derives from the <xref:System.ServiceModel.Channels.BindingElement> base class and inherits from the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> class.</span></span> <span data-ttu-id="2cd74-139">Dies ermöglicht anderen WCF-Komponenten, dieses Bindungs Element als Bindungs Element für die Nachrichten Codierung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-139">This allows other WCF components to recognize this binding element as being a message encoding binding element.</span></span> <span data-ttu-id="2cd74-140">Die Implementierung von <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> gibt eine Instanz der entsprechenden Nachrichtenencoder-Factory mit entsprechenden Einstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="2cd74-140">The implementation of <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> returns an instance of the matching message encoder factory with appropriate settings.</span></span>

<span data-ttu-id="2cd74-141">`CustomTextMessageBindingElement` macht Einstellungen für `MessageVersion`, `ContentType` und `Encoding` durch Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cd74-141">The `CustomTextMessageBindingElement` exposes settings for `MessageVersion`, `ContentType`, and `Encoding` through properties.</span></span> <span data-ttu-id="2cd74-142">Der Encoder unterstützt sowohl die Soap11Addressing- als auch die Soap12Addressing1-Version.</span><span class="sxs-lookup"><span data-stu-id="2cd74-142">The encoder supports both Soap11Addressing and Soap12Addressing1 versions.</span></span> <span data-ttu-id="2cd74-143">Als Standard ist Soap11Addressing1 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2cd74-143">The default is Soap11Addressing1.</span></span> <span data-ttu-id="2cd74-144">Der Standardwert von `ContentType` lautet "text/xml".</span><span class="sxs-lookup"><span data-stu-id="2cd74-144">The default value of the `ContentType` is "text/xml".</span></span> <span data-ttu-id="2cd74-145">Die `Encoding`-Eigenschaft ermöglicht es Ihnen, den Wert der gewünschten Zeichencodierung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-145">The `Encoding` property allows you to set the value of the desired character encoding.</span></span> <span data-ttu-id="2cd74-146">Der Beispiel Client und der Dienst verwenden die ISO-8859-1 (Latin1)-Zeichencodierung, die von WCF nicht unterstützt wird <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="2cd74-146">The sample client and service uses the ISO-8859-1 (Latin1) character encoding, which is not supported by the <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF.</span></span>

<span data-ttu-id="2cd74-147">Im folgenden Code wird gezeigt, wie die Bindung programmgesteuert mithilfe des benutzerdefinierten Textnachrichtenencoders erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2cd74-147">The following code shows how to programmatically create the binding using the custom text message encoder.</span></span>

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();
bindingElements.Add(textBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
```

## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a><span data-ttu-id="2cd74-148">Hinzufügen von Metadaten-Unterstützung zum Nachrichtencodierungs-Bindungselement</span><span class="sxs-lookup"><span data-stu-id="2cd74-148">Adding Metadata Support to the Message Encoding Binding Element</span></span>

<span data-ttu-id="2cd74-149">Jeder Typ, der aus <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> abgeleitet wird, ist für die Aktualisierung der Version der SOAP-Bindung im für den Dienst generierten WSDL-Dokument verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="2cd74-149">Any type that derives from <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> is responsible for updating the version of the SOAP binding in the WSDL document generated for the service.</span></span> <span data-ttu-id="2cd74-150">Dies erfolgt durch Implementierung der `ExportEndpoint`-Methode in der <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle und anschließende Änderung des generierten WSDL.</span><span class="sxs-lookup"><span data-stu-id="2cd74-150">This is done by implementing the `ExportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlExportExtension> interface and then modifying the generated WSDL.</span></span> <span data-ttu-id="2cd74-151">In diesem Beispiel verwendet `CustomTextMessageBindingElement` die WSDL-Exportlogik aus `TextMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2cd74-151">In this sample, the `CustomTextMessageBindingElement` uses the WSDL export logic from the `TextMessageEncodingBindingElement`.</span></span>

<span data-ttu-id="2cd74-152">Für dieses Beispiel wird die Clientkonfiguration per Hand konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2cd74-152">For this sample, the client configuration is hand configured.</span></span> <span data-ttu-id="2cd74-153">Sie können Svcutil.exe nicht zur Generierung der Clientkonfiguration verwenden, da `CustomTextMessageBindingElement` keine Richtlinienassertion zur Beschreibung seines Verhaltens exportiert.</span><span class="sxs-lookup"><span data-stu-id="2cd74-153">You cannot use Svcutil.exe to generate the client configuration because the `CustomTextMessageBindingElement` does not export a policy assertion to describe its behavior.</span></span> <span data-ttu-id="2cd74-154">Sie sollten im Allgemeinen die <xref:System.ServiceModel.Description.IPolicyExportExtension>-Schnittstelle auf einem benutzerdefinierten Bindungselement implementieren, um eine benutzerdefinierte Richtlinienassertion zu exportieren, die das Verhalten oder die Funktion beschreibt, die vom Bindungselement implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2cd74-154">You should generally implement the <xref:System.ServiceModel.Description.IPolicyExportExtension> interface on a custom binding element to export a custom policy assertion that describes the behavior or capability implemented by the binding element.</span></span> <span data-ttu-id="2cd74-155">Ein Beispiel für den Export einer Richtlinien Assertion für ein benutzerdefiniertes Bindungs Element finden Sie unter [Transport: UDP](transport-udp.md) Sample.</span><span class="sxs-lookup"><span data-stu-id="2cd74-155">For an example of how to export a policy assertion for a custom binding element, see the [Transport: UDP](transport-udp.md) sample.</span></span>

## <a name="message-encoding-binding-configuration-handler"></a><span data-ttu-id="2cd74-156">Bindungskonfigurationshandler zur Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="2cd74-156">Message Encoding Binding Configuration Handler</span></span>

<span data-ttu-id="2cd74-157">Im vorherigen Abschnitt wird gezeigt, wie der benutzerdefinierte Textnachrichtenencoder programmgesteuert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cd74-157">The previous section shows how to use the custom text message encoder programmatically.</span></span> <span data-ttu-id="2cd74-158">`CustomTextMessageEncodingBindingSection` implementiert einen Konfigurationshandler, der es Ihnen ermöglicht, die Verwendung eines benutzerdefinierten Textnachrichtenencoders innerhalb einer Konfigurationsdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2cd74-158">The `CustomTextMessageEncodingBindingSection` implements a configuration handler that allows you to specify the use of a custom text message encoder within a configuration file.</span></span> <span data-ttu-id="2cd74-159">Die `CustomTextMessageEncodingBindingSection` -Klasse wird aus der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> -Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2cd74-159">The `CustomTextMessageEncodingBindingSection` class derives from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="2cd74-160">Die `BindingElementType`-Eigenschaft informiert das Konfigurationssystem über den Typ des für diesen Abschnitt zu erstellenden Bindungselements.</span><span class="sxs-lookup"><span data-stu-id="2cd74-160">The `BindingElementType` property informs the configuration system of the type of binding element to create for this section.</span></span>

<span data-ttu-id="2cd74-161">Alle von `CustomTextMessageBindingElement` definierten Einstellungen werden als Eigenschaften in `CustomTextMessageEncodingBindingSection` verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="2cd74-161">All of the settings defined by `CustomTextMessageBindingElement` are exposed as the properties in the `CustomTextMessageEncodingBindingSection`.</span></span> <span data-ttu-id="2cd74-162">Wenn <xref:System.Configuration.ConfigurationPropertyAttribute> nicht festgelegt wird, hilft dieses Attribut bei der Zuordnung der Konfigurationselementattribute zu den Eigenschaften und Einstellungsstandardwerten.</span><span class="sxs-lookup"><span data-stu-id="2cd74-162">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if the attribute is not set.</span></span> <span data-ttu-id="2cd74-163">Nachdem die Werte aus der Konfiguration geladen und auf die Eigenschaften des Typs angewendet wurden, wird die <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>-Methode aufgerufen, die die Eigenschaften in eine konkrete Instanz eines Bindungselements konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2cd74-163">After the values from configuration are loaded and applied to the properties of the type, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> method is called, which converts the properties into a concrete instance of a binding element.</span></span>

<span data-ttu-id="2cd74-164">Dieser Konfigurationshandler ordnet die folgende Darstellung in der App.config oder Web.config für den Dienst oder Client zu.</span><span class="sxs-lookup"><span data-stu-id="2cd74-164">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>

```xml
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />
```

<span data-ttu-id="2cd74-165">In diesem Beispiel wird die ISO-8859-1-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cd74-165">The sample uses the ISO-8859-1 encoding.</span></span>

<span data-ttu-id="2cd74-166">Um diesen Konfigurationshandler zu verwenden, muss er mithilfe des folgenden Konfigurationselements registriert werden.</span><span class="sxs-lookup"><span data-stu-id="2cd74-166">To use this configuration handler it must be registered using the following configuration element.</span></span>

```xml
<extensions>
    <bindingElementExtensions>
        <add name="customTextMessageEncoding" type="
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection,
                  CustomTextMessageEncoder" />
    </bindingElementExtensions>
</extensions>
```
