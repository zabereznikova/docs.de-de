---
title: 'Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 048408adf8678c243a225a233cb1173c9b7f869f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495550"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a><span data-ttu-id="920d3-102">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF</span><span class="sxs-lookup"><span data-stu-id="920d3-102">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>
<span data-ttu-id="920d3-103">Dieses Thema beschreibt Verfahren zum Migrieren von eines einfachen ASP.NET AJAX-Diensts mit einem entsprechenden AJAX-aktivierten Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="920d3-103">This topic outlines procedures to migrate a basic ASP.NET AJAX service to an equivalent AJAX-enabled Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="920d3-104">Es wird gezeigt, wie eine funktional äquivalente WCF-Version von ASP.NET AJAX-Diensts erstellt.</span><span class="sxs-lookup"><span data-stu-id="920d3-104">It shows how to create a functionally equivalent WCF version of an ASP.NET AJAX service.</span></span> <span data-ttu-id="920d3-105">Die beiden Dienste können dann parallel verwendet werden, oder kann der WCF-Dienst verwendet, um ASP.NET AJAX-Dienst zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="920d3-105">The two services can then be used side by side, or the WCF service can be used to replace the ASP.NET AJAX service.</span></span>  
  
 <span data-ttu-id="920d3-106">Migrieren einer vorhandenen ASP.NET AJAX bietet Service an einen WCF AJAX-Dienst die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="920d3-106">Migrating an existing ASP.NET AJAX service to a WCF AJAX service gives you the following benefits:</span></span>  
  
-   <span data-ttu-id="920d3-107">Sie können den AJAX-Dienst mit nur minimaler zusätzlicher Konfiguration als SOAP-Dienst verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="920d3-107">You can expose your AJAX service as a SOAP service with minimal extra configuration.</span></span>  
  
-   <span data-ttu-id="920d3-108">Sie können WCF-Funktionen, z. B. Ablaufverfolgung profitieren und so weiter.</span><span class="sxs-lookup"><span data-stu-id="920d3-108">You can benefit from WCF features such as tracing, and so on.</span></span>  
  
 <span data-ttu-id="920d3-109">In den folgenden Verfahren wird davon ausgegangen, dass Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="920d3-109">The following procedures assume that you are using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
 <span data-ttu-id="920d3-110">Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="920d3-110">The code that results from the procedures outlined in this topic is provided in the example following the procedures.</span></span>  
  
 <span data-ttu-id="920d3-111">Weitere Informationen zum Bereitstellen eines WCF-Diensts über einen AJAX-aktivierten Endpunkt finden Sie unter der [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="920d3-111">For more information about exposing a WCF service through an AJAX-enabled endpoint, see the [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) topic.</span></span>  
  
### <a name="to-create-and-test-the-aspnet-web-service-application"></a><span data-ttu-id="920d3-112">So erstellen und testen Sie die ASP.NET-Webdienstanwendung</span><span class="sxs-lookup"><span data-stu-id="920d3-112">To create and test the ASP.NET Web service application</span></span>  
  
1.  <span data-ttu-id="920d3-113">Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="920d3-113">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="920d3-114">Aus der **Datei** klicken Sie im Menü **neu**, klicken Sie dann **Projekt**, klicken Sie dann **Web**, und wählen Sie dann **ASP.NET-Webdienstanwendung** .</span><span class="sxs-lookup"><span data-stu-id="920d3-114">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Service Application**.</span></span>  
  
3.  <span data-ttu-id="920d3-115">Nennen Sie das Projekt `ASPHello` , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="920d3-115">Name the project `ASPHello` and click **OK**.</span></span>  
  
4.  <span data-ttu-id="920d3-116">Entfernen Sie in der Datei Service1.asmx.cs die Kommentarzeichen vor der Zeile, die `System.Web.Script.Services.ScriptService]` enthält, damit AJAX für diesen Dienst aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="920d3-116">Uncomment the line in the Service1.asmx.cs file that contains `System.Web.Script.Services.ScriptService]` to enable AJAX for this service.</span></span>  
  
5.  <span data-ttu-id="920d3-117">Aus der **erstellen** klicken Sie im Menü **Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="920d3-117">From the **Build** menu, select **Build Solution**.</span></span>  
  
6.  <span data-ttu-id="920d3-118">Aus der **Debuggen** klicken Sie im Menü **Starten ohne Debugging**.</span><span class="sxs-lookup"><span data-stu-id="920d3-118">From the **Debug** menu, select **Start Without Debugging**.</span></span>  
  
7.  <span data-ttu-id="920d3-119">Wählen Sie auf der generierten Webseite den Vorgang `HelloWorld` aus.</span><span class="sxs-lookup"><span data-stu-id="920d3-119">On the Web page generated, select the `HelloWorld` operation.</span></span>  
  
8.  <span data-ttu-id="920d3-120">Klicken Sie auf die **Invoke** Schaltfläche auf der `HelloWorld` Testseite.</span><span class="sxs-lookup"><span data-stu-id="920d3-120">Click the **Invoke** button on the `HelloWorld` test page.</span></span> <span data-ttu-id="920d3-121">Sie sollten die folgende XML-Antwort empfangen.</span><span class="sxs-lookup"><span data-stu-id="920d3-121">You should receive the following XML response.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. <span data-ttu-id="920d3-122">Diese Antwort bestätigt Ihnen, dass Sie nun über einen funktionierenden ASP.NET AJAX-Dienst verfügen und insbesondere, dass der Dienst jetzt einen Endpunkt unter Service1.asmx/HelloWorld verfügbar gemacht hat, der auf HTTP POST-Anforderungen antwortet und XML zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="920d3-122">This response confirms that you now have a functioning ASP.NET AJAX service and, in particular, that the service has now exposed an endpoint at Service1.asmx/HelloWorld that responds to HTTP POST requests and returns XML.</span></span>  
  
     <span data-ttu-id="920d3-123">Jetzt sind Sie bereit ist, konvertiert diesen Dienst, um einen WCF AJAX-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="920d3-123">Now you are ready to convert this service to use a WCF AJAX service.</span></span>  
  
### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a><span data-ttu-id="920d3-124">So erstellen Sie eine äquivalente WCF AJAX-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="920d3-124">To create an equivalent WCF AJAX service application</span></span>  
  
1.  <span data-ttu-id="920d3-125">Mit der rechten Maustaste die **ASPHello** Projekt, und wählen Sie **hinzufügen**, klicken Sie dann **neues Element**, und klicken Sie dann **AJAX-aktivierter WCF-Dienst**.</span><span class="sxs-lookup"><span data-stu-id="920d3-125">Right-click the **ASPHello** project and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="920d3-126">Benennen Sie den Dienst `WCFHello` , und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="920d3-126">Name the service `WCFHello` and click **Add**.</span></span>  
  
3.  <span data-ttu-id="920d3-127">Öffnen Sie die Datei WCFHello.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="920d3-127">Open the WCFHello.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="920d3-128">Kopieren Sie die folgende Implementierung des in der Datei Service1.asmx.cs die `HelloWorld` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="920d3-128">From Service1.asmx.cs, copy the following implementation of the `HelloWorld` operation.</span></span>  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  <span data-ttu-id="920d3-129">Fügen Sie die kopierte Implementierung des der `HelloWorld` Vorgang in die Datei WCFHello.svc.cs anstelle des folgenden Codes.</span><span class="sxs-lookup"><span data-stu-id="920d3-129">Paste to copied implementation of the `HelloWorld` operation into the WCFHello.svc.cs file in place of the following code.</span></span>  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  <span data-ttu-id="920d3-130">Geben Sie die `Namespace` -Attribut für <xref:System.ServiceModel.ServiceContractAttribute> als `WCFHello`.</span><span class="sxs-lookup"><span data-stu-id="920d3-130">Specify the `Namespace` attribute for <xref:System.ServiceModel.ServiceContractAttribute> as `WCFHello`.</span></span>  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  <span data-ttu-id="920d3-131">Hinzufügen der <xref:System.ServiceModel.Web.WebInvokeAttribute> auf die `HelloWorld` Vorgang und legen die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> -Eigenschaft zum Zurückgeben von <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span><span class="sxs-lookup"><span data-stu-id="920d3-131">Add the <xref:System.ServiceModel.Web.WebInvokeAttribute> to the `HelloWorld` operation and set the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> property to return <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span></span> <span data-ttu-id="920d3-132">Beachten Sie, dass der Standardrückgabetyp <xref:System.ServiceModel.Web.WebMessageFormat.Json> ist, sofern nichts anderes festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="920d3-132">Note that, if not set, the default return type is <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span>  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  <span data-ttu-id="920d3-133">Aus der **erstellen** klicken Sie im Menü **Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="920d3-133">From the **Build** menu, select **Build Solution**.</span></span>  
  
9. <span data-ttu-id="920d3-134">Öffnen Sie die Datei WCFHello.svc und aus der **Debuggen** klicken Sie im Menü **Starten ohne Debugging**.</span><span class="sxs-lookup"><span data-stu-id="920d3-134">Open the WCFHello.svc file and from the **Debug** menu, select **Start Without Debugging**.</span></span>  
  
10. <span data-ttu-id="920d3-135">Der Dienst macht jetzt einen Endpunkt unter `WCFHello.svc/HelloWorld`, die auf HTTP-POST-Anforderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="920d3-135">The service now exposes an endpoint at `WCFHello.svc/HelloWorld`, which responds to HTTP POST requests.</span></span> <span data-ttu-id="920d3-136">HTTP POST-Anforderungen können im Browser nicht getestet werden, aber der Endpunkt gibt die folgenden XML-Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="920d3-136">HTTP POST requests cannot be tested from the browser, but the endpoint returns XML following XML.</span></span>  
  
    ```xml  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. <span data-ttu-id="920d3-137">Die `WCFHello.svc/HelloWorld` und die `Service1.aspx/HelloWorld` Endpunkte sind jetzt funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="920d3-137">The `WCFHello.svc/HelloWorld` and the `Service1.aspx/HelloWorld` endpoints are now functionally equivalent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="920d3-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="920d3-138">Example</span></span>  
 <span data-ttu-id="920d3-139">Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird im folgenden Beispiel bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="920d3-139">The code that results from the procedures outlined in this topic is provided in the following example.</span></span>  
  
```  
//This is the ASP.NET code in the Service1.asmx.cs file.  
  
using System;  
using System.Collections;  
using System.ComponentModel;  
using System.Data;  
using System.Linq;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Linq;  
using System.Web.Script.Services;  
  
namespace ASPHello  
{  
    /// <summary>  
    /// Summary description for Service1.  
    /// </summary>  
    [WebService(Namespace = "http://tempuri.org/")]  
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
    [ToolboxItem(false)]  
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.   
    [System.Web.Script.Services.ScriptService]  
    public class Service1 : System.Web.Services.WebService  
    {  
  
        [WebMethod]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
    }  
}   
  
//This is the WCF code in the WCFHello.svc.cs file.  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace ASPHello  
{  
    [ServiceContract(Namespace = "WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class WCFHello  
    {  
        // Add [WebInvoke] attribute to use HTTP GET.  
        [OperationContract]  
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
  
        // Add more operations here and mark them with [OperationContract].  
    }  
}  
```  
  
 <span data-ttu-id="920d3-140">Der <xref:System.Xml.XmlDocument>-Typ wird vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> nicht unterstützt, da er vom <xref:System.Xml.Serialization.XmlSerializer> nicht serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="920d3-140">The <xref:System.Xml.XmlDocument> type is not supported by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because it is not serializable by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="920d3-141">Sie können entweder einen <xref:System.Xml.Linq.XDocument>-Typ verwenden oder stattdessen das <xref:System.Xml.XmlDocument.DocumentElement%2A> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="920d3-141">You can use either an <xref:System.Xml.Linq.XDocument> type, or serialize the <xref:System.Xml.XmlDocument.DocumentElement%2A> instead.</span></span>  
  
 <span data-ttu-id="920d3-142">Wenn ASMX-Webdienste aktualisiert werden und migriert Seite-an-Seite-WCF-Diensten, vermeiden Sie die Zuordnung von zwei Typen auf dem gleichen Namen auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="920d3-142">If ASMX Web services are being upgraded and migrated side-by-side to WCF services, avoid mapping two types to the same name on the client.</span></span> <span data-ttu-id="920d3-143">Denn andernfalls wird beim Serialisieren eine Ausnahme ausgelöst, wenn der gleiche Typ in einem <xref:System.Web.Services.WebMethodAttribute> und einem <xref:System.ServiceModel.ServiceContractAttribute> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="920d3-143">This causes an exception in serializers if the same type is used in a <xref:System.Web.Services.WebMethodAttribute> and a <xref:System.ServiceModel.ServiceContractAttribute>:</span></span>  
  
-   <span data-ttu-id="920d3-144">Wenn WCF-Dienst zuerst hinzugefügt wird, Aufruf der Methode ASMX-Webdienst führt dazu, dass die Ausnahme in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> , da die WCF-Formatdefinition der Reihenfolge im Proxy Vorrang hat.</span><span class="sxs-lookup"><span data-stu-id="920d3-144">If WCF service is added first, invoking the method on ASMX Web Service causes exception in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> because the WCF style definition of the order in the proxy takes precedence.</span></span>  
  
-   <span data-ttu-id="920d3-145">Wenn ASMX-Webdienst zuerst hinzugefügt wird, Aufrufen der Methode für WCF-Dienst führt dazu, dass die Ausnahme in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> , da die Webdienst-Formatdefinition der Reihenfolge im Proxy Vorrang hat.</span><span class="sxs-lookup"><span data-stu-id="920d3-145">If ASMX Web Service is added first, invoking method on WCF service causes exception in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because the Web Service style definition of the order in the proxy takes precedence.</span></span>  
  
 <span data-ttu-id="920d3-146">Es gibt bedeutende Unterschiede im Verhalten von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und dem ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span><span class="sxs-lookup"><span data-stu-id="920d3-146">There are significant differences in behavior between the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> and the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span></span> <span data-ttu-id="920d3-147">Beispielsweise stellt der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ein Wörterbuch als Array von Schlüssel-Wert-Paaren dar, wohingegen der ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> ein Wörterbuch als tatsächliche JSON-Objekte darstellt.</span><span class="sxs-lookup"><span data-stu-id="920d3-147">For example, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> represents a dictionary as an array of key/value pairs, whereas the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> represents a dictionary as actual JSON objects.</span></span> <span data-ttu-id="920d3-148">Deshalb ist das Folgende die Darstellung eines Wörterbuchs in ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="920d3-148">So the following is the dictionary represented in ASP.NET AJAX.</span></span>  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add("one", 1);  
d.Add("two", 2);  
```  
  
 <span data-ttu-id="920d3-149">Dieses Wörterbuch wird entsprechend der folgenden Liste in JSON-Objekten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="920d3-149">This dictionary is represented in JSON objects as shown in the following list:</span></span>  
  
-   <span data-ttu-id="920d3-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span><span class="sxs-lookup"><span data-stu-id="920d3-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span></span>  
  
-   <span data-ttu-id="920d3-151">{"one": 1, "two": 2} vom ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer></span><span class="sxs-lookup"><span data-stu-id="920d3-151">{"one":1,"two":2} by the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer></span></span>  
  
 <span data-ttu-id="920d3-152">Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ist insofern leistungsfähiger, als dass er Wörterbücher handhaben kann, bei denen der Schlüsseltyp keine Zeichenfolge ist. Der <xref:System.Web.Script.Serialization.JavaScriptSerializer> kann dies nicht.</span><span class="sxs-lookup"><span data-stu-id="920d3-152">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is more powerful in the sense that it can handle dictionaries where the key type is not string, while the <xref:System.Web.Script.Serialization.JavaScriptSerializer> cannot.</span></span> <span data-ttu-id="920d3-153">Letzterer ist jedoch JSON-freundlicher.</span><span class="sxs-lookup"><span data-stu-id="920d3-153">But the latter is more JSON-friendly.</span></span>  
  
 <span data-ttu-id="920d3-154">Die wichtigsten Unterschiede zwischen diesen Serialisierern werden in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="920d3-154">The significant differences between these serializers are summarized in the following table.</span></span>  
  
|<span data-ttu-id="920d3-155">Unterschiedskategorie</span><span class="sxs-lookup"><span data-stu-id="920d3-155">Category of Differences</span></span>|<span data-ttu-id="920d3-156">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="920d3-156">DataContractJsonSerializer</span></span>|<span data-ttu-id="920d3-157">ASP.NET AJAX JavaScriptSerializer</span><span class="sxs-lookup"><span data-stu-id="920d3-157">ASP.NET AJAX JavaScriptSerializer</span></span>|  
|-----------------------------|--------------------------------|---------------------------------------|  
|<span data-ttu-id="920d3-158">Deserialisieren des leeren Puffers (new byte[0]) in <xref:System.Object> (oder <xref:System.Uri> oder andere Klassen).</span><span class="sxs-lookup"><span data-stu-id="920d3-158">Deserializing the empty buffer (new byte[0]) into <xref:System.Object> (or <xref:System.Uri>, or some other classes).</span></span>|<span data-ttu-id="920d3-159">SerializationException</span><span class="sxs-lookup"><span data-stu-id="920d3-159">SerializationException</span></span>|<span data-ttu-id="920d3-160">null</span><span class="sxs-lookup"><span data-stu-id="920d3-160">null</span></span>|  
|<span data-ttu-id="920d3-161">Serialisierung von <xref:System.DBNull.Value></span><span class="sxs-lookup"><span data-stu-id="920d3-161">Serialization of <xref:System.DBNull.Value></span></span>|<span data-ttu-id="920d3-162">{} (oder {"__type": "#System"})</span><span class="sxs-lookup"><span data-stu-id="920d3-162">{} (or {"__type":"#System"})</span></span>|<span data-ttu-id="920d3-163">Null</span><span class="sxs-lookup"><span data-stu-id="920d3-163">Null</span></span>|  
|<span data-ttu-id="920d3-164">Serialisierung der privaten Member von [Serializable]-Typen.</span><span class="sxs-lookup"><span data-stu-id="920d3-164">Serialization of the private members of [Serializable] types.</span></span>|<span data-ttu-id="920d3-165">serialisiert</span><span class="sxs-lookup"><span data-stu-id="920d3-165">serialized</span></span>|<span data-ttu-id="920d3-166">nicht serialisiert</span><span class="sxs-lookup"><span data-stu-id="920d3-166">not serialized</span></span>|  
|<span data-ttu-id="920d3-167">Serialisierung der öffentlichen Eigenschaften von <xref:System.Runtime.Serialization.ISerializable>-Typen</span><span class="sxs-lookup"><span data-stu-id="920d3-167">Serialization of the public properties of <xref:System.Runtime.Serialization.ISerializable> types.</span></span>|<span data-ttu-id="920d3-168">nicht serialisiert</span><span class="sxs-lookup"><span data-stu-id="920d3-168">not serialized</span></span>|<span data-ttu-id="920d3-169">serialisiert</span><span class="sxs-lookup"><span data-stu-id="920d3-169">serialized</span></span>|  
|<span data-ttu-id="920d3-170">"Erweiterungen" von JSON</span><span class="sxs-lookup"><span data-stu-id="920d3-170">"Extensions" of JSON</span></span>|<span data-ttu-id="920d3-171">Entspricht der JSON-Spezifikation, die erfordert, dass Objektmembernamen in Anführungszeichen gesetzt werden müssen ({"a":"hello"}).</span><span class="sxs-lookup"><span data-stu-id="920d3-171">Adheres to the JSON specification, which requires quotes on object member names ({"a":"hello"}).</span></span>|<span data-ttu-id="920d3-172">Lässt Namen von Objektmembern ohne Anführungszeichen zu ({a:"hello"}).</span><span class="sxs-lookup"><span data-stu-id="920d3-172">Supports the names of object members without quotes ({a:"hello"}).</span></span>|  
|<span data-ttu-id="920d3-173"><xref:System.DateTime> UTC (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="920d3-173"><xref:System.DateTime> Coordinated Universal Time (UTC)</span></span>|<span data-ttu-id="920d3-174">Unterstützt keine Format "\\/Date(123456789U)\\/" oder "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".</span><span class="sxs-lookup"><span data-stu-id="920d3-174">Does not support format "\\/Date(123456789U)\\/" or "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)".</span></span>|<span data-ttu-id="920d3-175">Unterstützt das Format "\\/Date(123456789U)\\/" und "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "als DateTime-Werte.</span><span class="sxs-lookup"><span data-stu-id="920d3-175">Supports format "\\/Date(123456789U)\\/" and "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)" as DateTime values.</span></span>|  
|<span data-ttu-id="920d3-176">Darstellung von Wörterbüchern</span><span class="sxs-lookup"><span data-stu-id="920d3-176">Representation of dictionaries</span></span>|<span data-ttu-id="920d3-177">Ein Array von KeyValuePair\<K, V >, behandelt Schlüsseltypen, die keine Zeichenfolgen sind.</span><span class="sxs-lookup"><span data-stu-id="920d3-177">An array of KeyValuePair\<K,V>, handles key types that are not strings.</span></span>|<span data-ttu-id="920d3-178">Als tatsächliche JSON-Objekte, behandelt aber nur Schlüsseltypen, die Zeichenfolgen sind.</span><span class="sxs-lookup"><span data-stu-id="920d3-178">As actual JSON objects - but only handles key types that are strings.</span></span>|  
|<span data-ttu-id="920d3-179">Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="920d3-179">Escaped characters</span></span>|<span data-ttu-id="920d3-180">Immer mit einem Schrägstrich (/) als Escapezeichen; lässt nie ungültige JSON-Zeichen ohne Escapezeichen wie "\n" zu.</span><span class="sxs-lookup"><span data-stu-id="920d3-180">Always with an escape forward slash (/); never allows un-escaped invalid JSON characters, such as "\n".</span></span>|<span data-ttu-id="920d3-181">Mit einem Schrägstrich (/) als Escapezeichen für DateTime-Werte.</span><span class="sxs-lookup"><span data-stu-id="920d3-181">With an escape forward slash (/) for DateTime values.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="920d3-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="920d3-182">See Also</span></span>  
 [<span data-ttu-id="920d3-183">Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="920d3-183">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
