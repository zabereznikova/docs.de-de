---
title: 'Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d82febd776bfc51e3e9725701253ed19996349b5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration
Mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie einen Dienst erstellen, der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der auf einer Client-Website von JavaScript aufgerufen werden kann. Zum Erstellen eines solchen Endpunkts können Sie entweder (wie bei allen anderen WCF-Endpunkten) eine Konfigurationsdatei verwenden, oder Sie können eine Methode einsetzen, die keine Konfigurationselemente benötigt. In diesem Thema wird die zweite Methode veranschaulicht.  
  
 Um Dienste mit ASP.NET AJAX-Endpunkten ohne Konfiguration zu erstellen, müssen diese Dienste von Internetinformationsdiensten (IIS) gehostet werden. Geben Sie zum Aktivieren von ASP.NET AJAX-Endpunkt mit diesem Ansatz die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> als Factory-Parameter in der [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive in der SVC-Datei. Diese benutzerdefinierte Factory ist die Komponente, die automatisch einen ASP.NET AJAX-Endpunkt konfiguriert, damit er auf einer Client-Website von JavaScript aufgerufen werden kann.  
  
 Ein Arbeitsbeispiel finden Sie unter der [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Einen Überblick über die zum Konfigurieren von ASP.NET AJAX-Endpunkt mithilfe von Konfigurationselementen finden Sie unter [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>So erstellen Sie einen WCF-Basisdienst  
  
1.  Definieren Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Basisdienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut gekennzeichnet ist. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>So hosten Sie einen Dienst in Internetinformationsdiensten (IIS) ohne Konfiguration  
  
1.  Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung. Bearbeiten Sie diese Datei durch Hinzufügen der entsprechenden [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie Informationen für den Dienst. Angeben, die die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in verwendet werden soll die [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie automatisch einen ASP.NET AJAX-Endpunkt zu konfigurieren.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  Erstellen Sie den Dienst, und rufen Sie ihn vom Client aus auf. Internetinformationsdienste (IIS) aktiviert den Dienst, sobald er aufgerufen wird. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Hosting in IIS finden Sie unter [wie: Hosten eines WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1.  Der Endpunkt ist eine leere Adresse relativ zur SVC-Datei konfiguriert, damit der Dienst jetzt verfügbar ist und kann durch Senden von Anforderungen an service.svc/ aufgerufen werden\<Vorgang > – z. B. service.svc/Add für die `Add` Vorgang. Sie können ihn verwenden, indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie die [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Beispiel  
  
 Der automatisch konfigurierte Endpunkt wird bei einer leeren Adresse relativ zur Basis-URL erstellt. Bei diesem Ansatz wird auch eine Konfigurationsdatei hinzugefügt und verwendet. Wenn die Konfigurationsdatei Endpunktdefinitionen enthält, werden diese Endpunkte dem automatisch konfigurierten Endpunkt hinzugefügt.  
  
 Die Datei "service.svc" verwendet beispielsweise die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, und das Dienstverzeichnis enthält eine Web.config-Datei, die mithilfe der <xref:System.ServiceModel.BasicHttpBinding> einen Endpunkt für den gleichen Dienst definiert, wobei für diesen eine zu "soap" relative Adresse angegeben ist. In diesem Fall enthält der Dienst zwei Endpunkte: einen unter service.svc (der auf ASP.NET AJAX-Anforderungen antwortet) und einen weiteren unter service.svc/soap (der auf SOAP-Anforderungen antwortet).  
  
 Definiert die Konfigurationsdatei einen Endpunkt unter einer leeren relativen Adresse und wird <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> verwendet, wird eine Ausnahme ausgelöst, und der Start des Diensts schlägt fehl.  
  
 Sie können die Konfiguration nicht dazu verwenden, Einstellungen auf dem automatisch konfigurierten Endpunkt zu ändern. Muss eine Einstellung (etwa das Readerkontingent) geändert werden, dürfen Sie nicht den konfigurationsfreien Ansatz verwenden, indem Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aus der SVC-Datei entfernen und einen Konfigurationseintrag für den Endpunkt einfügen.  
  
 Wenn Ihr Dienst den ASP.NET-Kompatibilitätsmodus erfordert &#8211; etwa weil er die <xref:System.Web.HttpContext>-Klasse oder den ASP.NET-Autorisierungsmechanismus verwendet &#8211; ist eine Konfigurationsdatei erforderlich, damit dieser Modus aktiviert werden kann. Das Konfigurationselement, das erforderlich ist der [ \<ServiceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) -Element, das wie folgt hinzugefügt werden muss.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Weitere Informationen finden Sie unter der [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) Thema.  
  
 Bei der <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>-Klasse handelt es sich um eine abgeleitete Klasse von <xref:System.ServiceModel.Activation.ServiceHostFactory>. Eine ausführliche Erläuterung des Diensts Host Factory angibt, finden Sie unter der [erweitern Hosting mithilfe von ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) Thema.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste zu WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
