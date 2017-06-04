---
title: "System.Web.Routing-Integration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.Web.Routing-Integration
Beim Hosten eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Diensts in Internetinformationsdienste \(IIS\) fügen Sie eine SVC\-Datei in das virtuelle Verzeichnis ein.Diese SVC\-Datei gibt die zu verwendende Diensthostfactory sowie die Klasse an, die den Dienst implementiert.Beim Senden von Anforderungen an den Dienst geben Sie die SVC\-Datei im URI an, z. B.: http:\/\/contoso.com\/EmployeeServce.svc.Für Programmierer, die REST\-Dienste schreiben, ist dieser Typ von URI nicht optimal.URIs für REST\-Dienste geben eine bestimmte Ressource an und verfügen normalerweise nicht über Erweiterungen.Mithilfe der <xref:System.Web.Routing>\-Integrationsfunktion können Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-REST\-Dienst hosten, der auf URIs ohne Erweiterung reagiert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Routing finden Sie unter [ASP.NET\-Routing](http://go.microsoft.com/fwlink/?LinkId=184660) und im Beispiel [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md).  
  
## Verwenden der System.Web.Routing\-Integration  
 Für die <xref:System.Web.Routing>\-Integrationsfunktion verwenden Sie die <xref:System.ServiceModel.Activation.ServiceRoute>\-Klasse, um eine oder mehrere Routen zu erstellen und diese dem <xref:System.Web.Routing.RouteTable>\-Objekt in einer Global.asax\-Datei hinzuzufügen.Diese Routen geben die relativen URIs an, auf die der Dienst reagiert.Dies wird im folgenden Beispiel veranschaulicht.  
  
```  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));   
   }  
</script>  
  
```  
  
 Hier werden alle Anforderungen mit einem relativen URI, die mit "Customers" beginnen, an den `Service`\-Dienst weitergeleitet.  
  
 In der Datei "Web.config" müssen Sie das `System.Web.Routing.UrlRoutingModule`\-Modul hinzufügen, das `runAllManagedModulesForAllRequests`\-Attribut auf `true` setzen und dem `<system.webServer>`\-Element den `UrlRoutingHandler`\-Handler hinzufügen. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 Es werden ein Modul und ein Handler geladen, die für das Routing erforderlich sind.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Routing](../../../../docs/framework/wcf/feature-details/routing.md).Außerdem müssen Sie das `aspNetCompatibilityEnabled`\-Attribut wie im folgenden Beispiel gezeigt im `<serviceHostingEnvironment>`\-Element auf `true` setzen.  
  
```  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 Die Klasse, die den Dienst implementiert, muss die ASP.NET\-Kompatibilitätsanforderungen wie im folgenden Beispiel gezeigt aktivieren.  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## Siehe auch  
 [WCF\-Web\-HTTP\-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [ASP.NET\-Routing](http://go.microsoft.com/fwlink/?LinkId=184660)