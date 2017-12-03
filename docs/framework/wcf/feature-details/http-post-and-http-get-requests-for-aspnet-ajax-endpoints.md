---
title: "Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 340f06c760ec4af6427343578790a8dad2d5dd62
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte
Mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie einen Dienst erstellen, der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der auf einer Client-Website von JavaScript aufgerufen werden kann. Erläutert die grundlegenden Verfahren zum Erstellen von Diensten [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) und [wie: Hinzufügen einer ASP.NET AJAX-Endpunkt ohne mithilfe der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 ASP.NET AJAX unterstützt Vorgänge, die HTTP POST- und HTTP GET-Verben verwenden, wobei HTTP POST der Standard ist. Wenn Sie einen Vorgang erstellen, der keine Nebeneffekte hat und Daten zurückgibt, die sich selten oder niemals ändern, können Sie stattdessen HTTP GET verwenden. Die Ergebnisse von GET-Vorgängen können zwischengespeichert werden, was bedeutet, dass mehrere Aufrufe des gleichen Vorgangs zu nur einer Anforderung an den Dienst zusammengefasst werden können. Diese Zwischenspeicherung wird nicht von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vorgenommen, sondern kann auf jeder Ebene stattfinden (im Browser des Benutzers, auf einem Proxyserver und auf anderen Ebenen). Die Zwischenspeicherung ist dann vorteilhaft, wenn Sie die Leistung des Diensts erhöhen möchten. Sie ist aber möglicherweise inakzeptabel, wenn sich die Daten häufig ändern oder wenn der Vorgang irgendeine Aktion ausführt.  
  
 Wenn Sie beispielsweise einen Dienst für die Verwaltung der Musikbibliothek eines Benutzers entwickeln, ist es für einen Vorgang, der auf der Basis des Albumtitels den Künstler ermittelt, sinnvoll, GET zu verwenden. Ein Vorgang jedoch, der ein Album in die Sammlung des Benutzers einfügt, muss POST verwenden.  
  
 Verwenden Sie zur Steuerung der Lebensdauer des Zwischenspeichers den <xref:System.ServiceModel.Web.OutgoingWebResponseContext>-Typ. Wenn Sie beispielsweise einen Dienst entwickeln, der stündlich aktualisierte Wettervorhersagen zurückgibt, könnten Sie GET verwenden, jedoch die Lebensdauer des Zwischenspeichers auf eine Stunde oder weniger beschränken, damit die Benutzer des Diensts keine veralteten Daten erhalten.  
  
 Wenn Sie auf Dienste von einer ASP.NET AJAX-Seite zugreifen, die das Skript-Manager-Steuerelement verwendet, ist es gleichgültig, ob der Vorgang GET oder POST verwendet &#8211; der Skript-Manager stellt sicher, dass der korrekte Anforderungstyp ausgegeben wird.  
  
 HTTP GET-Vorgänge verwenden alle von POST-Vorgängen unterstützten Eingabeparameter, einschließlich komplexer Datenvertragstypen. In den meisten Fällen ist es jedoch empfehlenswert, zu viele oder zu komplexe Parameter in GET-Vorgängen zu vermeiden, da sie die Effizienz der Zwischenspeicherung vermindern.  
  
 In diesem Thema wird gezeigt, wie zwischen GET und POST ausgewählt wird, indem den relevanten Vorgängen das <xref:System.ServiceModel.Web.WebGetAttribute>- oder das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut im Dienstvertrag hinzugefügt wird. Die anderen zur Ausführung eines Diensts erforderlichen Schritte (Implementieren, Konfigurieren und Hosten des Diensts) sind den Schritten ähnlich, die für jeden ASP.NET AJAX-Dienst in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgeführt werden müssen.  
  
 Ein mit dem <xref:System.ServiceModel.Web.WebGetAttribute> markierter Vorgang verwendet immer eine GET-Anforderung. Ein mit dem <xref:System.ServiceModel.Web.WebInvokeAttribute> oder mit keinem der beiden Attribute markierter Vorgang verwendet eine POST-Anforderung. Das <xref:System.ServiceModel.Web.WebInvokeAttribute> erlaubt über die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft die Verwendung anderer HTTP-Verben als GET und POST (etwa PUT und DELETE). Diese Verben werden jedoch von ASP.NET AJAX nicht unterstützt. Verwenden Sie die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft nicht, wenn Sie vorhaben, den Dienst von ASP.NET-Seiten aus aufzurufen, die das Skript-Manager-Steuerelement verwenden.  
  
 Ein funktionsfähiges Beispiel der Wechsel zum Abrufen, finden Sie unter der [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel.  
  
 Ein Beispiel, das POST verwendet, finden Sie unter der [AJAX-Dienst mithilfe von HTTP-POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) Beispiel.  
  
### <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>So erstellen Sie einen WCF-Dienst, der auf HTTP GET- oder HTTP POST-Anforderungen reagiert  
  
1.  Definieren Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Basisdienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut gekennzeichnet ist. Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>. Fügen Sie das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut hinzu, um festzulegen, dass ein Vorgang auf HTTP GET-Anforderungen reagieren sollte. Sie können auch das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut hinzufügen, um explizit die Auswahl von HTTP POST festzulegen, oder Sie geben überhaupt kein Attribut an, wodurch standardmäßig HTTP POST verwendet wird.  
  
    ```  
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
  
2.  Implementieren Sie den `IMusicService`-Dienstvertrag mit `MusicService`.  
  
    ```  
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3.  Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung. Bearbeiten Sie diese Datei durch Hinzufügen der entsprechenden [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie Informationen für den Dienst. Angeben, die die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in verwendet werden soll die [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie automatisch einen ASP.NET AJAX-Endpunkt zu konfigurieren.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
### <a name="to-call-the-service"></a>So rufen Sie den Dienst auf  
  
1.  Sie können die GET-Vorgänge Ihres Diensts ohne irgendeinen Clientcode testen, indem Sie den Browser verwenden. Ist Ihr Dienst beispielsweise unter der Adresse "http://example.com/service.svc" konfiguriert, dann geben Sie "http://example.com/service.svc/LookUpArtist?album=SomeAlbum" in die Adressleiste des Browsers ein, um den Dienst aufzurufen und dessen Antwort herunterzuladen und anzuzeigen.  
  
2.  Sie können Dienste mit GET-Vorgängen auf gleiche Weise wie jeden anderen ASP.NET AJAX-Dienst verwenden &#8211; indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben. Ein Beispiel finden Sie die [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von WCF-Diensten für ASP.NET-AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
