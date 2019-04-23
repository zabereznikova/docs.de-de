---
title: 'Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF-Web-HTTP-Programmiermodells zurückgibt'
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: 55fdc6824ab82bdf3b5913cd600815ed05bd909c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303920"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a>Vorgehensweise: Erstellen eines Diensts, der beliebige Daten mithilfe des WCF-Web-HTTP-Programmiermodells zurückgibt
Unter bestimmten Voraussetzungen benötigen Entwickler umfassende Steuerungsmöglichkeiten für die Rückgabe der Daten durch einen Dienstvorgang. Dies ist der Fall, wenn ein Dienstvorgang Daten in einem nicht von WCF unterstützten Format zurückgeben muss. In diesem Thema wird erläutert, mit den WCF-HTTP-Webprogrammierungsmodell zum Erstellen eines solchen Diensts. Dieser Dienst besitzt einen Vorgang, durch den ein Stream zurückgegeben wird.  
  
### <a name="to-implement-the-service-contract"></a>So implementieren Sie den Dienstvertrag  
  
1. Definieren Sie den Dienstvertrag. Der Vertrag wird `IImageServer` genannt und besitzt eine Methode mit der Bezeichnung `GetImage`, von der ein <xref:System.IO.Stream> zurückgegeben wird.  
  
    ```  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     Da die Methode gibt eine <xref:System.IO.Stream>, WCF wird davon ausgegangen, dass der Vorgang verfügt über vollständige Kontrolle über die Bytes, die vom Dienstvorgang zurückgegeben werden und keine Formatierung auf die Daten, die zurückgegeben wird.  
  
2. Implementieren Sie den Dienstvertrag. Der Vertrag besitzt lediglich einen Vorgang (`GetImage`). Diese Methode generiert eine Bitmap und speichert diese anschließend im JPG-Format in einem <xref:System.IO.MemoryStream>. Der Vorgang gibt diesen Stream anschließend an den Aufrufer zurück.  
  
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
  
     Beachten Sie die vorvorletzte Codezeile: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`  
  
     Hierdurch wird der ContentType-Header auf `"image/jpeg"` festgelegt. Zwar wird in diesem Beispiel das Zurückgeben einer JPG-Datei veranschaulicht, das Beispiel kann jedoch zum Zurückgeben eines beliebigen Datentyps in einem beliebigen Format angepasst werden. Die Daten müssen durch den Vorgang abgerufen oder erstellt und anschließend in den Stream geschrieben werden.  
  
### <a name="to-host-the-service"></a>So hosten Sie den Dienst  
  
1. Erstellen Sie eine Konsolenanwendung, um den Dienst zu hosten.  
  
    ```  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2. Erstellen Sie eine Variable, um die Basisadresse für den Dienst innerhalb der `Main`-Methode zu speichern.  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz für den Dienst, in der die Dienstklasse und die Basisadresse angegeben sind.  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. Fügen Sie mithilfe der <xref:System.ServiceModel.WebHttpBinding> und der <xref:System.ServiceModel.Description.WebHttpBehavior> einen Endpunkt hinzu.  
  
    ```  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. Öffnen des Diensthosts  
  
    ```  
    host.Open()  
    ```  
  
6. Warten Sie, bis der Benutzer den Dienst durch Drücken der EINGABETASTE beendet.  
  
    ```  
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a>So rufen Sie den unformatierten Dienst mithilfe von Internet Explorer auf  
  
1. Führen Sie den Dienst aus. Die folgende Ausgabe sollte angezeigt werden: `Service is running Press ENTER to close the host`  
  
2. Öffnen Sie Internet Explorer, und geben Sie `http://localhost:8000/Service/GetImage?width=50&height=40` ein. Ein gelbes Rechteck sollte angezeigt werden, durch dessen Mitte eine blauen diagonale Linie verläuft.  
  
## <a name="example"></a>Beispiel  
 Die folgende vollständige Auflistung enthält den Code für dieses Thema:  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Verweisen Sie beim Kompilieren des Beispielcodes auf "System.ServiceModel.dll" und "System.ServiceModel.Web.dll".  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
