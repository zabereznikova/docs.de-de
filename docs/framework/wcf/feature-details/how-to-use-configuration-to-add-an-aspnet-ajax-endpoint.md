---
title: "Vorgehensweise: Verwenden der Konfiguration zum Hinzuf&#252;gen eines ASP.NET AJAX-Endpunkts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Vorgehensweise: Verwenden der Konfiguration zum Hinzuf&#252;gen eines ASP.NET AJAX-Endpunkts
Mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie einen Dienst erstellen, der einen ASP.NET AJAX\-aktivierten Endpunkt verfügbar macht, der auf einer Client\-Website von JavaScript aufgerufen werden kann.Zum Erstellen eines solchen Endpunkts können Sie entweder \(wie bei allen anderen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Endpunkten\) eine Konfigurationsdatei verwenden, oder Sie können eine Methode einsetzen, die keine Konfigurationselemente benötigt.In diesem Thema wird die Konfigurationsmethode veranschaulicht.  
  
 Der Teil der Prozedur, durch den der Dienstendpunkt ASP.NET AJAX\-aktiviert wird, konfiguriert den Endpunkt für die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und fügt das [\<enableWebScript\>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)\-Endpunktverhalten hinzu.Die Schritte zum Implementieren und Hosten des Diensts nach der Konfiguration des Endpunkts sind den Schritten ähnlich, die von jedem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst verwendet werden.Ein Arbeitsbeispiel finden Sie unter [AJAX\-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Konfigurieren eines ASP.NET AJAX\-Endpunkts ohne Konfiguration finden Sie unter [Vorgehensweise: Hinzufügen eines ASP.NET AJAX\-Endpunkts ohne Verwendung einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### So erstellen Sie einen WCF\-Basisdienst  
  
1.  Definieren Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Basisdienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut gekennzeichnet ist.Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>.Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>\-Eigenschaft festlegen.  
  
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
  
2.  Implementieren Sie den `ICalculator`\-Dienstvertrag mit `CalculatorService`.  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Definieren Sie einen Namespace für die `ICalculator`\-Implementierung und die `CalculatorService`\-Implementierung, indem Sie sie in einen Namespaceblock einschließen.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### So erstellen Sie einen ASP.NET AJAX\-Endpunkt für den Dienst  
  
1.  Erstellen Sie eine Verhaltenskonfiguration, und geben Sie das [\<enableWebScript\>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)\-Verhalten für ASP.NET AJAX\-aktivierte Endpunkte des Diensts an.  
  
    ```  
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
  
2.  Erstellen Sie einen Endpunkt für den Dienst, der <xref:System.ServiceModel.WebHttpBinding> und das ASP.NET AJAX\-Verhalten verwendet, das im vorherigen Schritt definiert wurde.  
  
    ```  
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
  
### So hosten Sie den Dienst in IIS  
  
1.  Um den Dienst in IIS zu hosten, erstellen Sie in der Anwendung eine neue Datei mit dem Namen service und einer SVC\-Erweiterung.Bearbeiten Sie diese Datei, indem Sie die entsprechenden [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\-Direktiveninformationen für den Dienst hinzufügen.Die Dienstdatei für das `CalculatorService`\-Beispiel enthält z. B. folgende Informationen.  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Hosting in IIS finden Sie unter [Gewusst wie: Hosten eines WCF\-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### So rufen Sie den Dienst auf  
  
1.  Der Endpunkt ist für eine leere Adresse konfiguriert, die relativ zur SVC\-Datei festgelegt ist. Daher ist der Dienst jetzt verfügbar und kann durch Senden von Anforderungen an "service.svc\/\<operation\>" aufgerufen werden – beispielsweise durch "service.svc\/Add" für den `Add`\-Vorgang.Sie können ihn verwenden, indem Sie die Endpunkt\-URL in die Scripts\-Auflistung des ASP.NET AJAX Script Manager\-Steuerelements eingeben.Ein Beispiel hierfür finden Sie unter [AJAX\-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## Siehe auch  
 [Erstellen von WCF\-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [Vorgehensweise: Migrieren AJAX\-aktivierter ASP.NET\-Webdienste nach WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)