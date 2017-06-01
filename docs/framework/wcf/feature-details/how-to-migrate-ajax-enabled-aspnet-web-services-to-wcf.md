---
title: "Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF
In diesem Thema werden Verfahren beschrieben, um einen grundlegenden ASP.NET AJAX\-Dienst zu einem entsprechenden AJAX\-aktivierten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst zu migrieren.  Es wird veranschaulicht, wie eine funktional äquivalente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Version eines ASP.NET AJAX\-Diensts erstellt wird.  Die beiden Dienste können parallel eingesetzt werden, oder der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst wird verwendet, um den ASP.NET AJAX\-Dienst zu ersetzen.  
  
 Die Migration eines vorhandenen ASP.NET AJAX\-Diensts zu einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX\-Dienst bietet Ihnen folgende Vorteile:  
  
-   Sie können den AJAX\-Dienst mit nur minimaler zusätzlicher Konfiguration als SOAP\-Dienst verfügbar machen.  
  
-   Sie können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Funktionen, z.&\#160;B. der Ablaufverfolgung usw., profitieren.  
  
 In den folgenden Verfahren wird davon ausgegangen, dass Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] verwenden.  
  
 Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Verfügbarmachen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts über einen AJAX\-fähigen Endpunkt finden Sie im Thema [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX\-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### So erstellen und testen Sie die ASP.NET\-Webdienstanwendung  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Wählen Sie im Menü **Datei** die Option **Neu**, dann **Projekt** und anschließend **Web** aus, und wählen Sie dann **ASP.NET\-Webdienstanwendung** aus.  
  
3.  Nennen Sie das Projekt `ASPHello`, und klicken Sie auf **OK**.  
  
4.  Entfernen Sie in der Datei Service1.asmx.cs die Kommentarzeichen vor der Zeile, die `System.Web.Script.Services.ScriptService]` enthält, damit AJAX für diesen Dienst aktiviert wird.  
  
5.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
6.  Wählen Sie im Menü **Debuggen** die Option **Starten ohne Debuggen**.  
  
7.  Wählen Sie auf der generierten Webseite den Vorgang `HelloWorld` aus.  
  
8.  Klicken Sie auf der `HelloWorld`\-Testseite auf die Schaltfläche **Invoke**.  Sie sollten die folgende XML\-Antwort empfangen.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. Diese Antwort bestätigt Ihnen, dass Sie nun über einen funktionierenden ASP.NET AJAX\-Dienst verfügen und insbesondere, dass der Dienst jetzt einen Endpunkt unter Service1.asmx\/HelloWorld verfügbar gemacht hat, der auf HTTP POST\-Anforderungen antwortet und XML zurückgibt.  
  
     Sie sind jetzt bereit, diesen Dienst für die Verwendung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX\-Diensts zu konvertieren.  
  
### So erstellen Sie eine äquivalente WCF AJAX\-Dienstanwendung  
  
1.  Klicken Sie mit der rechten Maustaste auf das Projekt **ASPHello**, und wählen Sie **Hinzufügen**, dann **Neues Element** und anschließend **AJAX\-aktivierter WCF\-Dienst** aus.  
  
2.  Geben Sie für den Dienst den Namen `WCFHello` ein, und klicken Sie auf **Hinzufügen**.  
  
3.  Öffnen Sie die Datei WCFHello.svc.cs.  
  
4.  Kopieren Sie in der Datei Service1.asmx.cs die folgende Implementierung des `HelloWorld`\-Vorgangs.  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  Fügen Sie die kopierte Implementierung des `HelloWorld`\-Vorgangs in die Datei WCFHello.svc.cs anstelle des folgenden Codes ein.  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  Legen Sie das `Namespace`\-Attribut für <xref:System.ServiceModel.ServiceContractAttribute> auf `WCFHello` fest.  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  Fügen Sie das <xref:System.ServiceModel.Web.WebInvokeAttribute> dem `HelloWorld`\-Vorgang hinzu, und legen Sie die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>\-Eigenschaft auf die Rückgabe von <xref:System.ServiceModel.Web.WebMessageFormat> fest.  Beachten Sie, dass der Standardrückgabetyp <xref:System.ServiceModel.Web.WebMessageFormat> ist, sofern nichts anderes festgelegt wird.  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
9. Öffnen Sie die Datei WCFHello.svc, und wählen Sie im Menü **Debuggen** die Option **Starten ohne Debuggen** aus.  
  
10. Der Dienst macht jetzt unter `WCFHello.svc/HelloWorld`, einen Endpunkt verfügbar, der auf HTTP POST\-Anforderungen reagiert.  HTTP POST\-Anforderungen können im Browser nicht getestet werden, aber der Endpunkt gibt die folgenden XML\-Daten zurück.  
  
    ```  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. Der `WCFHello.svc/HelloWorld`\- und der `Service1.aspx/HelloWorld`\-Endpunkt sind jetzt funktional äquivalent.  
  
## Beispiel  
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
  
 Der <xref:System.Xml.XmlDocument>\-Typ wird vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> nicht unterstützt, da er vom <xref:System.Xml.Serialization.XmlSerializer> nicht serialisiert werden kann.  Sie können entweder einen <xref:System.Xml.Linq.XDocument>\-Typ verwenden oder stattdessen das <xref:System.Xml.XmlDocument.DocumentElement%2A> serialisieren.  
  
 Wenn ASMX\-Webdienste parallel zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten aktualisiert und migriert werden, sollten die Typen jeweils eindeutigen Namen auf dem Client zugeordnet werden.  Denn andernfalls wird beim Serialisieren eine Ausnahme ausgelöst, wenn der gleiche Typ in einem <xref:System.Web.Services.WebMethodAttribute> und einem <xref:System.ServiceModel.ServiceContractAttribute> verwendet wird.  
  
-   Wird der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Webdienst zuerst hinzugefügt, dann wird beim Aufruf der Methode des ASMX\-Webdiensts eine Ausnahme in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> ausgelöst, weil die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Formatdefinition der Reihenfolge im Proxy Vorrang hat.  
  
-   Wird der ASMX\-Webdienst zuerst hinzugefügt, dann wird beim Aufruf der Methode des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts eine Ausnahme in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ausgelöst, weil die Webdienst\-Formatdefinition der Reihenfolge im Proxy Vorrang hat.  
  
 Es gibt bedeutende Unterschiede im Verhalten von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und dem ASP.NET AJAX <xref:System.Web.Script.Serialization.JavascriptSerializer>.  Beispielsweise stellt der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ein Wörterbuch als Array von Schlüssel\-Wert\-Paaren dar, wohingegen der ASP.NET AJAX <xref:System.Web.Script.Serialization.JavascriptSerializer> ein Wörterbuch als tatsächliche JSON\-Objekte darstellt.  Deshalb ist das Folgende die Darstellung eines Wörterbuchs in ASP.NET AJAX.  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add(“one”, 1);  
d.Add(“two”, 2);  
```  
  
 Dieses Wörterbuch wird entsprechend der folgenden Liste in JSON\-Objekten dargestellt:  
  
-   \[{"Key":"one","Value":1},{"Key":"two","Value":2}\] vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
  
-   {"one": 1, "two": 2} vom ASP.NET AJAX <xref:System.Web.Script.Serialization.JavascriptSerializer>  
  
 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ist insofern leistungsfähiger, als dass er Wörterbücher handhaben kann, bei denen der Schlüsseltyp keine Zeichenfolge ist. Der <xref:System.Web.Script.Serialization.JavascriptSerializer> kann dies nicht.  Letzterer ist jedoch JSON\-freundlicher.  
  
 Die wichtigsten Unterschiede zwischen diesen Serialisierern werden in der folgenden Tabelle zusammengefasst.  
  
|Unterschiedskategorie|DataContractJsonSerializer|ASP.NET AJAX JavaScriptSerializer|  
|---------------------------|--------------------------------|---------------------------------------|  
|Deserialisieren des leeren Puffers \(new byte\[0\]\) in <xref:System.Object> \(oder <xref:System.Uri> oder andere Klassen\).|SerializationException|null|  
|Serialisierung von <xref:System.DBNull.Value>|{} \(oder {"\_\_type":"\#System"}\)|Null|  
|Serialisierung der privaten Member von \[Serializable\]\-Typen.|serialisiert|nicht serialisiert|  
|Serialisierung der öffentlichen Eigenschaften von <xref:System.Runtime.Serialization.ISerializable>\-Typen|nicht serialisiert|serialisiert|  
|"Erweiterungen" von JSON|Entspricht der JSON\-Spezifikation, die erfordert, dass Objektmembernamen in Anführungszeichen gesetzt werden müssen \({"a":"hello"}\).|Lässt Namen von Objektmembern ohne Anführungszeichen zu \({a:"hello"}\).|  
|<xref:System.DateTime> UTC \(Coordinated Universal Time\)|Unterstützt nicht die Formate "\\\/Date\(123456789U\)\\\/" or "\\\/Date\\\(\\d\+\(U&#124;\(\\\+\\\-\[\\d{4}\]\)\)?  \\\)\\\\\/\)".|Unterstützt das Format "\\\/Date\(123456789U\)\\\/" and "\\\/Date\\\(\\d\+\(U&#124;\(\\\+\\\-\[\\d{4}\]\)\)?  \\\)\\\\\/\)" als DateTime\-Werte.|  
|Darstellung von Wörterbüchern|Ein Array von KeyValuePair\<K, V\>, behandelt Schlüsseltypen, die keine Zeichenfolgen sind.|Als tatsächliche JSON\-Objekte, behandelt aber nur Schlüsseltypen, die Zeichenfolgen sind.|  
|Escapezeichen|Immer mit einem Schrägstrich \(\/\) als Escapezeichen; lässt nie ungültige JSON\-Zeichen ohne Escapezeichen wie "\\n" zu.|Mit einem Schrägstrich \(\/\) als Escapezeichen für DateTime\-Werte.|  
  
## Siehe auch  
 [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX\-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)