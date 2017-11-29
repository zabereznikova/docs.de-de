---
title: 'Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 91b611af6c8de5c2bc0119838eb12950d3207177
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF
In diesem Thema werden Verfahren beschrieben, um einen grundlegenden ASP.NET AJAX-Dienst zu einem entsprechenden AJAX-aktivierten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst zu migrieren. Es wird veranschaulicht, wie eine funktional äquivalente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Version eines ASP.NET AJAX-Diensts erstellt wird. Die beiden Dienste können parallel eingesetzt werden, oder der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst wird verwendet, um den ASP.NET AJAX-Dienst zu ersetzen.  
  
 Die Migration eines vorhandenen ASP.NET AJAX-Diensts zu einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX-Dienst bietet Ihnen folgende Vorteile:  
  
-   Sie können den AJAX-Dienst mit nur minimaler zusätzlicher Konfiguration als SOAP-Dienst verfügbar machen.  
  
-   Sie können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Funktionen, z.&#160;B. der Ablaufverfolgung usw., profitieren.  
  
 In den folgenden Verfahren wird davon ausgegangen, dass Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] verwenden.  
  
 Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Verfügbarmachen von einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts über einen AJAX-aktivierten Endpunkt die [wie: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) Thema.  
  
### <a name="to-create-and-test-the-aspnet-web-service-application"></a>So erstellen und testen Sie die ASP.NET-Webdienstanwendung  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Aus der **Datei** klicken Sie im Menü **neu**, klicken Sie dann **Projekt**, klicken Sie dann **Web**, und wählen Sie dann **ASP.NET-Webdienstanwendung** .  
  
3.  Nennen Sie das Projekt `ASPHello` , und klicken Sie auf **OK**.  
  
4.  Entfernen Sie in der Datei Service1.asmx.cs die Kommentarzeichen vor der Zeile, die `System.Web.Script.Services.ScriptService]` enthält, damit AJAX für diesen Dienst aktiviert wird.  
  
5.  Aus der **erstellen** klicken Sie im Menü **Projektmappe**.  
  
6.  Aus der **Debuggen** klicken Sie im Menü **Starten ohne Debugging**.  
  
7.  Wählen Sie auf der generierten Webseite den Vorgang `HelloWorld` aus.  
  
8.  Klicken Sie auf die **Invoke** Schaltfläche auf der `HelloWorld` Testseite. Sie sollten die folgende XML-Antwort empfangen.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. Diese Antwort bestätigt Ihnen, dass Sie nun über einen funktionierenden ASP.NET AJAX-Dienst verfügen und insbesondere, dass der Dienst jetzt einen Endpunkt unter Service1.asmx/HelloWorld verfügbar gemacht hat, der auf HTTP POST-Anforderungen antwortet und XML zurückgibt.  
  
     Sie sind jetzt bereit, diesen Dienst für die Verwendung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX-Diensts zu konvertieren.  
  
### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>So erstellen Sie eine äquivalente WCF AJAX-Dienstanwendung  
  
1.  Mit der rechten Maustaste die **ASPHello** Projekt, und wählen Sie **hinzufügen**, klicken Sie dann **neues Element**, und klicken Sie dann **AJAX-aktivierter WCF-Dienst**.  
  
2.  Benennen Sie den Dienst `WCFHello` , und klicken Sie auf **hinzufügen**.  
  
3.  Öffnen Sie die Datei WCFHello.svc.cs.  
  
4.  Kopieren Sie die folgende Implementierung des in der Datei Service1.asmx.cs die `HelloWorld` Vorgang.  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  Fügen Sie die kopierte Implementierung des der `HelloWorld` Vorgang in die Datei WCFHello.svc.cs anstelle des folgenden Codes.  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  Geben Sie die `Namespace` -Attribut für <xref:System.ServiceModel.ServiceContractAttribute> als `WCFHello`.  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  Hinzufügen der <xref:System.ServiceModel.Web.WebInvokeAttribute> auf die `HelloWorld` Vorgang und legen die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> -Eigenschaft zum Zurückgeben von <xref:System.ServiceModel.Web.WebMessageFormat.Xml>. Beachten Sie, dass der Standardrückgabetyp <xref:System.ServiceModel.Web.WebMessageFormat.Json> ist, sofern nichts anderes festgelegt wird.  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  Aus der **erstellen** klicken Sie im Menü **Projektmappe**.  
  
9. Öffnen Sie die Datei WCFHello.svc und aus der **Debuggen** klicken Sie im Menü **Starten ohne Debugging**.  
  
10. Der Dienst macht jetzt einen Endpunkt unter `WCFHello.svc/HelloWorld`, die auf HTTP-POST-Anforderungen reagiert. HTTP POST-Anforderungen können im Browser nicht getestet werden, aber der Endpunkt gibt die folgenden XML-Daten zurück.  
  
    ```xml  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. Die `WCFHello.svc/HelloWorld` und die `Service1.aspx/HelloWorld` Endpunkte sind jetzt funktional äquivalent.  
  
## <a name="example"></a>Beispiel  
 Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird im folgenden Beispiel bereitgestellt.  
  
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
  
 Der <xref:System.Xml.XmlDocument>-Typ wird vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> nicht unterstützt, da er vom <xref:System.Xml.Serialization.XmlSerializer> nicht serialisiert werden kann. Sie können entweder einen <xref:System.Xml.Linq.XDocument>-Typ verwenden oder stattdessen das <xref:System.Xml.XmlDocument.DocumentElement%2A> serialisieren.  
  
 Wenn ASMX-Webdienste parallel zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten aktualisiert und migriert werden, sollten die Typen jeweils eindeutigen Namen auf dem Client zugeordnet werden. Denn andernfalls wird beim Serialisieren eine Ausnahme ausgelöst, wenn der gleiche Typ in einem <xref:System.Web.Services.WebMethodAttribute> und einem <xref:System.ServiceModel.ServiceContractAttribute> verwendet wird.  
  
-   Wird der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Webdienst zuerst hinzugefügt, dann wird beim Aufruf der Methode des ASMX-Webdiensts eine Ausnahme in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> ausgelöst, weil die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Formatdefinition der Reihenfolge im Proxy Vorrang hat.  
  
-   Wird der ASMX-Webdienst zuerst hinzugefügt, dann wird beim Aufruf der Methode des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts eine Ausnahme in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ausgelöst, weil die Webdienst-Formatdefinition der Reihenfolge im Proxy Vorrang hat.  
  
 Es gibt bedeutende Unterschiede im Verhalten von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und dem ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>. Beispielsweise stellt der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ein Wörterbuch als Array von Schlüssel-Wert-Paaren dar, wohingegen der ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> ein Wörterbuch als tatsächliche JSON-Objekte darstellt. Deshalb ist das Folgende die Darstellung eines Wörterbuchs in ASP.NET AJAX.  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add("one", 1);  
d.Add("two", 2);  
```  
  
 Dieses Wörterbuch wird entsprechend der folgenden Liste in JSON-Objekten dargestellt:  
  
-   [{"Key":"one","Value":1},{"Key":"two","Value":2}] vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
  
-   {"one": 1, "two": 2} vom ASP.NET AJAX<xref:System.Web.Script.Serialization.JavaScriptSerializer>  
  
 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ist insofern leistungsfähiger, als dass er Wörterbücher handhaben kann, bei denen der Schlüsseltyp keine Zeichenfolge ist. Der <xref:System.Web.Script.Serialization.JavaScriptSerializer> kann dies nicht. Letzterer ist jedoch JSON-freundlicher.  
  
 Die wichtigsten Unterschiede zwischen diesen Serialisierern werden in der folgenden Tabelle zusammengefasst.  
  
|Unterschiedskategorie|DataContractJsonSerializer|ASP.NET AJAX JavaScriptSerializer|  
|-----------------------------|--------------------------------|---------------------------------------|  
|Deserialisieren des leeren Puffers (new byte[0]) in <xref:System.Object> (oder <xref:System.Uri> oder andere Klassen).|SerializationException|null|  
|Serialisierung von <xref:System.DBNull.Value>|{} (oder {"__type":"#System"})|Null|  
|Serialisierung der privaten Member von [Serializable]-Typen.|serialisiert|nicht serialisiert|  
|Serialisierung der öffentlichen Eigenschaften von <xref:System.Runtime.Serialization.ISerializable>-Typen|nicht serialisiert|serialisiert|  
|"Erweiterungen" von JSON|Entspricht der JSON-Spezifikation, die erfordert, dass Objektmembernamen in Anführungszeichen gesetzt werden müssen ({"a":"hello"}).|Lässt Namen von Objektmembern ohne Anführungszeichen zu ({a:"hello"}).|  
|<xref:System.DateTime> UTC (Coordinated Universal Time)|Unterstützt keine Format "\\/Date(123456789U)\\/" oder "\\/Date\\(\d+ (U &#124; (\\+\\-[\d\{4\]}))?\\) \\\\/)".|Unterstützt das Format "\\/Date(123456789U)\\/" und "\\/Date\\(\d+ (U &#124; (\\+\\-[\d\{4\]}))?\\) \\ \\/) "als DateTime-Werte.|  
|Darstellung von Wörterbüchern|Ein Array von KeyValuePair\<K, V >, behandelt Schlüsseltypen, die keine Zeichenfolgen sind.|Als tatsächliche JSON-Objekte, behandelt aber nur Schlüsseltypen, die Zeichenfolgen sind.|  
|Escapezeichen|Immer mit einem Schrägstrich (/) als Escapezeichen; lässt nie ungültige JSON-Zeichen ohne Escapezeichen wie "\n" zu.|Mit einem Schrägstrich (/) als Escapezeichen für DateTime-Werte.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
