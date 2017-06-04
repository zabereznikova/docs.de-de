---
title: "Vorgehensweise: Ausw&#228;hlen zwischen HTTP POST- und HTTP GET-Anforderungen f&#252;r ASP.NET AJAX-Endpunkte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Vorgehensweise: Ausw&#228;hlen zwischen HTTP POST- und HTTP GET-Anforderungen f&#252;r ASP.NET AJAX-Endpunkte
Mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie einen Dienst erstellen, der einen ASP.NET AJAX\-aktivierten Endpunkt verfügbar macht, der auf einer Client\-Website von JavaScript aufgerufen werden kann.  Die grundlegenden Verfahren für die Erstellung solcher Dienste werden in [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX\-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) und [Vorgehensweise: Hinzufügen eines ASP.NET AJAX\-Endpunkts ohne Verwendung einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md) behandelt.  
  
 ASP.NET AJAX unterstützt Vorgänge, die HTTP POST\- und HTTP GET\-Verben verwenden, wobei HTTP POST der Standard ist.  Wenn Sie einen Vorgang erstellen, der keine Nebeneffekte hat und Daten zurückgibt, die sich selten oder niemals ändern, können Sie stattdessen HTTP GET verwenden.  Die Ergebnisse von GET\-Vorgängen können zwischengespeichert werden, was bedeutet, dass mehrere Aufrufe des gleichen Vorgangs zu nur einer Anforderung an den Dienst zusammengefasst werden können.  Diese Zwischenspeicherung wird nicht von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vorgenommen, sondern kann auf jeder Ebene stattfinden \(im Browser des Benutzers, auf einem Proxyserver und auf anderen Ebenen\). Die Zwischenspeicherung ist dann vorteilhaft, wenn Sie die Leistung des Diensts erhöhen möchten. Sie ist aber möglicherweise inakzeptabel, wenn sich die Daten häufig ändern oder wenn der Vorgang irgendeine Aktion ausführt.  
  
 Wenn Sie beispielsweise einen Dienst für die Verwaltung der Musikbibliothek eines Benutzers entwickeln, ist es für einen Vorgang, der auf der Basis des Albumtitels den Künstler ermittelt, sinnvoll, GET zu verwenden. Ein Vorgang jedoch, der ein Album in die Sammlung des Benutzers einfügt, muss POST verwenden.  
  
 Verwenden Sie zur Steuerung der Lebensdauer des Zwischenspeichers den <xref:System.ServiceModel.Web.OutgoingWebResponseContext>\-Typ.  Wenn Sie beispielsweise einen Dienst entwickeln, der stündlich aktualisierte Wettervorhersagen zurückgibt, könnten Sie GET verwenden, jedoch die Lebensdauer des Zwischenspeichers auf eine Stunde oder weniger beschränken, damit die Benutzer des Diensts keine veralteten Daten erhalten.  
  
 Wenn Sie auf Dienste von einer ASP.NET AJAX\-Seite zugreifen, die das Skript\-Manager\-Steuerelement verwendet, ist es gleichgültig, ob der Vorgang GET oder POST verwendet &\#8211; der Skript\-Manager stellt sicher, dass der korrekte Anforderungstyp ausgegeben wird.  
  
 HTTP GET\-Vorgänge verwenden alle von POST\-Vorgängen unterstützten Eingabeparameter, einschließlich komplexer Datenvertragstypen.  In den meisten Fällen ist es jedoch empfehlenswert, zu viele oder zu komplexe Parameter in GET\-Vorgängen zu vermeiden, da sie die Effizienz der Zwischenspeicherung vermindern.  
  
 In diesem Thema wird gezeigt, wie zwischen GET und POST ausgewählt wird, indem den relevanten Vorgängen das <xref:System.ServiceModel.Web.WebGetAttribute>\- oder das <xref:System.ServiceModel.Web.WebInvokeAttribute>\-Attribut im Dienstvertrag hinzugefügt wird.  Die anderen zur Ausführung eines Diensts erforderlichen Schritte \(Implementieren, Konfigurieren und Hosten des Diensts\) sind den Schritten ähnlich, die für jeden ASP.NET AJAX\-Dienst in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgeführt werden müssen.  
  
 Ein mit dem <xref:System.ServiceModel.Web.WebGetAttribute> markierter Vorgang verwendet immer eine GET\-Anforderung.  Ein mit dem <xref:System.ServiceModel.Web.WebInvokeAttribute> oder mit keinem der beiden Attribute markierter Vorgang verwendet eine POST\-Anforderung.  Das <xref:System.ServiceModel.Web.WebInvokeAttribute> erlaubt über die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>\-Eigenschaft die Verwendung anderer HTTP\-Verben als GET und POST \(etwa PUT und DELETE\).  Diese Verben werden jedoch von ASP.NET AJAX nicht unterstützt.  Verwenden Sie die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>\-Eigenschaft nicht, wenn Sie vorhaben, den Dienst von ASP.NET\-Seiten aus aufzurufen, die das Skript\-Manager\-Steuerelement verwenden.  
  
 Ein funktionsfähiges Beispiel für das Umschalten auf GET finden Sie unter [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
 Ein Beispiel, in dem POST verwendet wird, finden Sie unter [AJAX\-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
### So erstellen Sie einen WCF\-Dienst, der auf HTTP GET\- oder HTTP POST\-Anforderungen reagiert  
  
1.  Definieren Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Basisdienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut gekennzeichnet ist.  Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>.  Fügen Sie das <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut hinzu, um festzulegen, dass ein Vorgang auf HTTP GET\-Anforderungen reagieren sollte.  Sie können auch das <xref:System.ServiceModel.Web.WebInvokeAttribute>\-Attribut hinzufügen, um explizit die Auswahl von HTTP POST festzulegen, oder Sie geben überhaupt kein Attribut an, wodurch standardmäßig HTTP POST verwendet wird.  
  
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
  
2.  Implementieren Sie den `IMusicService`\-Dienstvertrag mit `MusicService`.  
  
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
  
3.  Erstellen Sie eine neue Datei mit einer SVC\-Erweiterung in der Anwendung.  Bearbeiten Sie diese Datei, indem Sie die entsprechenden [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\-Direktiveninformationen für den Dienst hinzufügen.  Geben Sie in der [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\-Direktive an, dass ein <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> verwendet wird, um einen ASP.NET AJAX\-Endpunkt automatisch zu konfigurieren.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
### So rufen Sie den Dienst auf  
  
1.  Sie können die GET\-Vorgänge Ihres Diensts ohne irgendeinen Clientcode testen, indem Sie den Browser verwenden.  Ist Ihr Dienst beispielsweise unter der Adresse "http:\/\/example.com\/service.svc" konfiguriert, dann geben Sie "http:\/\/example.com\/service.svc\/LookUpArtist?album\=SomeAlbum" in die Adressleiste des Browsers ein, um den Dienst aufzurufen und dessen Antwort herunterzuladen und anzuzeigen.  
  
2.  Sie können Dienste mit GET\-Vorgängen auf gleiche Weise wie jeden anderen ASP.NET AJAX\-Dienst verwenden &\#8211; indem Sie die Dienst\-URL in die Scripts\-Auflistung des ASP.NET AJAX Script Manager\-Steuerelements eingeben.  Ein Beispiel dafür finden Sie unter [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
## Siehe auch  
 [Erstellen von WCF\-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [Vorgehensweise: Migrieren AJAX\-aktivierter ASP.NET\-Webdienste nach WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)