---
title: "Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF-Web-HTTP-Programmiermodells zurückgibt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e1d808d4daf91b5ff89b05cab8359c90090f293
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="3b699-102">Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF-Web-HTTP-Programmiermodells zurückgibt</span><span class="sxs-lookup"><span data-stu-id="3b699-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="3b699-103">Unter bestimmten Voraussetzungen benötigen Entwickler umfassende Steuerungsmöglichkeiten für die Rückgabe der Daten durch einen Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="3b699-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="3b699-104">Dies ist der Fall, wenn ein Dienstvorgang Daten in einem Format, die von nicht unterstützten zurückgeben muss [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b699-104">This is the case when a service operation must return data in a format not supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="3b699-105">In diesem Thema wird erläutert, wie ein solcher Dienst mithilfe des WEB-HTTP-Webprogrammiermodells von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b699-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="3b699-106">Dieser Dienst besitzt einen Vorgang, durch den ein Stream zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3b699-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="3b699-107">So implementieren Sie den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="3b699-107">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="3b699-108">Definieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="3b699-108">Define the service contract.</span></span> <span data-ttu-id="3b699-109">Der Vertrag wird `IImageServer` genannt und besitzt eine Methode mit der Bezeichnung `GetImage`, von der ein <xref:System.IO.Stream> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3b699-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="3b699-110">Da die Methode einen <xref:System.IO.Stream> zurückgibt, wird von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] davon ausgegangen, dass der Vorgang die vollständige Kontrolle über die Bytes besitzt, die vom Dienstvorgang zurückgegeben werden. Für die zurückgegebenen Daten erfolgt keine Formatierung.</span><span class="sxs-lookup"><span data-stu-id="3b699-110">Because the method returns a <xref:System.IO.Stream>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2.  <span data-ttu-id="3b699-111">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="3b699-111">Implement the service contract.</span></span> <span data-ttu-id="3b699-112">Der Vertrag besitzt lediglich einen Vorgang (`GetImage`).</span><span class="sxs-lookup"><span data-stu-id="3b699-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="3b699-113">Diese Methode generiert eine Bitmap und speichert diese anschließend im JPG-Format in einem <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="3b699-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="3b699-114">Der Vorgang gibt diesen Stream anschließend an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="3b699-114">The operation then returns that stream to the caller.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="3b699-115">Beachten Sie die vorvorletzte Codezeile: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span><span class="sxs-lookup"><span data-stu-id="3b699-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="3b699-116">Hierdurch wird der ContentType-Header auf `"image/jpeg"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3b699-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="3b699-117">Zwar wird in diesem Beispiel das Zurückgeben einer JPG-Datei veranschaulicht, das Beispiel kann jedoch zum Zurückgeben eines beliebigen Datentyps in einem beliebigen Format angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3b699-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="3b699-118">Die Daten müssen durch den Vorgang abgerufen oder erstellt und anschließend in den Stream geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3b699-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="3b699-119">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="3b699-119">To host the service</span></span>  
  
1.  <span data-ttu-id="3b699-120">Erstellen Sie eine Konsolenanwendung, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="3b699-120">Create a console application to host the service.</span></span>  
  
    ```  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2.  <span data-ttu-id="3b699-121">Erstellen Sie eine Variable, um die Basisadresse für den Dienst innerhalb der `Main`-Methode zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3b699-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="3b699-122">Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz für den Dienst, in der die Dienstklasse und die Basisadresse angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3b699-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="3b699-123">Fügen Sie mithilfe der <xref:System.ServiceModel.WebHttpBinding> und der <xref:System.ServiceModel.Description.WebHttpBehavior> einen Endpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b699-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="3b699-124">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="3b699-124">Open the service host.</span></span>  
  
    ```  
    host.Open()  
    ```  
  
6.  <span data-ttu-id="3b699-125">Warten Sie, bis der Benutzer den Dienst durch Drücken der EINGABETASTE beendet.</span><span class="sxs-lookup"><span data-stu-id="3b699-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```  
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="3b699-126">So rufen Sie den unformatierten Dienst mithilfe von Internet Explorer auf</span><span class="sxs-lookup"><span data-stu-id="3b699-126">To call the raw service using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="3b699-127">Führen Sie den Dienst aus. Die folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="3b699-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2.  <span data-ttu-id="3b699-128">Öffnen Sie Internet Explorer, und geben Sie `http://localhost:8000/Service/GetImage?width=50&height=40` ein. Ein gelbes Rechteck sollte angezeigt werden, durch dessen Mitte eine blauen diagonale Linie verläuft.</span><span class="sxs-lookup"><span data-stu-id="3b699-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b699-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b699-129">Example</span></span>  
 <span data-ttu-id="3b699-130">Die folgende vollständige Auflistung enthält den Code für dieses Thema:</span><span class="sxs-lookup"><span data-stu-id="3b699-130">The following is a complete listing of the code for this topic.</span></span>  
  
```  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="3b699-131">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3b699-131">Compiling the Code</span></span>  
  
-   <span data-ttu-id="3b699-132">Verweisen Sie beim Kompilieren des Beispielcodes auf "System.ServiceModel.dll" und "System.ServiceModel.Web.dll".</span><span class="sxs-lookup"><span data-stu-id="3b699-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b699-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b699-133">See Also</span></span>  
 [<span data-ttu-id="3b699-134">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="3b699-134">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
