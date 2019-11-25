---
title: 'Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF-Web-HTTP-Programmiermodells zurückgibt'
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: 41d9f0e53401bcd6b57b04a38e76af5ddb9fb4cc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976104"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="063a8-102">Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF-Web-HTTP-Programmiermodells zurückgibt</span><span class="sxs-lookup"><span data-stu-id="063a8-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="063a8-103">Unter bestimmten Voraussetzungen benötigen Entwickler umfassende Steuerungsmöglichkeiten für die Rückgabe der Daten durch einen Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="063a8-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="063a8-104">Dies ist der Fall, wenn ein Dienst Vorgang Daten in einem Format zurückgeben muss, das nicht von WCF unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="063a8-104">This is the case when a service operation must return data in a format not supported by WCF.</span></span> <span data-ttu-id="063a8-105">In diesem Thema wird die Verwendung des WCF-Web-http-Programmiermodells zum Erstellen eines solchen Diensts erläutert.</span><span class="sxs-lookup"><span data-stu-id="063a8-105">This topic discusses using the WCF WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="063a8-106">Dieser Dienst besitzt einen Vorgang, durch den ein Stream zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="063a8-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="063a8-107">So implementieren Sie den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="063a8-107">To implement the service contract</span></span>  
  
1. <span data-ttu-id="063a8-108">Definieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="063a8-108">Define the service contract.</span></span> <span data-ttu-id="063a8-109">Der Vertrag wird `IImageServer` genannt und besitzt eine Methode mit der Bezeichnung `GetImage`, von der ein <xref:System.IO.Stream> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="063a8-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="063a8-110">Da die Methode eine <xref:System.IO.Stream>zurückgibt, geht WCF davon aus, dass der Vorgang die gesamte Kontrolle über die Bytes hat, die vom Dienst Vorgang zurückgegeben werden, und wendet keine Formatierung auf die zurückgegebenen Daten an.</span><span class="sxs-lookup"><span data-stu-id="063a8-110">Because the method returns a <xref:System.IO.Stream>, WCF assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2. <span data-ttu-id="063a8-111">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="063a8-111">Implement the service contract.</span></span> <span data-ttu-id="063a8-112">Der Vertrag besitzt lediglich einen Vorgang (`GetImage`).</span><span class="sxs-lookup"><span data-stu-id="063a8-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="063a8-113">Diese Methode generiert eine Bitmap und speichert diese anschließend im JPG-Format in einem <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="063a8-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="063a8-114">Der Vorgang gibt diesen Stream anschließend an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="063a8-114">The operation then returns that stream to the caller.</span></span>  
  
    ```csharp
    public class Service : IImageServer
    {
        public Stream GetImage(int width, int height)
        {
            Bitmap bitmap = new Bitmap(width, height);
            for (int i = 0; i < bitmap.Width; i++)
            {
                for (int j = 0; j < bitmap.Height; j++)
                {
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);
                }
            }
            MemoryStream ms = new MemoryStream();
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);
            ms.Position = 0;
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";
            return ms;
        }
    }
    ```  
  
     <span data-ttu-id="063a8-115">Beachten Sie die vorvorletzte Codezeile: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span><span class="sxs-lookup"><span data-stu-id="063a8-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="063a8-116">Hierdurch wird der ContentType-Header auf `"image/jpeg"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="063a8-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="063a8-117">Zwar wird in diesem Beispiel das Zurückgeben einer JPG-Datei veranschaulicht, das Beispiel kann jedoch zum Zurückgeben eines beliebigen Datentyps in einem beliebigen Format angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="063a8-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="063a8-118">Die Daten müssen durch den Vorgang abgerufen oder erstellt und anschließend in den Stream geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="063a8-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="063a8-119">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="063a8-119">To host the service</span></span>  
  
1. <span data-ttu-id="063a8-120">Erstellen Sie eine Konsolenanwendung, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="063a8-120">Create a console application to host the service.</span></span>  
  
    ```csharp
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2. <span data-ttu-id="063a8-121">Erstellen Sie eine Variable, um die Basisadresse für den Dienst innerhalb der `Main`-Methode zu speichern.</span><span class="sxs-lookup"><span data-stu-id="063a8-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="063a8-122">Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz für den Dienst, in der die Dienstklasse und die Basisadresse angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="063a8-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```csharp
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="063a8-123">Fügen Sie mithilfe der <xref:System.ServiceModel.WebHttpBinding> und der <xref:System.ServiceModel.Description.WebHttpBehavior> einen Endpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="063a8-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="063a8-124">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="063a8-124">Open the service host.</span></span>  
  
    ```csharp  
    host.Open();  
    ```  
  
6. <span data-ttu-id="063a8-125">Warten Sie, bis der Benutzer den Dienst durch Drücken der EINGABETASTE beendet.</span><span class="sxs-lookup"><span data-stu-id="063a8-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```csharp
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="063a8-126">So rufen Sie den unformatierten Dienst mithilfe von Internet Explorer auf</span><span class="sxs-lookup"><span data-stu-id="063a8-126">To call the raw service using Internet Explorer</span></span>  
  
1. <span data-ttu-id="063a8-127">Führen Sie den Dienst aus. Die folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="063a8-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2. <span data-ttu-id="063a8-128">Öffnen Sie Internet Explorer, und geben Sie `http://localhost:8000/Service/GetImage?width=50&height=40` ein. Ein gelbes Rechteck sollte angezeigt werden, durch dessen Mitte eine blauen diagonale Linie verläuft.</span><span class="sxs-lookup"><span data-stu-id="063a8-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="063a8-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="063a8-129">Example</span></span>  
 <span data-ttu-id="063a8-130">Die folgende vollständige Auflistung enthält den Code für dieses Thema:</span><span class="sxs-lookup"><span data-stu-id="063a8-130">The following is a complete listing of the code for this topic.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="063a8-131">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="063a8-131">Compiling the Code</span></span>  
  
- <span data-ttu-id="063a8-132">Verweisen Sie beim Kompilieren des Beispielcodes auf "System.ServiceModel.dll" und "System.ServiceModel.Web.dll".</span><span class="sxs-lookup"><span data-stu-id="063a8-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063a8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="063a8-133">See also</span></span>

- [<span data-ttu-id="063a8-134">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="063a8-134">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
