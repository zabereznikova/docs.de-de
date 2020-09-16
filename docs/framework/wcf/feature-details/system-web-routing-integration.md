---
title: System.Web.Routing-Integration
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 6e67aa4a790edeb367b099d4a94f465f1e7b9bcc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554774"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="507ba-102">System.Web.Routing-Integration</span><span class="sxs-lookup"><span data-stu-id="507ba-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="507ba-103">Wenn Sie einen Windows Communication Foundation (WCF)-Dienst in Internet Informationsdienste (IIS) gehostet haben, platzieren Sie eine SVC-Datei im virtuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="507ba-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="507ba-104">Diese SVC-Datei gibt die zu verwendende Diensthostfactory sowie die Klasse an, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="507ba-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="507ba-105">Wenn Sie Anforderungen an den Dienst senden, geben Sie die. svc-Datei im URI an, z `http://contoso.com/EmployeeServce.svc` . b.:.</span><span class="sxs-lookup"><span data-stu-id="507ba-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="507ba-106">Für Programmierer, die REST-Dienste schreiben, ist dieser Typ von URI nicht optimal.</span><span class="sxs-lookup"><span data-stu-id="507ba-106">For programmers writing REST services, this type of URI is not optimal.</span></span> <span data-ttu-id="507ba-107">URIs für REST-Dienste geben eine bestimmte Ressource an und verfügen normalerweise nicht über Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="507ba-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="507ba-108">Mithilfe der- <xref:System.Web.Routing> Integrationsfunktion können Sie einen WCF-REST-Dienst hosten, der auf URIs ohne Erweiterung reagiert.</span><span class="sxs-lookup"><span data-stu-id="507ba-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="507ba-109">Weitere Informationen zum Routing finden Sie unter [ASP.NET Routing](/previous-versions/aspnet/cc668201(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="507ba-109">For more information about routing see [ASP.NET Routing](/previous-versions/aspnet/cc668201(v=vs.100)).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="507ba-110">Verwenden der System.Web.Routing-Integration</span><span class="sxs-lookup"><span data-stu-id="507ba-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="507ba-111">Für die <xref:System.Web.Routing>-Integrationsfunktion verwenden Sie die <xref:System.ServiceModel.Activation.ServiceRoute>-Klasse, um eine oder mehrere Routen zu erstellen und diese dem <xref:System.Web.Routing.RouteTable>-Objekt in einer Global.asax-Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="507ba-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="507ba-112">Diese Routen geben die relativen URIs an, auf die der Dienst reagiert.</span><span class="sxs-lookup"><span data-stu-id="507ba-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="507ba-113">Das folgende Beispiel zeigt die erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="507ba-113">The following example shows how to do this.</span></span>  
  
```aspx-csharp  
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
  
 <span data-ttu-id="507ba-114">Hier werden alle Anforderungen mit einem relativen URI, die mit "Customers" beginnen, an den `Service`-Dienst weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="507ba-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="507ba-115">In der Datei "Web.config" müssen Sie das `System.Web.Routing.UrlRoutingModule`-Modul hinzufügen, das `runAllManagedModulesForAllRequests`-Attribut auf `true` setzen und dem `UrlRoutingHandler`-Element den `<system.webServer>`-Handler hinzufügen. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="507ba-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="507ba-116">Es werden ein Modul und ein Handler geladen, die für das Routing erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="507ba-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="507ba-117">Weitere Informationen finden Sie unter [Routing](routing.md).</span><span class="sxs-lookup"><span data-stu-id="507ba-117">For more information, see [Routing](routing.md).</span></span> <span data-ttu-id="507ba-118">Außerdem müssen Sie das `aspNetCompatibilityEnabled`-Attribut wie im folgenden Beispiel gezeigt im `true`-Element auf `<serviceHostingEnvironment>` setzen.</span><span class="sxs-lookup"><span data-stu-id="507ba-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="507ba-119">Die Klasse, die den Dienst implementiert, muss die ASP.NET-Kompatibilitätsanforderungen wie im folgenden Beispiel gezeigt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="507ba-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="507ba-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="507ba-120">See also</span></span>

- [<span data-ttu-id="507ba-121">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="507ba-121">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- <span data-ttu-id="507ba-122">[ASP.NET-Routing](/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="507ba-122">[ASP.NET Routing](/previous-versions/aspnet/cc668201(v=vs.100))</span></span>
