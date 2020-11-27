---
title: Zugreifen auf WCF-Dienste mit einer Windows Store-Client-App
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: ab57adbe0effa2b74541053aa0fcc5b572a6b7fd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293935"
---
# <a name="access-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="b4414-102">Zugreifen auf WCF-Dienste mit einer Windows Store-Client-App</span><span class="sxs-lookup"><span data-stu-id="b4414-102">Access WCF Services with a Windows Store Client App</span></span>

<span data-ttu-id="b4414-103">Mit Windows 8 wird ein neuer Anwendungstyp, die so genannten Windows Store-Anwendungen, eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b4414-103">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="b4414-104">Diese Anwendungen sind für Touchscreenoberflächen konzipiert.</span><span class="sxs-lookup"><span data-stu-id="b4414-104">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="b4414-105">.NET Framework 4.5 ermöglicht Windows Store-Anwendungen das Aufrufen von WCF-Diensten.</span><span class="sxs-lookup"><span data-stu-id="b4414-105">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="b4414-106">WCF-Unterstützung in Windows Store-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b4414-106">WCF Support in Windows Store Applications</span></span>  

 <span data-ttu-id="b4414-107">Innerhalb einer Windows Store-Anwendung ist ein Teilbereich der WCF-Funktionen verfügbar. Ausführliche Informationen finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="b4414-107">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b4414-108">Verwenden Sie die WinRT-Syndication-APIs anstelle der von WCF verfügbar gemachten APIs.</span><span class="sxs-lookup"><span data-stu-id="b4414-108">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="b4414-109">Weitere Informationen finden Sie unter , [WinRT-Syndication-API](xref:Windows.Web.Syndication)</span><span class="sxs-lookup"><span data-stu-id="b4414-109">For more information see, [WinRT Syndication API](xref:Windows.Web.Syndication)</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b4414-110">Das Hinzufügen eines Webdienst Verweises zu einer Windows-Runtime Komponente mithilfe von Dienstverweis hinzufügen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4414-110">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn't supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="b4414-111">Unterstützte Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4414-111">Supported Bindings</span></span>  

 <span data-ttu-id="b4414-112">Die folgenden WCF-Bindungen werden in Windows Store-Anwendungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b4414-112">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.BasicHttpBinding>  
  
2. <xref:System.ServiceModel.NetTcpBinding>  
  
3. <xref:System.ServiceModel.NetHttpBinding>  
  
4. <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="b4414-113">Die folgenden Bindungselemente werden in Windows Store-Anwendungen unterstützt</span><span class="sxs-lookup"><span data-stu-id="b4414-113">The following binding elements are supported in Windows Store Applications</span></span>  
  
1. <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2. <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3. <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4. <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5. <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6. <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7. <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8. <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="b4414-114">Sowohl textbasierte als auch binäre Codierungen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4414-114">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="b4414-115">Alle WCF-Übertragungsmodi werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4414-115">All WCF transfer modes are supported.</span></span> <span data-ttu-id="b4414-116">Weitere Informationen finden Sie unter [Streaming Message Transfer](streaming-message-transfer.md).</span><span class="sxs-lookup"><span data-stu-id="b4414-116">For more information see, [Streaming Message Transfer](streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="b4414-117">Dienstverweis hinzufügen</span><span class="sxs-lookup"><span data-stu-id="b4414-117">Add Service Reference</span></span>  

 <span data-ttu-id="b4414-118">Um einen WCF-Dienst aus einer Windows Store-Anwendung aufzurufen, verwenden Sie die Funktion „Dienstverweis hinzufügen“ in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b4414-118">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="b4414-119">Sie werden bei Verwendung von „Dienstverweis hinzufügen“ innerhalb einer Windows Store-Anwendung einige Funktionsunterschiede bemerken.</span><span class="sxs-lookup"><span data-stu-id="b4414-119">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="b4414-120">Als erstes wird keine Konfigurationsdatei generiert.</span><span class="sxs-lookup"><span data-stu-id="b4414-120">First no configuration file is generated.</span></span> <span data-ttu-id="b4414-121">Da Windows Store-Anwendungen keine Konfigurationsdateien verwenden, müssen sie im Code konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b4414-121">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="b4414-122">Dieser Konfigurationscode befindet sich in der Datei „References.cs“, die durch „Dienstverweis hinzufügen“ generiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4414-122">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="b4414-123">Um diese Datei anzuzeigen, müssen Sie im Projektmappen-Explorer "alle Dateien anzeigen" auswählen.</span><span class="sxs-lookup"><span data-stu-id="b4414-123">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="b4414-124">Die Datei befindet sich innerhalb des Projekts unter dem Knoten „Dienstverweise“ und dann „Reference.svcmap“.</span><span class="sxs-lookup"><span data-stu-id="b4414-124">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="b4414-125">Alle Vorgänge, die für WCF-Dienste in einer Windows Store-Anwendung generiert werden, werden unter Verwendung des taskbasierten asynchronen Musters asynchron implementiert.</span><span class="sxs-lookup"><span data-stu-id="b4414-125">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="b4414-126">Weitere Informationen finden Sie unter [asynchrone Aufgaben: Vereinfachen der asynchronen Programmierung mit Aufgaben](/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span><span class="sxs-lookup"><span data-stu-id="b4414-126">For more information, see [Async Tasks - Simplify Asynchronous Programming with Tasks](/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span></span>  
  
 <span data-ttu-id="b4414-127">Da die Konfiguration nun im Code generiert wird, werden alle Änderungen in der Datei „Reference.cs“ überschrieben, sobald der Dienstverweis aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4414-127">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="b4414-128">Um diese Situation zu vermeiden, wird der Konfigurationscode innerhalb einer partiellen Methode generiert, die Sie in der Clientproxyklasse implementieren können.</span><span class="sxs-lookup"><span data-stu-id="b4414-128">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="b4414-129">Die partielle Methode wird folgendermaßen deklariert:</span><span class="sxs-lookup"><span data-stu-id="b4414-129">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="b4414-130">Sie können diese partielle Methode implementieren und die Bindung oder den Endpunkt in der Clientproxyklasse wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="b4414-130">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="b4414-131">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b4414-131">Serialization</span></span>  

 <span data-ttu-id="b4414-132">Die folgenden Serialisierungsprogramme werden in Windows Store-Anwendungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b4414-132">The following serializers are supported in Windows Store applications:</span></span>  
  
1. <span data-ttu-id="b4414-133">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="b4414-133">DataContractSerializer</span></span>  
  
2. <span data-ttu-id="b4414-134">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="b4414-134">DataContractJsonSerializer</span></span>  
  
3. <span data-ttu-id="b4414-135">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="b4414-135">XmlSerializer</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b4414-136">„XmlDictionaryWriter.Write (DateTime)“ schreibt jetzt das DateTime-Objekt als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b4414-136">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="b4414-137">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b4414-137">Security</span></span>  

<span data-ttu-id="b4414-138">Die folgenden Sicherheitsmodi werden in Windows Store-Anwendungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b4414-138">The following security modes are supported in Windows Store applications:</span></span>
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
<span data-ttu-id="b4414-139">Die folgenden Client Anmelde Informationstypen werden in Windows Store-Anwendungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b4414-139">The following client credential types are supported in Windows Store applications:</span></span>
  
1. <span data-ttu-id="b4414-140">Keine</span><span class="sxs-lookup"><span data-stu-id="b4414-140">None</span></span>  
  
2. <span data-ttu-id="b4414-141">Einfach</span><span class="sxs-lookup"><span data-stu-id="b4414-141">Basic</span></span>  
  
3. <span data-ttu-id="b4414-142">Digest</span><span class="sxs-lookup"><span data-stu-id="b4414-142">Digest</span></span>  
  
4. <span data-ttu-id="b4414-143">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="b4414-143">Negotiate</span></span>  
  
5. <span data-ttu-id="b4414-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="b4414-144">NTLM</span></span>  
  
6. <span data-ttu-id="b4414-145">Windows</span><span class="sxs-lookup"><span data-stu-id="b4414-145">Windows</span></span>  
  
7. <span data-ttu-id="b4414-146">Benutzername (Nachrichtensicherheit)</span><span class="sxs-lookup"><span data-stu-id="b4414-146">Username (Message Security)</span></span>  
  
8. <span data-ttu-id="b4414-147">Windows (Transportsicherheit)</span><span class="sxs-lookup"><span data-stu-id="b4414-147">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="b4414-148">Damit Windows Store-Anwendungen auf standardmäßige Windows-Anmeldeinformationen zugreifen und diese senden können, müssen Sie diese Funktionalität innerhalb der Datei „Package.appmanifest“ aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4414-148">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="b4414-149">Öffnen Sie diese Datei, wählen Sie die Registerkarte Funktionen aus, und wählen Sie "Windows-Standard Anmelde Informationen"</span><span class="sxs-lookup"><span data-stu-id="b4414-149">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="b4414-150">Dadurch kann die Anwendung eine Verbindung mit Intranetressourcen herstellen, die Domänenanmeldeinformationen erfordern.</span><span class="sxs-lookup"><span data-stu-id="b4414-150">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b4414-151">Damit Windows Store-Anwendungen Computer übergreifende Aufrufe durchführen können, müssen Sie eine weitere Funktion mit dem Namen "Home/work Networking" aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4414-151">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="b4414-152">Diese Einstellung befindet sich auch in der Datei "Package. AppManifest" auf der Registerkarte "Funktionen". Aktivieren Sie das Kontrollkästchen Start-und Arbeitsnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="b4414-152">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="b4414-153">Dadurch erhält die Anwendung einen eingehenden und ausgehenden Zugriff auf die Netzwerke der vertrauenswürdigen Orte des Benutzers wie "Home" und "Work".</span><span class="sxs-lookup"><span data-stu-id="b4414-153">This gives your application inbound and outbound access to the networks of the user's trusted places like home and work.</span></span> <span data-ttu-id="b4414-154">Wichtige eingehende Ports sind immer blockiert.</span><span class="sxs-lookup"><span data-stu-id="b4414-154">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="b4414-155">Für den Zugriff auf Internetdienste müssen Sie auch die Internetfunktion (Client) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4414-155">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="b4414-156">Sonstiges</span><span class="sxs-lookup"><span data-stu-id="b4414-156">Misc</span></span>  

 <span data-ttu-id="b4414-157">Die Verwendung der folgenden Klassen wird für Windows Store-Anwendungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b4414-157">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.ChannelFactory>  
  
2. <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3. <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="b4414-158">Definieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="b4414-158">Defining Service Contracts</span></span>  

 <span data-ttu-id="b4414-159">Es wird empfohlen, asynchrone Dienstvorgänge nur mit dem taskbasierten asynchronen Muster zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b4414-159">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="b4414-160">Dadurch wird sichergestellt, dass Windows Store-Anwendungen beim Aufrufen eines Dienstvorgangs reaktionsfähig bleiben.</span><span class="sxs-lookup"><span data-stu-id="b4414-160">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b4414-161">Obwohl keine Ausnahme ausgelöst wird, wenn Sie einen synchronen Vorgang definieren, wird dringend empfohlen, nur asynchrone Vorgänge zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b4414-161">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="b4414-162">Aufrufen von WCF-Diensten aus Windows Store-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b4414-162">Calling WCF Services from Windows Store Applications</span></span>  

 <span data-ttu-id="b4414-163">Wie bereits erwähnt, müssen alle Konfigurationsschritte im Code vorgenommen werden, und zwar in der GetBindingForEndpoint-Methode in der generierten Proxyklasse.</span><span class="sxs-lookup"><span data-stu-id="b4414-163">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="b4414-164">Ein Dienstvorgang wird genauso aufgerufen wie eine taskbasierte asynchrone Methode. Siehe dazu den folgenden Codeausschnitt.</span><span class="sxs-lookup"><span data-stu-id="b4414-164">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="b4414-165">Beachten Sie, dass für die Methode, die den asynchronen Aufruf ausführt, das async-Schlüsselwort und beim Aufrufen der asynchronen Methode das await-Schlüsselwort verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4414-165">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4414-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4414-166">See also</span></span>

- [<span data-ttu-id="b4414-167">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b4414-167">Programming WCF Security</span></span>](programming-wcf-security.md)
- [<span data-ttu-id="b4414-168">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4414-168">Bindings</span></span>](../bindings.md)
