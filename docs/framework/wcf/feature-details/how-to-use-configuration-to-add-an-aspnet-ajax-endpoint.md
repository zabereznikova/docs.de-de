---
title: 'Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts'
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 97f8174161068f2c72b6bd2bc4e8a3044f5bccdd
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051661"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts
Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-fähigen Endpunkt zur Verfügung stellt, der von JavaScript auf einer Client Website aufgerufen werden kann. Zum Erstellen eines solchen Endpunkts können Sie entweder eine Konfigurationsdatei wie alle anderen Windows Communication Foundation (WCF)-Endpunkte verwenden oder eine Methode verwenden, die keine Konfigurationselemente erfordert. In diesem Thema wird die Konfigurationsmethode veranschaulicht.  
  
 Der Teil der Prozedur, mit dem der Dienst Endpunkt ASP.NET AJAX-fähig werden kann, besteht aus der Konfiguration des Endpunkts für die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und zum Hinzufügen des [\<enableWebScript>](../../configure-apps/file-schema/wcf/enablewebscript.md) Endpunkt Verhaltens. Nach der Konfiguration des Endpunkts sind die Schritte zum Implementieren und Hosten des Diensts mit denen vergleichbar, die von einem beliebigen WCF-Dienst verwendet werden. Ein funktionierendes Beispiel finden [Sie unter AJAX-Dienst mit HTTP Post](../samples/ajax-service-using-http-post.md).  
  
 Weitere Informationen zum Konfigurieren eines ASP.NET AJAX-Endpunkts ohne Verwendung der Konfiguration finden Sie unter Gewusst [wie: Hinzufügen eines ASP.NET AJAX](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)-Endpunkts ohne Verwendung der Konfiguration.  
  
## <a name="to-create-a-basic-wcf-service"></a>So erstellen Sie einen WCF-Basisdienst  
  
1. Definieren Sie einen grundlegenden WCF-Dienstvertrag mit einer mit dem-Attribut markierten Schnittstelle <xref:System.ServiceModel.ServiceContractAttribute> . Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }
        // Other operations omitted…
    }
    ```  
  
3. Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>So erstellen Sie einen ASP.NET AJAX-Endpunkt für den Dienst  
  
1. Erstellen Sie eine Verhaltens Konfiguration, und geben Sie das [\<enableWebScript>](../../configure-apps/file-schema/wcf/enablewebscript.md) Verhalten für ASP.NET AJAX-aktivierte Endpunkte des Dienstanbieter an.  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2. Erstellen Sie einen Endpunkt für den Dienst, der <xref:System.ServiceModel.WebHttpBinding> und das ASP.NET AJAX-Verhalten verwendet, das im vorherigen Schritt definiert wurde.  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>
    ```  
  
## <a name="to-host-the-service-in-iis"></a>So hosten Sie den Dienst in IIS  
  
1. Um den Dienst in IIS zu hosten, erstellen Sie in der Anwendung eine neue Datei mit dem Namen service und einer SVC-Erweiterung. Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktiveninformationen für den Dienst hinzufügen. Die Dienstdatei für das `CalculatorService`-Beispiel enthält z.&#160;B. folgende Informationen.  
  
    ```aspx-csharp
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. Weitere Informationen zum Hosten in IIS finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in IIS](how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1. Der Endpunkt wird mit einer leeren Adresse relativ zur SVC-Datei konfiguriert, sodass der Dienst jetzt verfügbar ist und aufgerufen werden kann, indem Anforderungen an Service. svc gesendet werden, z. b. " \<operation> Service. svc/Add" für den `Add` Vorgang. Sie können ihn verwenden, indem Sie die Endpunkt-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie unter der [AJAX-Dienst mit HTTP Post](../samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von WCF-Diensten für ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md)
- [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
