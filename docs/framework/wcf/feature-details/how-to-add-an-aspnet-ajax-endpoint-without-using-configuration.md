---
title: 'Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 4a7ff48e529ab58c8744edea22d52ad12a4d7b96
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895076"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration
Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der von JavaScript auf einer Client Website aufgerufen werden kann. Zum Erstellen eines solchen Endpunkts können Sie entweder (wie bei allen anderen WCF-Endpunkten) eine Konfigurationsdatei verwenden, oder Sie können eine Methode einsetzen, die keine Konfigurationselemente benötigt. In diesem Thema wird die zweite Methode veranschaulicht.  
  
 Um Dienste mit ASP.NET AJAX-Endpunkten ohne Konfiguration zu erstellen, müssen diese Dienste von Internetinformationsdiensten (IIS) gehostet werden. Um einen ASP.NET AJAX-Endpunkt mithilfe dieses Ansatzes zu aktivieren, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> geben Sie als factoryparameter in der [ \@Service Host](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive in der SVC-Datei an. Diese benutzerdefinierte Factory ist die Komponente, die automatisch einen ASP.NET AJAX-Endpunkt konfiguriert, damit er auf einer Client-Website von JavaScript aufgerufen werden kann.  
  
 Ein funktionierendes Beispiel finden Sie unter [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Einen Überblick über die Konfiguration eines ASP.NET AJAX-Endpunkts mithilfe von Konfigurationselementen finden [Sie unter Gewusst wie: Verwenden Sie die Konfiguration, um einen ASP.net](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)AJAX-Endpunkt hinzuzufügen.  
  
### <a name="to-create-a-basic-wcf-service"></a>So erstellen Sie einen WCF-Basisdienst  
  
1. Definieren Sie einen grundlegenden WCF-Dienstvertrag mit einer mit <xref:System.ServiceModel.ServiceContractAttribute> dem-Attribut markierten Schnittstelle. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.  
  
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
  
2. Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>So hosten Sie einen Dienst in Internetinformationsdiensten (IIS) ohne Konfiguration  
  
1. Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung. Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@Service Host](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktiveninformationen für den Dienst hinzufügen. Geben Sie an <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> , dass in der [ \@Service Host](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive verwendet werden soll, um einen ASP.NET AJAX-Endpunkt automatisch zu konfigurieren.  
  
    ```text
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. Erstellen Sie den Dienst, und rufen Sie ihn vom Client aus auf. Internetinformationsdienste (IIS) aktiviert den Dienst, sobald er aufgerufen wird. Weitere Informationen zum Hosting in IIS finden [Sie unter Gewusst wie: Hosten eines WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1. Der Endpunkt wird mit einer leeren Adresse relativ zur SVC-Datei konfiguriert, sodass der Dienst jetzt verfügbar ist und durch das Senden von Anforderungen an Service. svc/\<Operation > aufgerufen werden kann, z. b. "Service. svc/Add" für den `Add` Vorgang. Sie können ihn verwenden, indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie unter [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Beispiel  
  
 Der automatisch konfigurierte Endpunkt wird bei einer leeren Adresse relativ zur Basis-URL erstellt. Bei diesem Ansatz wird auch eine Konfigurationsdatei hinzugefügt und verwendet. Wenn die Konfigurationsdatei Endpunktdefinitionen enthält, werden diese Endpunkte dem automatisch konfigurierten Endpunkt hinzugefügt.  
  
 Die Datei "service.svc" verwendet beispielsweise die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, und das Dienstverzeichnis enthält eine Web.config-Datei, die mithilfe der <xref:System.ServiceModel.BasicHttpBinding> einen Endpunkt für den gleichen Dienst definiert, wobei für diesen eine zu "soap" relative Adresse angegeben ist. In diesem Fall enthält der Dienst zwei Endpunkte: einen unter service.svc (der auf ASP.NET AJAX-Anforderungen antwortet) und einen weiteren unter service.svc/soap (der auf SOAP-Anforderungen antwortet).  
  
 Definiert die Konfigurationsdatei einen Endpunkt unter einer leeren relativen Adresse und wird <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> verwendet, wird eine Ausnahme ausgelöst, und der Start des Diensts schlägt fehl.  
  
 Sie können die Konfiguration nicht dazu verwenden, Einstellungen auf dem automatisch konfigurierten Endpunkt zu ändern. Muss eine Einstellung (etwa das Readerkontingent) geändert werden, dürfen Sie nicht den konfigurationsfreien Ansatz verwenden, indem Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aus der SVC-Datei entfernen und einen Konfigurationseintrag für den Endpunkt einfügen.  
  
 Wenn Ihr Dienst den ASP.NET-Kompatibilitätsmodus erfordert &#8211; etwa weil er die <xref:System.Web.HttpContext>-Klasse oder den ASP.NET-Autorisierungsmechanismus verwendet &#8211; ist eine Konfigurationsdatei erforderlich, damit dieser Modus aktiviert werden kann. Das erforderliche Konfigurationselement ist das [ \<servicehoststingenvironment->](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) Element, das wie folgt hinzugefügt werden muss.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Weitere Informationen finden Sie im Thema [WCF-Dienste und ASP.net](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) .  
  
 Bei der <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>-Klasse handelt es sich um eine abgeleitete Klasse von <xref:System.ServiceModel.Activation.ServiceHostFactory>. Eine ausführliche Erläuterung des Diensthostfactory-Mechanismus finden Sie im Thema [Erweitern des Hosting mit ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) .  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Vorgehensweise: Migrieren von AJAX-fähigen ASP.NET-Webdiensten zu WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
