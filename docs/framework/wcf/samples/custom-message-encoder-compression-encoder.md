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
# <a name="custom-message-encoder-compression-encoder"></a><span data-ttu-id="f5069-102">Benutzerdefinierter Nachrichtenencoder: Komprimierungsencoder</span><span class="sxs-lookup"><span data-stu-id="f5069-102">Custom Message Encoder: Compression Encoder</span></span>

<span data-ttu-id="f5069-103">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Encoder mithilfe der Windows Communication Foundation (WCF)-Plattform implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f5069-103">This sample demonstrates how to implement a custom encoder using the Windows Communication Foundation (WCF) platform.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5069-104">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f5069-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5069-105">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f5069-105">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f5069-106">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5069-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5069-107">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f5069-107">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`

## <a name="sample-details"></a><span data-ttu-id="f5069-108">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="f5069-108">Sample Details</span></span>

<span data-ttu-id="f5069-109">Das Beispiel besteht aus einem Clientkonsolenprogramm (.exe), einem selbst gehosteten Dienstkonsolenprogramm (.exe) und einer Komprimierungsnachrichtenencoder-Bibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="f5069-109">This sample consists of a client console program (.exe), a self-hosted service console program (.exe) and a compression message encoder library (.dll).</span></span> <span data-ttu-id="f5069-110">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="f5069-110">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="f5069-111">Der Vertrag wird durch die `ISampleServer`-Schnittstelle definiert, die allgemeine Zeichenfolgen-Echovorgänge (`Echo` und `BigEcho`) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f5069-111">The contract is defined by the `ISampleServer` interface, which exposes basic string echoing operations (`Echo` and `BigEcho`).</span></span> <span data-ttu-id="f5069-112">Der Client stellt synchrone Anforderungen an einen angegebenen Vorgang, und der Dienst antwortet dem Client, indem er die Nachricht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="f5069-112">The client makes synchronous requests to a given operation and the service replies by repeating the message back to the client.</span></span> <span data-ttu-id="f5069-113">Client- und Dienstaktivität sind in den Konsolenfenstern sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f5069-113">Client and service activity is visible in the console windows.</span></span> <span data-ttu-id="f5069-114">Das Beispiel soll zeigen, wie ein benutzerdefinierter Encoder geschrieben wird und wie sich das Komprimieren einer Nachricht auf das Netzwerk auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f5069-114">The intent of this sample is to show how to write a custom encoder and demonstrate the impact of compression of a message on the wire.</span></span> <span data-ttu-id="f5069-115">Sie können dem Komprimierungsnachrichtenencoder eine Instrumentierung zum Berechnen der Nachrichtengröße und/oder der Verarbeitungszeit hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f5069-115">You can add instrumentation to the compression message encoder to calculate message size, processing time, or both.</span></span>

> [!NOTE]
> <span data-ttu-id="f5069-116">In der .NET Framework 4 wurde die automatische Dekomprimierung auf einem WCF-Client aktiviert, wenn der Server eine komprimierte Antwort sendet (erstellt mit einem Algorithmus wie z. b. gzip oder deflate).</span><span class="sxs-lookup"><span data-stu-id="f5069-116">In the .NET Framework 4, automatic decompression has been enabled on a WCF client if the server is sending a compressed response (created with an algorithm such as GZip or Deflate).</span></span> <span data-ttu-id="f5069-117">Bei einem im Internet über Internet Information Server (IIS) gehosteten Dienst kann IIS so konfiguriert werden, dass der Dienst eine komprimierte Antwort sendet.</span><span class="sxs-lookup"><span data-stu-id="f5069-117">If the service is Web-hosted in Internet Information Server (IIS), then IIS can be configured for the service to send a compressed response.</span></span> <span data-ttu-id="f5069-118">Dieses Beispiel kann verwendet werden, wenn die Komprimierung und Dekomprimierung für den Client und für den Dienst durchgeführt werden müssen oder wenn der Dienst selbst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f5069-118">This sample can be used if the requirement is to do compression and decompression on both the client and the service or if the service is self-hosted.</span></span>

<span data-ttu-id="f5069-119">Das Beispiel veranschaulicht, wie ein benutzerdefinierter Nachrichten Encoder erstellt und in eine WCF-Anwendung integriert wird.</span><span class="sxs-lookup"><span data-stu-id="f5069-119">The sample demonstrates how to build and integrate a custom message encoder into a WCF application.</span></span> <span data-ttu-id="f5069-120">Die Bibliothek "GZipEncoder.dll" wird sowohl mit dem Client als auch mit dem Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f5069-120">The library GZipEncoder.dll is deployed with both the client and the service.</span></span> <span data-ttu-id="f5069-121">Das Beispiel zeigt auch, wie sich das Komprimieren von Nachrichten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f5069-121">This sample also demonstrates the impact of compressing messages.</span></span> <span data-ttu-id="f5069-122">Der Code in der "GZipEncoder.dll" zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f5069-122">The code in GZipEncoder.dll demonstrates the following:</span></span>

- <span data-ttu-id="f5069-123">Das Erstellen eines benutzerdefinierten Encoders und einer Encoder-Factory.</span><span class="sxs-lookup"><span data-stu-id="f5069-123">Building a custom encoder and encoder factory.</span></span>

- <span data-ttu-id="f5069-124">Das Entwickeln eines Bindungselements für einen benutzerdefinierten Encoder.</span><span class="sxs-lookup"><span data-stu-id="f5069-124">Developing a binding element for a custom encoder.</span></span>

- <span data-ttu-id="f5069-125">Das Verwenden der benutzerdefinierten Bindungskonfiguration zum Integrieren von benutzerdefinierten Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="f5069-125">Using the custom binding configuration for integrating custom binding elements.</span></span>

- <span data-ttu-id="f5069-126">Das Entwickeln eines benutzerdefinierten Konfigurationshandlers, um die Dateikonfiguration eines benutzerdefinierten Bindungselements zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f5069-126">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>

<span data-ttu-id="f5069-127">Wie schon erwähnt, gibt es mehrere Ebenen, die in einem benutzerdefinierten Encoder implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-127">As indicated previously, there are several layers that are implemented in a custom encoder.</span></span> <span data-ttu-id="f5069-128">Um die Beziehungen zwischen den einzelnen Ebenen besser veranschaulichen zu können, enthält die folgende Liste eine vereinfachte Abfolge der Ereignisse beim Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f5069-128">To better illustrate the relationship between each of these layers, a simplified order of events for service start-up is in the following list:</span></span>

1. <span data-ttu-id="f5069-129">Der Server startet.</span><span class="sxs-lookup"><span data-stu-id="f5069-129">The server starts.</span></span>

2. <span data-ttu-id="f5069-130">Die Konfigurationsinformationen werden gelesen.</span><span class="sxs-lookup"><span data-stu-id="f5069-130">The configuration information is read.</span></span>

    1. <span data-ttu-id="f5069-131">Die Dienstkonfiguration registriert den benutzerdefinierten Konfigurationshandler.</span><span class="sxs-lookup"><span data-stu-id="f5069-131">The service configuration registers the custom configuration handler.</span></span>

    2. <span data-ttu-id="f5069-132">Der Diensthost wird erstellt und geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f5069-132">The service host is created and opened.</span></span>

    3. <span data-ttu-id="f5069-133">Das benutzerdefinierte Konfigurationselement erstellt das benutzerdefinierte Bindungselement und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="f5069-133">The custom configuration element creates and returns the custom binding element.</span></span>

    4. <span data-ttu-id="f5069-134">Das benutzerdefinierte Bindungselement erstellt eine Nachrichtenencoder-Factory und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="f5069-134">The custom binding element creates and returns a message encoder factory.</span></span>

3. <span data-ttu-id="f5069-135">Eine Nachricht wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="f5069-135">A message is received.</span></span>

4. <span data-ttu-id="f5069-136">Die Nachrichtenencoder-Factory gibt einen Nachrichtenencoder zum Lesen der Nachricht und Schreiben der Antwort zurück.</span><span class="sxs-lookup"><span data-stu-id="f5069-136">The message encoder factory returns a message encoder for reading in the message and writing out the response.</span></span>

5. <span data-ttu-id="f5069-137">Die Encoderebene wird in Form einer Klassenfactory implementiert.</span><span class="sxs-lookup"><span data-stu-id="f5069-137">The encoder layer is implemented as a class factory.</span></span> <span data-ttu-id="f5069-138">Nur die Encoderklassenfactory muss für den benutzerdefinierten Encoder öffentlich verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-138">Only the encoder class factory must be publicly exposed for the custom encoder.</span></span> <span data-ttu-id="f5069-139">Das Factoryobjekt wird vom Bindungselement zurückgegeben, wenn das <xref:System.ServiceModel.ServiceHost>-Objekt oder das <xref:System.ServiceModel.ChannelFactory%601>-Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5069-139">The factory object is returned by the binding element when the <xref:System.ServiceModel.ServiceHost> or <xref:System.ServiceModel.ChannelFactory%601> object is created.</span></span> <span data-ttu-id="f5069-140">Nachrichtenencoder können im Puffermodus oder im Streamingmodus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f5069-140">Message encoders can operate in a buffered or streaming mode.</span></span> <span data-ttu-id="f5069-141">In diesem Beispiel werden sowohl der Puffermodus als auch der Streamingmodus veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f5069-141">This sample demonstrates both buffered mode and streaming mode.</span></span>

<span data-ttu-id="f5069-142">Für jeden Modus gibt es eine zugehörige `ReadMessage`- und `WriteMessage`-Methode in der abstrakten `MessageEncoder`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f5069-142">For each mode there is an accompanying `ReadMessage` and `WriteMessage` method on the abstract `MessageEncoder` class.</span></span> <span data-ttu-id="f5069-143">In diesen Methoden findet der größte Teil der Codierungsarbeit statt.</span><span class="sxs-lookup"><span data-stu-id="f5069-143">A majority of the encoding work takes place in these methods.</span></span> <span data-ttu-id="f5069-144">Das Beispiel schließt die vorhandenen Text- und Binärnachrichtenencoder ein.</span><span class="sxs-lookup"><span data-stu-id="f5069-144">The sample wraps the existing text and binary message encoders.</span></span> <span data-ttu-id="f5069-145">Auf diese Weise kann es das Lesen und Schreiben der Übertragungsdarstellung von Nachrichten an den inneren Encoder delegieren, und die Ergebnisse können vom Komprimierungsencoder komprimiert oder dekomprimiert werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-145">This allows the sample to delegate the reading and writing of the wire representation of messages to the inner encoder and allows the compression encoder to compress or decompress the results.</span></span> <span data-ttu-id="f5069-146">Da keine Pipeline für die Nachrichten Codierung vorhanden ist, ist dies das einzige Modell für die Verwendung mehrerer Encoder in WCF.</span><span class="sxs-lookup"><span data-stu-id="f5069-146">Because there is no pipeline for message encoding, this is the only model for using multiple encoders in WCF.</span></span> <span data-ttu-id="f5069-147">Nachdem die Nachricht dekomprimiert wurde, wird die resultierende Nachricht an den Stapel weitergegeben, um vom Kanalstapel verarbeitet zu werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-147">Once the message has been decompressed, the resulting message is passed up the stack for the channel stack to handle.</span></span> <span data-ttu-id="f5069-148">Während der Komprimierung wird die resultierende komprimierte Nachricht direkt in den bereitgestellten Stream geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f5069-148">During compression, the resulting compressed message is written directly to the stream provided.</span></span>

<span data-ttu-id="f5069-149">In diesem Beispiel werden Hilfsmethoden (`CompressBuffer` und `DecompressBuffer`) verwendet, um die Konvertierung von Puffern in Streams zum Verwenden der `GZipStream`-Klasse auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f5069-149">This sample uses helper methods (`CompressBuffer` and `DecompressBuffer`) to perform conversion from buffers to streams to use the `GZipStream` class.</span></span>

<span data-ttu-id="f5069-150">Die gepufferten `ReadMessage`-Klasse und `WriteMessage`-Klasse machen von der `BufferManager`-Klasse Gebrauch.</span><span class="sxs-lookup"><span data-stu-id="f5069-150">The buffered `ReadMessage` and `WriteMessage` classes make use of the `BufferManager` class.</span></span> <span data-ttu-id="f5069-151">Auf den Encoder kann nur über die Encoder-Factory zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-151">The encoder is accessible only through the encoder factory.</span></span> <span data-ttu-id="f5069-152">Die abstrakte `MessageEncoderFactory`-Klasse bietet zum Zugreifen auf den aktuellen Encoder eine Eigenschaft namens `Encoder` und zum Erstellen eines Encoders, der Sitzungen unterstützt, eine Methode namens `CreateSessionEncoder`.</span><span class="sxs-lookup"><span data-stu-id="f5069-152">The abstract `MessageEncoderFactory` class provides a property named `Encoder` for accessing the current encoder and a method named `CreateSessionEncoder` for creating an encoder that supports sessions.</span></span> <span data-ttu-id="f5069-153">Ein solcher Encoder kann in Situationen verwendet werden, in denen der Kanal Sitzungen unterstützt, geordnet und zuverlässig ist.</span><span class="sxs-lookup"><span data-stu-id="f5069-153">Such an encoder can be used in the scenario where the channel supports sessions, is ordered and is reliable.</span></span> <span data-ttu-id="f5069-154">In diesem Szenario ist in jeder Sitzung, in der Daten zur Übertragung geschrieben werden, eine Optimierung möglich.</span><span class="sxs-lookup"><span data-stu-id="f5069-154">This scenario allows for optimization in each session of the data written to the wire.</span></span> <span data-ttu-id="f5069-155">Wenn dies nicht erwünscht ist, sollte die Basismethode nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-155">If this is not desired, the base method should not be overloaded.</span></span> <span data-ttu-id="f5069-156">Die `Encoder`-Eigenschaft bietet einen Mechanismus zum Zugreifen auf den sitzungslosen Encoder, und der Wert der Eigenschaft wird von der Standardimplementierung der `CreateSessionEncoder`-Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5069-156">The `Encoder` property provides a mechanism for accessing the session-less encoder and the default implementation of the `CreateSessionEncoder` method returns the value of the property.</span></span> <span data-ttu-id="f5069-157">Da das Beispiel einen vorhandenen Encoder einschließt, um Komprimierung zu ermöglichen, akzeptiert die `MessageEncoderFactory`-Implementierung eine `MessageEncoderFactory`, die die innere Encoder-Factory darstellt.</span><span class="sxs-lookup"><span data-stu-id="f5069-157">Because the sample wraps an existing encoder to provide compression, the `MessageEncoderFactory` implementation accepts a `MessageEncoderFactory` that represents the inner encoder factory.</span></span>

<span data-ttu-id="f5069-158">Nun, da der Encoder und die Encoderfactory definiert sind, können Sie mit einem WCF-Client und-Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-158">Now that the encoder and encoder factory are defined, they can be used with a WCF client and service.</span></span> <span data-ttu-id="f5069-159">Allerdings müssen diese Encoder dem Kanalstapel hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-159">However, these encoders must be added to the channel stack.</span></span> <span data-ttu-id="f5069-160">Zum manuellen Hinzufügen dieser Encoder-Factory können Sie Klassen von der <xref:System.ServiceModel.ServiceHost>-Klasse und der <xref:System.ServiceModel.ChannelFactory%601>-Klasse ableiten und die `OnInitialize`-Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f5069-160">You can derive classes from the <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.ChannelFactory%601> classes and override the `OnInitialize` methods to add this encoder factory manually.</span></span> <span data-ttu-id="f5069-161">Sie können die Encoder-Factory auch über ein benutzerdefiniertes Bindungselement verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="f5069-161">You can also expose the encoder factory through a custom binding element.</span></span>

<span data-ttu-id="f5069-162">Zum Erstellen eines neuen benutzerdefinierten Bindungselements leiten Sie eine Klasse von der <xref:System.ServiceModel.Channels.BindingElement>-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="f5069-162">To create a new custom binding element, derive a class from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="f5069-163">Es gibt jedoch mehrere Typen von Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="f5069-163">There are, however, several types of binding elements.</span></span> <span data-ttu-id="f5069-164">Um sicherzustellen, dass das benutzerdefinierte Bindungselement als ein Nachrichtencodierungs-Bindungselement erkannt wird, müssen Sie auch das <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> implementieren.</span><span class="sxs-lookup"><span data-stu-id="f5069-164">To ensure that the custom binding element is recognized as a message encoding binding element, you also must implement the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span></span> <span data-ttu-id="f5069-165">Das <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> macht eine Methode zum Erstellen einer neuen Nachrichtenencoder-Factory verfügbar (`CreateMessageEncoderFactory`), die so implementiert ist, dass sie eine Instanz der übereinstimmenden Nachrichtenencoder-Factory zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f5069-165">The <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> exposes a method for creating a new message encoder factory (`CreateMessageEncoderFactory`), which is implemented to return an instance of the matching message encoder factory.</span></span> <span data-ttu-id="f5069-166">Außerdem besitzt das <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> eine Eigenschaft zum Angeben der Adressierungsversion.</span><span class="sxs-lookup"><span data-stu-id="f5069-166">Additionally, the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> has a property to indicate the addressing version.</span></span> <span data-ttu-id="f5069-167">Da dieses Beispiel die vorhandenen Encoder einschließt, schließt die Implementierung des Beispiels auch die vorhandenen Encoderbindungselemente ein und nimmt ein inneres Encoderbindungselement als Parameter für den Konstruktor entgegen, das es über eine Eigenschaft verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f5069-167">Because this sample wraps the existing encoders, the sample implementation also wraps the existing encoder binding elements and takes an inner encoder binding element as a parameter to the constructor and exposes it through a property.</span></span> <span data-ttu-id="f5069-168">Das folgende Codebeispiel zeigt die Implementierung der `GZipMessageEncodingBindingElement`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f5069-168">The following sample code shows the implementation of the `GZipMessageEncodingBindingElement` class.</span></span>

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

<span data-ttu-id="f5069-169">Beachten Sie, dass die `GZipMessageEncodingBindingElement`-Klasse die `IPolicyExportExtension`-Schnittstelle implementiert, sodass dieses Bindungselement als Richtlinie in Metadaten exportiert werden kann, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5069-169">Note that `GZipMessageEncodingBindingElement` class implements the `IPolicyExportExtension` interface, so that this binding element can be exported as a policy in metadata, as shown in the following example.</span></span>

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

<span data-ttu-id="f5069-170">Die `GZipMessageEncodingBindingElementImporter`-Klasse implementiert die `IPolicyImportExtension`-Schnittstelle, diese Klasse importiert die Richtlinie für `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="f5069-170">The `GZipMessageEncodingBindingElementImporter` class implements the `IPolicyImportExtension` interface, this class imports policy for `GZipMessageEncodingBindingElement`.</span></span> <span data-ttu-id="f5069-171">Zum Importieren von Richtlinien in die Konfigurationsdatei kann das Tool "Svcutil.exe" verwendet werden. Zum Umgang mit `GZipMessageEncodingBindingElement` sollte der "Svcutil.exe.config" Folgendes hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-171">Svcutil.exe tool can be used to import policies to the configuration file, to handle `GZipMessageEncodingBindingElement`, the following should be added to Svcutil.exe.config.</span></span>

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

<span data-ttu-id="f5069-172">Nachdem nun ein passendes Bindungselement für den Komprimierungsencoder vorhanden ist, kann dieser programmgesteuert als Hook in den Dienst oder Client eingesetzt werden, indem ein neues benutzerdefiniertes Bindungsobjekt erstellt und dem benutzerdefinierten Bindungselement hinzugefügt wird, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5069-172">Now that there is a matching binding element for the compression encoder, it can be programmatically hooked into the service or client by constructing a new custom binding object and adding the custom binding element to it, as shown in the following sample code.</span></span>

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

<span data-ttu-id="f5069-173">Obwohl dies für die meisten Benutzerszenarios ausreichen sollte, ist die Unterstützung einer Dateikonfiguration wichtig, wenn der Dienst im Web gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f5069-173">While this may be sufficient for the majority of user scenarios, supporting a file configuration is critical if a service is to be Web-hosted.</span></span> <span data-ttu-id="f5069-174">Zur Unterstützung des Webhostszenarios müssen Sie einen benutzerdefinierten Konfigurationshandler erstellen, damit ein benutzerdefiniertes Bindungselement in einer Datei konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f5069-174">To support the Web-hosted scenario, you must develop a custom configuration handler to allow a custom binding element to be configurable in a file.</span></span>

<span data-ttu-id="f5069-175">Sie können einen Konfigurations Handler für das Bindungs Element zusätzlich zum Konfigurationssystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5069-175">You can build a configuration handler for the binding element on top of the configuration system.</span></span> <span data-ttu-id="f5069-176">Der Konfigurationshandler für das Bindungselement muss von der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>-Klasse abgeleitet sein.</span><span class="sxs-lookup"><span data-stu-id="f5069-176">The configuration handler for the binding element must derive from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="f5069-177">Der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType> informiert das Konfigurationssystem über den Typ des Bindungs Elements, das für diesen Abschnitt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f5069-177">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType> informs the configuration system of the type of binding element to create for this section.</span></span> <span data-ttu-id="f5069-178">Sämtliche Aspekte des `BindingElement`, die festgelegt werden können, sollten in der abgeleiteten <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>-Klasse als Eigenschaften zugänglich gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f5069-178">All aspects of the `BindingElement` that can be set should be exposed as properties in the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class.</span></span> <span data-ttu-id="f5069-179">Der unter <xref:System.Configuration.ConfigurationPropertyAttribute> stützt das Mapping der Konfigurationselement Attribute zu den Eigenschaften und das Festlegen von Standardwerten, wenn Attribute fehlen.</span><span class="sxs-lookup"><span data-stu-id="f5069-179">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if attributes are missing.</span></span> <span data-ttu-id="f5069-180">Nachdem die Werte aus der Konfiguration geladen und auf die Eigenschaften angewendet wurden, wird die <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType>-Methode aufgerufen, die die Eigenschaften in eine konkrete Instanz eines Bindungselements konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f5069-180">After the values from configuration are loaded and applied to the properties, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType> method is called, which converts the properties into a concrete instance of a binding element.</span></span> <span data-ttu-id="f5069-181">Die- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> Methode wird verwendet, um die Eigenschaften in der <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> abgeleiteten Klasse in die Werte zu konvertieren, die für das neu erstellte Bindungs Element festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5069-181">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> method is used to convert the properties on the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class into the values to be set on the newly created binding element.</span></span>

<span data-ttu-id="f5069-182">Das folgenden Codebeispiel zeigt die Implementierung des `GZipMessageEncodingElement`.</span><span class="sxs-lookup"><span data-stu-id="f5069-182">The following sample code shows the implementation of the `GZipMessageEncodingElement`.</span></span>

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

<span data-ttu-id="f5069-183">Dieser Konfigurationshandler ordnet die folgende Darstellung in der App.config oder Web.config für den Dienst oder Client zu.</span><span class="sxs-lookup"><span data-stu-id="f5069-183">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>

```xml
<gzipMessageEncoding innerMessageEncoding="textMessageEncoding" />
```

<span data-ttu-id="f5069-184">Um diesen Konfigurations Handler zu verwenden, muss er innerhalb des- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Elements registriert werden, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5069-184">To use this configuration handler, it must be registered within the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, as shown in the following sample configuration.</span></span>

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

<span data-ttu-id="f5069-185">Beim Ausführen des Servers werden die Vorgangsanforderungen und -antworten im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5069-185">When you run the server, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="f5069-186">Drücken Sie im Fenster die EINGABETASTE, um den Server zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f5069-186">Press ENTER in the window to shut down the server.</span></span>

```console
Press Enter key to Exit.

        Server Echo(string input) called:
        Client message: Simple hello

        Server BigEcho(string[] input) called:
        64 client messages
```

<span data-ttu-id="f5069-187">Beim Ausführen des Clients werden die Vorgangsanforderungen und -antworten im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5069-187">When you run the client, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="f5069-188">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f5069-188">Press ENTER in the client window to shut down the client.</span></span>

```console
Calling Echo(string):
Server responds: Simple hello Simple hello

Calling BigEcho(string[]):
Server responds: Hello 0

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f5069-189">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f5069-189">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f5069-190">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f5069-190">Install ASP.NET 4.0 using the following command:</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="f5069-191">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f5069-191">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="f5069-192">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5069-192">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="f5069-193">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5069-193">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5069-194">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f5069-194">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5069-195">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f5069-195">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f5069-196">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5069-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5069-197">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f5069-197">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`
