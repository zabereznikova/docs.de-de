---
title: 'Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts'
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: f14b441ead7c701aa4f794370fc5f54ad3b4a4e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts
Windows Communication Foundation (WCF) können Sie einen Dienst zu erstellen, mit der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar, die auf einer Client-Website von JavaScript aufgerufen werden kann. Zum Erstellen eines solchen Endpunkts können Sie eine Konfigurationsdatei verwenden, wie bei allen anderen Windows Communication Foundation (WCF)-Endpunkten oder verwenden Sie eine Methode, die keine Konfigurationselemente benötigt. In diesem Thema wird die Konfigurationsmethode veranschaulicht.  
  
 Der Teil der Prozedur, die den Dienstendpunkt zu ASP.NET AJAX-aktivierten ermöglicht besteht in der Konfiguration des Endpunkts verwendet die <xref:System.ServiceModel.WebHttpBinding> und zum Hinzufügen der [ \<EnableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Endpunktverhalten. Nach der Konfiguration des Endpunkts, sind die Schritte zum Implementieren und Hosten des Diensts von WCF-Dienst verwendeten ähnlich. Ein Arbeitsbeispiel finden Sie unter der [AJAX-Dienst mithilfe von HTTP-POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Weitere Informationen über das ASP.NET AJAX-Endpunkt zu konfigurieren, ohne Konfiguration finden Sie unter [wie: Hinzufügen einer ASP.NET AJAX-Endpunkt ohne mithilfe der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>So erstellen Sie einen WCF-Basisdienst  
  
1.  Definieren Sie einen grundlegenden WCF-Dienstvertrag mit einer Schnittstelle, die mit markierten der <xref:System.ServiceModel.ServiceContractAttribute> Attribut. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.  
  
    ```  
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>So erstellen Sie einen ASP.NET AJAX-Endpunkt für den Dienst  
  
1.  Erstellen eine Verhaltenskonfiguration und geben Sie die [ \<EnableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Verhalten für ASP.NET AJAX-aktivierte Endpunkte des Diensts.  
  
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
  
2.  Erstellen Sie einen Endpunkt für den Dienst, der <xref:System.ServiceModel.WebHttpBinding> und das ASP.NET AJAX-Verhalten verwendet, das im vorherigen Schritt definiert wurde.  
  
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
  
### <a name="to-host-the-service-in-iis"></a>So hosten Sie den Dienst in IIS  
  
1.  Um den Dienst in IIS zu hosten, erstellen Sie in der Anwendung eine neue Datei mit dem Namen service und einer SVC-Erweiterung. Bearbeiten Sie diese Datei durch Hinzufügen der entsprechenden [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie Informationen für den Dienst. Die Dienstdatei für das `CalculatorService`-Beispiel enthält z.&#160;B. folgende Informationen.  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  Weitere Informationen zum hosting in IIS finden Sie unter [wie: Hosten eines WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1.  Der Endpunkt ist eine leere Adresse relativ zur SVC-Datei konfiguriert, damit der Dienst jetzt verfügbar ist und kann durch Senden von Anforderungen an service.svc/ aufgerufen werden\<Vorgang > – z. B. service.svc/Add für die `Add` Vorgang. Sie können ihn verwenden, indem Sie die Endpunkt-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie die [AJAX-Dienst mithilfe von HTTP-POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste zu WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
