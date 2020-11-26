---
title: 'Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF REST-Programmiermodells akzeptiert'
ms.date: 03/30/2017
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
ms.openlocfilehash: 9c9899705861cc1cf2cda2559c30a0a60d8cc635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237832"
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a><span data-ttu-id="e44f3-102">Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF REST-Programmiermodells akzeptiert</span><span class="sxs-lookup"><span data-stu-id="e44f3-102">How to: Create a Service That Accepts Arbitrary Data using the WCF REST Programming Model</span></span>

<span data-ttu-id="e44f3-103">Unter bestimmten Voraussetzungen benötigen Entwickler umfassende Steuerungsmöglichkeiten für die Rückgabe der Daten durch einen Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="e44f3-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="e44f3-104">Dies ist der Fall, wenn ein Dienst Vorgang Daten in einem Format zurückgeben muss, das von bywcf nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e44f3-104">This is the case when a service operation must return data in a format not supported byWCF.</span></span> <span data-ttu-id="e44f3-105">In diesem Thema wird die Verwendung des WCF Rest-Programmiermodells erläutert, um einen Dienst zu erstellen, der beliebige Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="e44f3-105">This topic discusses using the WCF REST Programming Model to create a service that receives arbitrary data.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="e44f3-106">So implementieren Sie den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="e44f3-106">To implement the service contract</span></span>  
  
1. <span data-ttu-id="e44f3-107">Definieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="e44f3-107">Define the service contract.</span></span> <span data-ttu-id="e44f3-108">Der Vorgang, der die beliebigen Daten empfängt, muss über einen Parameter des Typs <xref:System.IO.Stream> verfügen.</span><span class="sxs-lookup"><span data-stu-id="e44f3-108">The operation that receives the arbitrary data must have a parameter of type <xref:System.IO.Stream>.</span></span> <span data-ttu-id="e44f3-109">Außerdem muss es sich bei diesem Parameter um den einzigen Parameter handeln, der im Text der Anforderung übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e44f3-109">In addition, this parameter must be the only parameter passed in the body of the request.</span></span> <span data-ttu-id="e44f3-110">Der in diesem Beispiel beschriebene Vorgang nimmt auch einen Dateinamenparameter an.</span><span class="sxs-lookup"><span data-stu-id="e44f3-110">The operation described in this example also takes a filename parameter.</span></span> <span data-ttu-id="e44f3-111">Dieser Parameter wird innerhalb der URL der Anforderung übergeben.</span><span class="sxs-lookup"><span data-stu-id="e44f3-111">This parameter is passed within the URL of the request.</span></span> <span data-ttu-id="e44f3-112">Geben Sie zum Festlegen, dass ein Parameter innerhalb der URL übergeben wird, im <xref:System.UriTemplate> eine <xref:System.ServiceModel.Web.WebInvokeAttribute> an.</span><span class="sxs-lookup"><span data-stu-id="e44f3-112">You can specify that a parameter is passed within the URL by specifying a <xref:System.UriTemplate> in the <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="e44f3-113">In diesem Fall endet der URI, der zum Abrufen dieser Methode verwendet wird, mit "UploadFile/some-filename".</span><span class="sxs-lookup"><span data-stu-id="e44f3-113">In this case the URI used to call this method ends in "UploadFile/Some-Filename".</span></span> <span data-ttu-id="e44f3-114">Der "{filename}"-Teil der URI-Vorlage gibt an, dass der filename-Parameter für den Vorgang innerhalb des URI übergeben wird, der zum Aufrufen des Vorgangs verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e44f3-114">The "{filename}" portion of the URI template specifies that the filename parameter for the operation is passed within the URI used to call the operation.</span></span>  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2. <span data-ttu-id="e44f3-115">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="e44f3-115">Implement the service contract.</span></span> <span data-ttu-id="e44f3-116">Der Vertrag verfügt über nur eine Methode (`UploadFile`), die in einem Stream eine Datei mit beliebigen Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="e44f3-116">The contract has only one method, `UploadFile` that receives a file of arbitrary data in a stream.</span></span> <span data-ttu-id="e44f3-117">Der Vorgang liest den Stream, erfasst die Menge der gelesenen Bytes und zeigt anschließend den Dateinamen und die Menge der gelesenen Bytes an.</span><span class="sxs-lookup"><span data-stu-id="e44f3-117">The operation reads the stream counting the number of bytes read and then displays the filename and the number of bytes read.</span></span>  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a><span data-ttu-id="e44f3-118">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="e44f3-118">To host the service</span></span>  
  
1. <span data-ttu-id="e44f3-119">Erstellen Sie eine Konsolenanwendung, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="e44f3-119">Create a console application to host the service.</span></span>  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2. <span data-ttu-id="e44f3-120">Erstellen Sie eine Variable, um die Basisadresse für den Dienst innerhalb der `Main`-Methode zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e44f3-120">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="e44f3-121">Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz für den Dienst, um die Dienstklasse und die Basisadresse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e44f3-121">Create a <xref:System.ServiceModel.ServiceHost> instance for the service that specifies the service class and the base address.</span></span>  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="e44f3-122">Fügen Sie einen Endpunkt hinzu, durch den der Vertrag, die <xref:System.ServiceModel.WebHttpBinding> sowie das <xref:System.ServiceModel.Description.WebHttpBehavior> angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e44f3-122">Add an endpoint that specifies the contract, <xref:System.ServiceModel.WebHttpBinding>, and <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="e44f3-123">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="e44f3-123">Open the service host.</span></span> <span data-ttu-id="e44f3-124">Der Dienst ist nun zum Empfangen von Anforderungen bereit.</span><span class="sxs-lookup"><span data-stu-id="e44f3-124">The service is now ready to receive requests.</span></span>  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a><span data-ttu-id="e44f3-125">So rufen Sie den Dienst programmgesteuert auf</span><span class="sxs-lookup"><span data-stu-id="e44f3-125">To call the service programmatically</span></span>  
  
1. <span data-ttu-id="e44f3-126">Erstellen Sie eine <xref:System.Net.HttpWebRequest> mit dem URI, mit dem der Dienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e44f3-126">Create a <xref:System.Net.HttpWebRequest> with the URI used to call the service.</span></span> <span data-ttu-id="e44f3-127">In diesem Code wird die Basisadresse mit `"/UploadFile/Text"` kombiniert.</span><span class="sxs-lookup"><span data-stu-id="e44f3-127">In this code, the base address is combined with `"/UploadFile/Text"`.</span></span> <span data-ttu-id="e44f3-128">Der `"UploadFile"`-Teil des URI gibt den aufzurufenden Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="e44f3-128">The `"UploadFile"` portion of the URI specifies the operation to call.</span></span> <span data-ttu-id="e44f3-129">Der `"Test.txt"`-Teil des URI gibt den Dateinamenparameter an, der an den `UploadFile`-Vorgang übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e44f3-129">The `"Test.txt"` portion of the URI specifies the filename parameter to pass to the `UploadFile` operation.</span></span> <span data-ttu-id="e44f3-130">Beide Elemente werden der <xref:System.UriTemplate> zugeordnet, die auf den Vorgangsvertrag angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e44f3-130">Both of these items map to the <xref:System.UriTemplate> applied to the operation contract.</span></span>  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2. <span data-ttu-id="e44f3-131">Legen Sie die <xref:System.Net.HttpWebRequest.Method%2A>-Eigenschaft der <xref:System.Net.HttpWebRequest> auf `POST` und die <xref:System.Net.HttpWebRequest.ContentType%2A>-Eigenschaft auf `"text/plain"` fest.</span><span class="sxs-lookup"><span data-stu-id="e44f3-131">Set the <xref:System.Net.HttpWebRequest.Method%2A> property of the <xref:System.Net.HttpWebRequest> to `POST` and the <xref:System.Net.HttpWebRequest.ContentType%2A> property to `"text/plain"`.</span></span> <span data-ttu-id="e44f3-132">Dadurch wird dem Dienst mitgeteilt, dass der Code Daten sendet und diese Daten im Nur-Text-Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="e44f3-132">This tells the service that the code is sending data and that data is in plain text.</span></span>  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3. <span data-ttu-id="e44f3-133">Rufen Sie <xref:System.Net.HttpWebRequest.GetRequestStream%2A> auf, um den Anforderungsstream abzurufen, erstellen Sie die zu sendenden Daten, schreiben Sie die Daten in den Anforderungsstream, und schließen Sie anschließend den Stream.</span><span class="sxs-lookup"><span data-stu-id="e44f3-133">Call <xref:System.Net.HttpWebRequest.GetRequestStream%2A> to get the request stream, create the data to send, write that data to the request stream, and close the stream.</span></span>  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4. <span data-ttu-id="e44f3-134">Rufen Sie die Antwort des Diensts ab, indem Sie <xref:System.Net.HttpWebRequest.GetResponse%2A> aufrufen, und zeigen Sie die Antwortdaten an die Konsole an.</span><span class="sxs-lookup"><span data-stu-id="e44f3-134">Get the response from the service by calling <xref:System.Net.HttpWebRequest.GetResponse%2A> and display the response data to the console.</span></span>  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5. <span data-ttu-id="e44f3-135">Schließen Sie den Diensthost.</span><span class="sxs-lookup"><span data-stu-id="e44f3-135">Close the service host.</span></span>  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="e44f3-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e44f3-136">Example</span></span>  

 <span data-ttu-id="e44f3-137">Im Folgenden finden Sie eine vollständige Liste des Codes für dieses Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e44f3-137">The following is a complete listing of the code for this example.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e44f3-138">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e44f3-138">Compiling the Code</span></span>  
  
- <span data-ttu-id="e44f3-139">Verweisen Sie beim Kompilieren des Codes auf "System.ServiceModel.dll" und "System.ServiceModel.Web.dll".</span><span class="sxs-lookup"><span data-stu-id="e44f3-139">When compiling the code reference System.ServiceModel.dll and System.ServiceModel.Web.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e44f3-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e44f3-140">See also</span></span>

- [<span data-ttu-id="e44f3-141">UriTemplate und UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="e44f3-141">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)
- [<span data-ttu-id="e44f3-142">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="e44f3-142">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="e44f3-143">Überblick über WCF-Web-HTTP-Programmiermodelle</span><span class="sxs-lookup"><span data-stu-id="e44f3-143">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
