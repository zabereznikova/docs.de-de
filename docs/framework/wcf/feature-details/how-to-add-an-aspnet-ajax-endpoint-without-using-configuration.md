---
title: 'Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9935e2a7738796fff9a037b09237a6acbf7bf988
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185134"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration
Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-fähigen Endpunkt verfügbar macht, der von JavaScript auf einer Clientwebsite aufgerufen werden kann. Zum Erstellen eines solchen Endpunkts können Sie entweder (wie bei allen anderen WCF-Endpunkten) eine Konfigurationsdatei verwenden, oder Sie können eine Methode einsetzen, die keine Konfigurationselemente benötigt. In diesem Thema wird die zweite Methode veranschaulicht.  
  
 Um Dienste mit ASP.NET AJAX-Endpunkten ohne Konfiguration zu erstellen, müssen diese Dienste von Internetinformationsdiensten (IIS) gehostet werden. Um einen ASP.NET AJAX-Endpunkt mit <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> diesem Ansatz zu aktivieren, geben Sie den Parameter as Factory in der [ \@ServiceHost-Direktive](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) in der .svc-Datei an. Diese benutzerdefinierte Factory ist die Komponente, die automatisch einen ASP.NET AJAX-Endpunkt konfiguriert, damit er auf einer Client-Website von JavaScript aufgerufen werden kann.  
  
 Ein arbeitstechnisches Beispiel finden Sie im [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Eine Übersicht darüber, wie ein ASP.NET AJAX-Endpunkt mithilfe von Konfigurationselementen konfiguriert wird, finden Sie unter [Gewusst wie: Verwenden von Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>So erstellen Sie einen WCF-Basisdienst  
  
1. Definieren Sie einen grundlegenden WCF-Dienstvertrag <xref:System.ServiceModel.ServiceContractAttribute> mit einer Schnittstelle, die mit dem Attribut gekennzeichnet ist. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.  
  
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
  
1. Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung. Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@ServiceHost-Direktiveninformationen](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) für den Dienst hinzufügen. Geben Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> an, dass der in der [ \@ServiceHost-Direktive](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) verwendet werden soll, um automatisch einen ASP.NET AJAX-Endpunkt s.  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. Erstellen Sie den Dienst, und rufen Sie ihn vom Client aus auf. Internetinformationsdienste (IIS) aktiviert den Dienst, sobald er aufgerufen wird. Weitere Informationen zum Hosten in IIS finden Sie unter [Gewusst wie: Hosten eines WCF-Dienstes in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1. Der Endpunkt wird an einer leeren Adresse relativ zur .svc-Datei konfiguriert, sodass der Dienst jetzt verfügbar\<ist und durch Senden von Anforderungen an `Add` den dienst.svc/-Vorgang> - z. B. service.svc/Add für den Vorgang, aufgerufen werden kann. Sie können ihn verwenden, indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie im [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Beispiel  
  
 Der automatisch konfigurierte Endpunkt wird bei einer leeren Adresse relativ zur Basis-URL erstellt. Bei diesem Ansatz wird auch eine Konfigurationsdatei hinzugefügt und verwendet. Wenn die Konfigurationsdatei Endpunktdefinitionen enthält, werden diese Endpunkte dem automatisch konfigurierten Endpunkt hinzugefügt.  
  
 Die Datei "service.svc" verwendet beispielsweise die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, und das Dienstverzeichnis enthält eine Web.config-Datei, die mithilfe der <xref:System.ServiceModel.BasicHttpBinding> einen Endpunkt für den gleichen Dienst definiert, wobei für diesen eine zu "soap" relative Adresse angegeben ist. In diesem Fall enthält der Dienst zwei Endpunkte: einen unter service.svc (der auf ASP.NET AJAX-Anforderungen antwortet) und einen weiteren unter service.svc/soap (der auf SOAP-Anforderungen antwortet).  
  
 Definiert die Konfigurationsdatei einen Endpunkt unter einer leeren relativen Adresse und wird <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> verwendet, wird eine Ausnahme ausgelöst, und der Start des Diensts schlägt fehl.  
  
 Sie können die Konfiguration nicht dazu verwenden, Einstellungen auf dem automatisch konfigurierten Endpunkt zu ändern. Muss eine Einstellung (etwa das Readerkontingent) geändert werden, dürfen Sie nicht den konfigurationsfreien Ansatz verwenden, indem Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aus der SVC-Datei entfernen und einen Konfigurationseintrag für den Endpunkt einfügen.  
  
 Wenn Ihr Dienst den ASP.NET-Kompatibilitätsmodus erfordert &#8211; etwa weil er die <xref:System.Web.HttpContext>-Klasse oder den ASP.NET-Autorisierungsmechanismus verwendet &#8211; ist eine Konfigurationsdatei erforderlich, damit dieser Modus aktiviert werden kann. Das erforderliche Konfigurationselement ist das [ \<>-Element s. HostingEnvironment,](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) das wie folgt hinzugefügt werden muss.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Weitere Informationen finden Sie im [WCF-Dienst- und](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) ASP.NET-Thema.  
  
 Bei der <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>-Klasse handelt es sich um eine abgeleitete Klasse von <xref:System.ServiceModel.Activation.ServiceHostFactory>. Eine ausführliche Erläuterung des Diensthostfactorymechanismus finden Sie im Thema [Erweitern des Hostings mit ServiceHostFactory.](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste zu WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
