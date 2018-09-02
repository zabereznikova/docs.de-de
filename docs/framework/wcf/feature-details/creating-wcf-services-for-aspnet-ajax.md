---
title: Erstellen von WCF-Diensten für ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
ms.openlocfilehash: 4d3953046a796686a465cd8096b8f2ba930aa9fd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463259"
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a>Erstellen von WCF-Diensten für ASP.NET AJAX
Microsoft ASP.NET AJAX ermöglicht es Ihnen, zügig Webseiten zu erstellen, die mit reaktionsschnellen und vertrauten Benutzeroberflächenelementen eine hohe Benutzerfreundlichkeit bieten. ASP.NET AJAX bietet Bibliotheken mit Clientskripts, in denen browserübergreifende ECMAScript (JavaScript)- und Dynamic&#160;HTML (DHTML)-Technologien integriert sind. Außerdem sind diese Funktionen in die serverbasierte ASP.NET&#160;2.0-Entwicklungsplattform integriert. Durch die Verwendung von ASP.NET AJAX können Sie die Benutzerfreundlichkeit und die Effizienz Ihrer Webanwendungen verbessern.  
  
 ASP.NET AJAX besteht aus Clientskriptbibliotheken und Serverkomponenten, die zu einem robusten Entwicklungsframework integriert sind. So greifen Sie über eine ASP.NET-Seite auf einen Dienst zu: Sobald die Dienst-URL des ASP.NET Script Manager-Steuerelements auf der Seite hinzugefügt wurde, können Dienstvorgänge anhand von JavaScript-Code aufgerufen werden. Dieser Code gleicht einem normalen JavaScript-Funktionsaufruf. Finden Sie unter [Learn ASP.NET AJAX](https://go.microsoft.com/fwlink/?LinkId=186475) zur Verwendung von Webdiensten innerhalb des AJAX-Framework.  
  
 Die meisten Windows Communication Foundation (WCF)-Dienste können als kompatibel mit ASP.NET AJAX-Dienst verfügbar gemacht werden, indem ein entsprechender ASP.NET AJAX-Endpunkt hinzufügen.  
  
 Wenn Sie Visual Studio verwenden, können Sie eine vorgefertigte Vorlage für AJAX-aktivierten WCF-Dienste zur Verfügung, in der **neues Element hinzufügen** Dialogfeld bei der Arbeit mit ASP.NET-Websites oder Webanwendungen.  
  
 Wenn Sie die Visual&#160;Studio-Vorlagen nicht verwenden, gibt es zwei Möglichkeiten, einen ASP.NET AJAX-Endpunkt zu erstellen:  
  
-   Erstellen Sie den Endpunkt mithilfe dynamischer Hostaktivierung, ohne eine Konfiguration zu verwenden. Dies ist der einfachste Ansatz, wenn Sie mit dem WCF-Konfigurationssystem nicht vertraut sind. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen einer ASP.NET AJAX-Endpunkt ohne mithilfe der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
-   Fügen Sie an einen WCF-Dienst mithilfe der Konfiguration einen AJAX-fähigen Endpunkt hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
 Das Webprogrammiermodell beschrieben, die der [Web-HTTP-Programmierung Überblick über WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) kann mit ASP.NET AJAX-Diensten verwendet werden. Dies gilt insbesondere in folgenden Fällen:  
  
-   Sie können das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut und das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut verwenden, um zwischen HTTP GET und HTTP POST-Verben auszuwählen. Wenn sie richtig verwendet werden, kann die Leistung Ihrer Anwendung bedeutend verbessert werden. Weitere Informationen finden Sie unter [Vorgehensweise: Auswählen zwischen HTTP POST- und GET HTTP-Anforderungen für ASP.NET AJAX-Endpunkte](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).  
  
-   Sie können die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft und die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft verwenden, damit Ihr Dienst XML-Daten anstelle der standardmäßigen JavaScript Object Notation (JSON) zurückgibt. Wenn dies für das ASP.NET AJAX-Framework ausgeführt wird, empfängt der JavaScript-Client ein XML DOM-Objekt.  
  
    > [!WARNING]
    >  Der Vorgang muss dafür den Inhaltstyp auf Text/XML festlegen. Andernfalls empfängt der JavaScript-Client eine Zeichenfolge mit dem XML-Objekt statt eines XML DOM-Objekts.  
  
     Das folgende Beispiel zeigt einen Vorgang, der XML-Daten zurückgibt, für die der Inhaltstyp richtig festgelegt wurde:  
  
    ```  
    [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]  
    public XElement GetData()  
    {  
    XElement x;  
    //Get some data here...  
  
    WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";      
    return x;  
    }  
    ```  
  
-   Es können keine weiteren Eigenschaften für das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut und das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut geändert werden, wenn die Kompatibilität mit ASP.NET AJAX erforderlich ist. Weitere Aspekte des Webprogrammiermodells können verwendet werden, sofern die ASP.NET AJAX-Aufrufkonventionen nicht verletzt werden.  
  
 Erweitertere Szenarien erfordern zusätzlichen Informationen über die AJAX-Unterstützung in WCF verstanden werden:  
  
-   Um zu verstehen, wie Daten übertragen werden, zwischen einem AJAX- und einen WCF-Dienst, der mit JavaScript sowie Details für die JavaScript-Typen wie .NET Framework-Typen zugeordnet werden, finden Sie unter [Unterstützung für JSON und andere von Datenformaten übertragen](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md).  
  
-   Um ASP.NET-Funktionen nutzen zu können, beispielsweise die URL-basierte Authentifizierung und den Zugriff auf ASP.NET-Sitzungsinformationen, empfiehlt es sich, den ASP.NET-Kompatibilitätsmodus durch Konfiguration zu aktivieren.  
  
 AJAX-Endpunkte in WCF können auch ohne Verwendung des ASP.NET AJAX-Frameworks verwendet werden. Hierzu müssen einen Überblick über die Unterstützungsarchitektur der AJAX-Unterstützung in WCF. Eine Erläuterung dieser Architektur, finden Sie unter [WCF-HTTP-Objekt Webprogrammiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md). Ein Codebeispiel, das diesen Ansatz veranschaulicht, finden Sie unter den [AJAX-Dienst mit JSON und XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
 [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
 [Vorgehensweise: Wählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
