---
title: 'Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts'
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 5314bb000371ee2d3eef2576e1edfa455aa65b90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184837"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts
Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-fähigen Endpunkt verfügbar macht, der von JavaScript auf einer Clientwebsite aufgerufen werden kann. Um einen solchen Endpunkt zu erstellen, können Sie entweder eine Konfigurationsdatei verwenden, wie bei allen anderen WCF-Endpunkten (Windows Communication Foundation), oder eine Methode verwenden, die keine Konfigurationselemente erfordert. In diesem Thema wird die Konfigurationsmethode veranschaulicht.  
  
 Der Teil der Prozedur, der es dem Dienstendpunkt ermöglicht, ASP.NET AJAX-aktiviert zu werden, besteht darin, den Endpunkt so zu konfigurieren, dass er die <xref:System.ServiceModel.WebHttpBinding> verwendet und das [ \<enableWebScript->-Endpunktverhalten](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) hinzugefügt wird. Nach dem Konfigurieren des Endpunkts ähneln die Schritte zum Implementieren und Hosten des Diensts denen, die von einem WCF-Dienst verwendet werden. Ein arbeitstechnisches Beispiel finden Sie im [AJAX-Dienst unter HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Weitere Informationen zum Konfigurieren eines ASP.NET AJAX-Endpunkts ohne Konfiguration finden Sie unter [Gewusst wie: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
## <a name="to-create-a-basic-wcf-service"></a>So erstellen Sie einen WCF-Basisdienst  
  
1. Definieren Sie einen grundlegenden WCF-Dienstvertrag <xref:System.ServiceModel.ServiceContractAttribute> mit einer Schnittstelle, die mit dem Attribut gekennzeichnet ist. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.  
  
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
  
1. Erstellen Sie eine Verhaltenskonfiguration, und geben Sie das [ \<verhaltene EnableWebScript->-Verhalten](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) für ASP.NET AJAX-aktivierten Endpunkte des Dienstes an.  
  
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
  
1. Um den Dienst in IIS zu hosten, erstellen Sie in der Anwendung eine neue Datei mit dem Namen service und einer SVC-Erweiterung. Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@ServiceHost-Direktiveninformationen](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) für den Dienst hinzufügen. Die Dienstdatei für das `CalculatorService`-Beispiel enthält z.&#160;B. folgende Informationen.  
  
    ```
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. Weitere Informationen zum Hosten in IIS finden Sie unter [Gewusst wie: Hosten eines WCF-Dienstes in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1. Der Endpunkt wird an einer leeren Adresse relativ zur .svc-Datei konfiguriert, sodass der Dienst jetzt verfügbar\<ist und durch Senden von Anforderungen an `Add` den dienst.svc/-Vorgang> - z. B. service.svc/Add für den Vorgang, aufgerufen werden kann. Sie können ihn verwenden, indem Sie die Endpunkt-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie im [AJAX-Dienst unter HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste zu WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
