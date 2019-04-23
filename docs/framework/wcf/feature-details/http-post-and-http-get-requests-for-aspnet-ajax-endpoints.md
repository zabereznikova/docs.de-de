---
title: 'Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 33763a77d1ab1c82af9b9e1fb9c42d72392f8798
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091277"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte

Windows Communication Foundation (WCF) ermöglicht Ihnen die Erstellung ein Diensts, das einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der auf einer Client-Website von JavaScript aufgerufen werden können. Erläutert die grundlegenden Verfahren zum Erstellen dieser Dienste [Vorgehensweise: Verwenden Sie die Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) und [Vorgehensweise: Hinzufügen ein ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 ASP.NET AJAX unterstützt Vorgänge, die HTTP POST- und HTTP GET-Verben verwenden, wobei HTTP POST der Standard ist. Wenn Sie einen Vorgang erstellen, der keine Nebeneffekte hat und Daten zurückgibt, die sich selten oder niemals ändern, können Sie stattdessen HTTP GET verwenden. Die Ergebnisse von GET-Vorgängen können zwischengespeichert werden, was bedeutet, dass mehrere Aufrufe des gleichen Vorgangs zu nur einer Anforderung an den Dienst zusammengefasst werden können. Das Zwischenspeichern erfolgt nicht durch WCF, jedoch kann stattfinden auf jeder Ebene (im Browser eines Benutzers, auf einen Proxy-Server und auf anderen Ebenen.) Die Zwischenspeicherung ist dann vorteilhaft, wenn Sie die Leistung des Diensts erhöhen möchten. Sie ist aber möglicherweise inakzeptabel, wenn sich die Daten häufig ändern oder wenn der Vorgang irgendeine Aktion ausführt.  
  
 Wenn Sie beispielsweise einen Dienst für die Verwaltung der Musikbibliothek eines Benutzers entwickeln, ist es für einen Vorgang, der auf der Basis des Albumtitels den Künstler ermittelt, sinnvoll, GET zu verwenden. Ein Vorgang jedoch, der ein Album in die Sammlung des Benutzers einfügt, muss POST verwenden.  
  
 Verwenden Sie zur Steuerung der Lebensdauer des Zwischenspeichers den <xref:System.ServiceModel.Web.OutgoingWebResponseContext>-Typ. Wenn Sie beispielsweise einen Dienst entwickeln, der stündlich aktualisierte Wettervorhersagen zurückgibt, könnten Sie GET verwenden, jedoch die Lebensdauer des Zwischenspeichers auf eine Stunde oder weniger beschränken, damit die Benutzer des Diensts keine veralteten Daten erhalten.  
  
 Wenn Sie auf Dienste von einer ASP.NET AJAX-Seite zugreifen, die das Skript-Manager-Steuerelement verwendet, ist es gleichgültig, ob der Vorgang GET oder POST verwendet &amp;#8211; der Skript-Manager stellt sicher, dass der korrekte Anforderungstyp ausgegeben wird.  
  
 HTTP GET-Vorgänge verwenden alle von POST-Vorgängen unterstützten Eingabeparameter, einschließlich komplexer Datenvertragstypen. In den meisten Fällen ist es jedoch empfehlenswert, zu viele oder zu komplexe Parameter in GET-Vorgängen zu vermeiden, da sie die Effizienz der Zwischenspeicherung vermindern.  
  
 In diesem Thema wird gezeigt, wie zwischen GET und POST ausgewählt wird, indem den relevanten Vorgängen das <xref:System.ServiceModel.Web.WebGetAttribute>- oder das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut im Dienstvertrag hinzugefügt wird. Die anderen Schritte (zum Implementieren, konfigurieren und Hosten des Diensts), die erforderlich sind, um den Dienst ausführen ähneln denen, die von einem ASP.NET AJAX-Dienst in WCF verwendet.  
  
 Ein mit dem <xref:System.ServiceModel.Web.WebGetAttribute> markierter Vorgang verwendet immer eine GET-Anforderung. Ein mit dem <xref:System.ServiceModel.Web.WebInvokeAttribute> oder mit keinem der beiden Attribute markierter Vorgang verwendet eine POST-Anforderung. Das <xref:System.ServiceModel.Web.WebInvokeAttribute> erlaubt über die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft die Verwendung anderer HTTP-Verben als GET und POST (etwa PUT und DELETE). Diese Verben werden jedoch von ASP.NET AJAX nicht unterstützt. Verwenden Sie die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft nicht, wenn Sie vorhaben, den Dienst von ASP.NET-Seiten aus aufzurufen, die das Skript-Manager-Steuerelement verwenden.  
  
 Ein funktionsfähiges Beispiel Umschalten auf GET finden Sie unter den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel.  
  
 Ein Beispiel, POST verwendet, finden Sie unter den [AJAX-Dienst mithilfe von HTTP-POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) Beispiel.  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>So erstellen Sie einen WCF-Dienst, der auf HTTP GET- oder HTTP POST-Anforderungen reagiert
  
1. Definieren ein grundlegenden WCF-Dienstvertrags mit einer Schnittstelle markiert mit dem <xref:System.ServiceModel.ServiceContractAttribute> Attribut. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Fügen Sie das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut hinzu, um festzulegen, dass ein Vorgang auf HTTP GET-Anforderungen reagieren sollte. Sie können auch das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut hinzufügen, um explizit die Auswahl von HTTP POST festzulegen, oder Sie geben überhaupt kein Attribut an, wodurch standardmäßig HTTP POST verwendet wird.
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implementieren Sie den `IMusicService`-Dienstvertrag mit `MusicService`.
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung. Bearbeiten Sie diese Datei durch Hinzufügen des entsprechenden [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -direktiveninformationen für den Dienst. Angeben, die die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in verwendet werden soll die [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie, um einen ASP.NET AJAX-Endpunkt automatisch zu konfigurieren.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1. Sie können die GET-Vorgänge Ihres Diensts ohne irgendeinen Clientcode testen, indem Sie den Browser verwenden. Angenommen, Ihr Dienst konfiguriert ist, auf die `http://example.com/service.svc` Adresse ein, klicken Sie dann Eingabe `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` in den Browser Adressleiste den Dienst aufruft, und führt dazu, dass die Antwort, heruntergeladen oder angezeigt werden soll.
  
2. Sie können Dienste mit GET-Vorgängen auf gleiche Weise wie jeden anderen ASP.NET AJAX-Dienst verwenden &amp;#8211; indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie unter den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md).
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Vorgehensweise: Migrate AJAX-Enabled ASP.NET Web Services to WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
