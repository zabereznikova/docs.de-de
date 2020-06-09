---
title: 'Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 15d7ad43ce9120e97aba9119aff6a6c1a19f301f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596915"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte

Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der von JavaScript auf einer Client Website aufgerufen werden kann. Die grundlegenden Verfahren zum entwickeln solcher Dienste finden Sie unter Gewusst [wie: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) und Gewusst [wie: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung der Konfiguration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 ASP.NET AJAX unterstützt Vorgänge, die HTTP POST- und HTTP GET-Verben verwenden, wobei HTTP POST der Standard ist. Wenn Sie einen Vorgang erstellen, der keine Nebeneffekte hat und Daten zurückgibt, die sich selten oder niemals ändern, können Sie stattdessen HTTP GET verwenden. Die Ergebnisse von GET-Vorgängen können zwischengespeichert werden, was bedeutet, dass mehrere Aufrufe des gleichen Vorgangs zu nur einer Anforderung an den Dienst zusammengefasst werden können. Die Zwischenspeicherung erfolgt nicht von WCF, kann jedoch auf jeder Ebene erfolgen (im Browser eines Benutzers, auf einem Proxy Server und auf anderen Ebenen). Das Caching ist von Vorteil, wenn Sie die Leistung des Dienstanbieter steigern möchten, dies ist jedoch möglicherweise nicht akzeptabel, wenn sich Daten häufig ändern oder wenn der Vorgang eine Aktion ausführt.  
  
 Wenn Sie beispielsweise einen Dienst für die Verwaltung der Musikbibliothek eines Benutzers entwickeln, ist es für einen Vorgang, der auf der Basis des Albumtitels den Künstler ermittelt, sinnvoll, GET zu verwenden. Ein Vorgang jedoch, der ein Album in die Sammlung des Benutzers einfügt, muss POST verwenden.  
  
 Verwenden Sie zur Steuerung der Lebensdauer des Zwischenspeichers den <xref:System.ServiceModel.Web.OutgoingWebResponseContext>-Typ. Wenn Sie beispielsweise einen Dienst entwickeln, der stündlich aktualisierte Wettervorhersagen zurückgibt, könnten Sie GET verwenden, jedoch die Lebensdauer des Zwischenspeichers auf eine Stunde oder weniger beschränken, damit die Benutzer des Diensts keine veralteten Daten erhalten.  
  
 Wenn Sie auf Dienste von einer ASP.NET AJAX-Seite zugreifen, die das Skript-Manager-Steuerelement verwendet, ist es gleichgültig, ob der Vorgang GET oder POST verwendet &#8211; der Skript-Manager stellt sicher, dass der korrekte Anforderungstyp ausgegeben wird.  
  
 HTTP GET-Vorgänge verwenden alle von POST-Vorgängen unterstützten Eingabeparameter, einschließlich komplexer Datenvertragstypen. In den meisten Fällen ist es jedoch empfehlenswert, zu viele oder zu komplexe Parameter in GET-Vorgängen zu vermeiden, da sie die Effizienz der Zwischenspeicherung vermindern.  
  
 In diesem Thema wird gezeigt, wie zwischen GET und POST ausgewählt wird, indem den relevanten Vorgängen das <xref:System.ServiceModel.Web.WebGetAttribute>- oder das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut im Dienstvertrag hinzugefügt wird. Die anderen Schritte (zum implementieren, konfigurieren und Hosten des Diensts), die zum Ausführen des Diensts erforderlich sind, ähneln denen, die von einem beliebigen ASP.NET AJAX-Dienst in WCF verwendet werden.  
  
 Ein mit dem <xref:System.ServiceModel.Web.WebGetAttribute> markierter Vorgang verwendet immer eine GET-Anforderung. Ein mit dem <xref:System.ServiceModel.Web.WebInvokeAttribute> oder mit keinem der beiden Attribute markierter Vorgang verwendet eine POST-Anforderung. Das <xref:System.ServiceModel.Web.WebInvokeAttribute> erlaubt über die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft die Verwendung anderer HTTP-Verben als GET und POST (etwa PUT und DELETE). Diese Verben werden jedoch von ASP.NET AJAX nicht unterstützt. Verwenden Sie die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft nicht, wenn Sie vorhaben, den Dienst von ASP.NET-Seiten aus aufzurufen, die das Skript-Manager-Steuerelement verwenden.  
  
 Ein funktionierendes Beispiel für den Wechsel zu Get finden Sie im Beispiel für den [grundlegenden AJAX-Dienst](../samples/basic-ajax-service.md) .  
  
 Ein Beispiel für die Verwendung von Post finden Sie im Beispiel für den [AJAX-Dienst mit HTTP Post](../samples/ajax-service-using-http-post.md) .  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>So erstellen Sie einen WCF-Dienst, der auf HTTP GET- oder HTTP POST-Anforderungen reagiert
  
1. Definieren Sie einen grundlegenden WCF-Dienstvertrag mit einer mit dem-Attribut markierten Schnittstelle <xref:System.ServiceModel.ServiceContractAttribute> . Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Fügen Sie das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut hinzu, um festzulegen, dass ein Vorgang auf HTTP GET-Anforderungen reagieren sollte. Sie können auch das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut hinzufügen, um explizit die Auswahl von HTTP POST festzulegen, oder Sie geben überhaupt kein Attribut an, wodurch standardmäßig HTTP POST verwendet wird.
  
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
  
3. Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung. Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktiveninformationen für den Dienst hinzufügen. Geben Sie an, dass <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in der [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive verwendet werden soll, um einen ASP.NET AJAX-Endpunkt automatisch zu konfigurieren.  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1. Sie können die GET-Vorgänge Ihres Diensts ohne irgendeinen Clientcode testen, indem Sie den Browser verwenden. Wenn Ihr Dienst z. b. an der Adresse konfiguriert ist `http://example.com/service.svc` , wird `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` der Dienst von der Eingabe in die Adressleiste des Browsers aufgerufen und bewirkt, dass die Antwort heruntergeladen oder angezeigt wird.
  
2. Sie können Dienste mit GET-Vorgängen auf gleiche Weise wie jeden anderen ASP.NET AJAX-Dienst verwenden &#8211; indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie unter [grundlegender AJAX-Dienst](../samples/basic-ajax-service.md).
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von WCF-Diensten für ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md)
- [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
