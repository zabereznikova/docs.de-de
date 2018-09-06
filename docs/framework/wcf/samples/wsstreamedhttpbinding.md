---
title: WSStreamedHttpBinding
ms.date: 03/30/2017
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
ms.openlocfilehash: d2111639266612183630231dbd51be55ef9c1ee4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779335"
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="492a8-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="492a8-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="492a8-103">Das Beispiel veranschaulicht, wie eine Bindung erstellt wird, die Streamingszenarios unterstützt, wenn HTTP-Transport verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="492a8-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="492a8-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="492a8-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="492a8-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="492a8-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="492a8-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="492a8-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="492a8-107">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="492a8-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="492a8-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="492a8-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="492a8-109">Zum Erstellen und Konfigurieren einer neuen Standardbindung müssen folgende Schritte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="492a8-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="492a8-110">Erstellen einer neuen Standardbindung</span><span class="sxs-lookup"><span data-stu-id="492a8-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="492a8-111">Die standardbindungen in Windows Communication Foundation (WCF) wie z. B. BasicHttpBinding und NetTcpBinding, konfigurieren die zugrunde liegenden Transporte und Kanalstapel für bestimmte Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="492a8-111">The standard bindings in Windows Communication Foundation (WCF) such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="492a8-112">In diesem Beispiel konfiguriert `WSStreamedHttpBinding` den Kanalstapel, um Streaming zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="492a8-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="492a8-113">Standardmäßig werden WS-Sicherheit und zuverlässiges Messaging nicht zum Kanalstapel hinzugefügt, da beide Funktionen nicht vom Streaming unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="492a8-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="492a8-114">Die neue Bindung wird in die Klasse `WSStreamedHttpBinding` implementiert, die von <xref:System.ServiceModel.Channels.Binding> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="492a8-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="492a8-115">`WSStreamedHttpBinding` enthält die folgenden Bindungselemente: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> und <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="492a8-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="492a8-116">Die Klasse stellt eine `CreateBindingElements()`-Methode bereit, um den resultierenden Bindungsstapel zu konfigurieren, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="492a8-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
    ```  
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
  
2.  <span data-ttu-id="492a8-117">Hinzufügen von Konfigurationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="492a8-117">Add configuration support</span></span>  
  
     <span data-ttu-id="492a8-118">Im Beispiel werden zwei weitere Klassen – `WSStreamedHttpBindingConfigurationElement` und `WSStreamedHttpBindingSection` – implementiert, um den Transport durch Konfiguration verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="492a8-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="492a8-119">Die Klasse `WSStreamedHttpBindingSection` ist eine <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> , verfügbar macht `WSStreamedHttpBinding` für das WCF-Konfigurationssystem.</span><span class="sxs-lookup"><span data-stu-id="492a8-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the WCF configuration system.</span></span> <span data-ttu-id="492a8-120">Der Großteil der Implementierung wird dem `WSStreamedHttpBindingConfigurationElement` übertragen, das von <xref:System.ServiceModel.Configuration.StandardBindingElement> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="492a8-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="492a8-121">Die Klasse `WSStreamedHttpBindingConfigurationElement` verfügt über Eigenschaften, die mit den Eigenschaften von `WSStreamedHttpBinding` übereinstimmen, sowie über Funktionen, um jedes Konfigurationselement einer Bindung zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="492a8-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="492a8-122">Registrieren Sie den Handler mit dem Konfigurationssystem, indem Sie den folgenden Abschnitt zur Konfigurationsdatei des Diensts hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="492a8-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
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
  
     <span data-ttu-id="492a8-123">Auf den Handler kann vom serviceModel-Konfigurationsabschnitt aus verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="492a8-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="492a8-124">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="492a8-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="492a8-125">Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="492a8-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="492a8-126">Stellen Sie sicher, dass Sie die aufgeführten Schritte ausgeführt haben [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="492a8-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="492a8-127">Stellen Sie sicher, dass Sie ausgeführt haben die [Installationsanweisungen zu Serverzertifikaten (Internet Information Services, IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="492a8-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="492a8-128">Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="492a8-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="492a8-129">Um das Beispiel in einer computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="492a8-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="492a8-130">Wenn das Clientfenster angezeigt wird, geben Sie "Sample.txt" ein.</span><span class="sxs-lookup"><span data-stu-id="492a8-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="492a8-131">In Ihrem Verzeichnis sollte sich eine Datei "Copy of Sample.txt" befinden.</span><span class="sxs-lookup"><span data-stu-id="492a8-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="492a8-132">Der WSStreamedHttpBinding-Beispieldienst</span><span class="sxs-lookup"><span data-stu-id="492a8-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="492a8-133">Der Beispieldienst, der die `WSStreamedHttpBinding` verwendet, befindet sich im Dienstunterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="492a8-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="492a8-134">Die Implementierung von `OperationContract` verwendet einen `MemoryStream`, um zuerst alle Daten vom eingehenden Stream abzurufen, bevor der `MemoryStream` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="492a8-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="492a8-135">Der Beispieldienst wird von Internetinformationsdiensten (IIS) gehostet.</span><span class="sxs-lookup"><span data-stu-id="492a8-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
```  
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
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="492a8-136">Der WSStreamedHttpBinding-Beispielclient</span><span class="sxs-lookup"><span data-stu-id="492a8-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="492a8-137">Der Client, der für die Interaktion mit dem Dienst über `WSStreamedHttpBinding` verwendet wird, befindet sich im Clientunterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="492a8-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="492a8-138">Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, eine sicherheitswarnung angezeigt, wenn Sie versuchen, eine HTTPS-Adresse in Ihrem Browser zugreifen, z.B. https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="492a8-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="492a8-139">Damit den WCF-Client mit einem vorhandenen Testzertifikat arbeiten kann, wurde an den Client, um die sicherheitswarnung zu unterdrücken, zusätzlicher Code hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="492a8-139">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="492a8-140">Der Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="492a8-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a><span data-ttu-id="492a8-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="492a8-141">See Also</span></span>
