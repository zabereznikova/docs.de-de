---
title: Erstellen von WCF-Diensten für ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
ms.openlocfilehash: 8c82d4c61b32572fd1ad7d8f19e939273cc2280b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599307"
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a>Erstellen von WCF-Diensten für ASP.NET AJAX

Microsoft ASP.NET AJAX ermöglicht es Ihnen, zügig Webseiten zu erstellen, die mit reaktionsschnellen und vertrauten Benutzeroberflächenelementen eine hohe Benutzerfreundlichkeit bieten. ASP.NET AJAX bietet Bibliotheken mit Clientskripts, in denen browserübergreifende ECMAScript (JavaScript)- und Dynamic&#160;HTML (DHTML)-Technologien integriert sind. Außerdem sind diese Funktionen in die serverbasierte ASP.NET&#160;2.0-Entwicklungsplattform integriert. Durch die Verwendung von ASP.NET AJAX können Sie die Benutzerfreundlichkeit und die Effizienz Ihrer Webanwendungen verbessern.

ASP.NET AJAX besteht aus Clientskriptbibliotheken und Serverkomponenten, die zu einem robusten Entwicklungsframework integriert sind. So greifen Sie über eine ASP.NET-Seite auf einen Dienst zu: Sobald die Dienst-URL des ASP.NET Script Manager-Steuerelements auf der Seite hinzugefügt wurde, können Dienstvorgänge anhand von JavaScript-Code aufgerufen werden. Dieser Code gleicht einem normalen JavaScript-Funktionsaufruf.

Die meisten Windows Communication Foundation (WCF)-Dienste können als Dienst verfügbar gemacht werden, der mit ASP.NET AJAX kompatibel ist, indem ein entsprechender ASP.NET AJAX-Endpunkt hinzugefügt wird.

Wenn Sie Visual Studio verwenden, können Sie eine vorgefertigte Vorlage für AJAX-fähige WCF-Dienste verwenden, die im Dialogfeld **Neues Element hinzufügen** verfügbar sind, wenn Sie mit ASP.NET-Websites oder-Webanwendungen arbeiten.

Wenn Sie die Visual&#160;Studio-Vorlagen nicht verwenden, gibt es zwei Möglichkeiten, einen ASP.NET AJAX-Endpunkt zu erstellen:

- Erstellen Sie den Endpunkt mithilfe dynamischer Hostaktivierung, ohne eine Konfiguration zu verwenden. Dies ist der einfachste Ansatz, wenn Sie mit dem WCF-Konfigurationssystem nicht vertraut sind. Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung der Konfiguration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).

- Fügen Sie einem WCF-Dienst mithilfe der Konfiguration einen AJAX-aktivierten Endpunkt hinzu. Weitere Informationen finden Sie unter Vorgehens [Weise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).

Das in der [Übersicht über das WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model-overview.md) beschriebene webprogrammier Modell kann mit ASP.NET AJAX-Diensten verwendet werden. Dies gilt insbesondere in folgenden Fällen:

- Sie können das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut und das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut verwenden, um zwischen HTTP GET und HTTP POST-Verben auszuwählen. Wenn sie richtig verwendet werden, kann die Leistung Ihrer Anwendung bedeutend verbessert werden. Weitere Informationen finden Sie unter Gewusst [wie: auswählen zwischen HTTP Post-und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte](http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).

- Sie können die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft und die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft verwenden, damit Ihr Dienst XML-Daten anstelle der standardmäßigen JavaScript Object Notation (JSON) zurückgibt. Wenn dies für das ASP.NET AJAX-Framework ausgeführt wird, empfängt der JavaScript-Client ein XML DOM-Objekt.

  > [!WARNING]
  > Der Vorgang muss dafür den Inhaltstyp auf Text/XML festlegen. Andernfalls empfängt der JavaScript-Client eine Zeichenfolge mit dem XML-Objekt statt eines XML DOM-Objekts.

    Das folgende Beispiel zeigt einen Vorgang, der XML-Daten zurückgibt, für die der Inhaltstyp richtig festgelegt wurde:

  ```csharp
  [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]
  public XElement GetData()
  {
      XElement x;
      //Get some data here...

      WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";
      return x;
  }
  ```

- Es können keine weiteren Eigenschaften für das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut und das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut geändert werden, wenn die Kompatibilität mit ASP.NET AJAX erforderlich ist. Weitere Aspekte des Webprogrammiermodells können verwendet werden, sofern die ASP.NET AJAX-Aufrufkonventionen nicht verletzt werden.

 Erweiterte Szenarien erfordern einige zusätzliche Details der AJAX-Unterstützung in WCF:

- Informationen dazu, wie Daten zwischen einem AJAX-Seiten Client und einem WCF-Dienst mithilfe von JavaScript übertragen werden, und ausführliche Informationen dazu, wie .NET Framework Typen JavaScript-Typen zugeordnet werden, finden Sie [unter Unterstützung für JSON und andere Datenübertragung Formate](support-for-json-and-other-data-transfer-formats.md).

- Um ASP.NET-Funktionen nutzen zu können, beispielsweise die URL-basierte Authentifizierung und den Zugriff auf ASP.NET-Sitzungsinformationen, empfiehlt es sich, den ASP.NET-Kompatibilitätsmodus durch Konfiguration zu aktivieren.

AJAX-Endpunkte in WCF können sogar ohne das ASP.NET AJAX-Framework genutzt werden. Dies erfordert ein Verständnis der Unterstützungs Architektur der AJAX-Unterstützung in WCF. Eine Erläuterung dieser Architektur finden Sie unter [Objektmodell für WCF-Web-HTTP-Programmierung](wcf-web-http-programming-object-model.md). Ein Codebeispiel, in dem dieser Ansatz veranschaulicht wird, finden Sie unter [AJAX-Dienst mit JSON und XML](../samples/ajax-service-with-json-and-xml-sample.md).

## <a name="see-also"></a>Weitere Informationen

- [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md)
- [Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)
- [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
- [Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte](http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
