---
title: 'Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: dfbb32a751623fb1e3753cfd8bbbaf5910d571b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142999"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF
Dieses Thema beschreibt Verfahren zum Migrieren von eines einfachen ASP.NET AJAX-Diensts mit einem entsprechenden AJAX-fähigen Windows Communication Foundation (WCF)-Dienst. Es zeigt, wie eine funktional der WCF-Version von ASP.NET AJAX-Dienst zu erstellen. Die beiden Dienste können dann parallel verwendet werden, oder der WCF-Dienst kann verwendet werden, um die ASP.NET AJAX-Dienst zu ersetzen.

 Migrieren einer vorhandenen ASP.NET AJAX bietet Service an einen WCF AJAX-Dienst die folgenden Vorteile:

-   Sie können den AJAX-Dienst mit nur minimaler zusätzlicher Konfiguration als SOAP-Dienst verfügbar machen.

-   Sie können profitieren Sie von WCF-Features wie z. B. Ablaufverfolgung und so weiter.

 Die folgenden Verfahren wird davon ausgegangen, dass Sie Visual Studio 2012 verwenden.

 Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.

 Weitere Informationen zu einen WCF-Dienst über einen AJAX-aktivierten Endpunkt verfügbar zu machen, finden Sie unter den [Vorgehensweise: Verwenden Sie die Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) Thema.

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>So erstellen und testen Sie die ASP.NET-Webdienstanwendung

1.  Öffnen Sie Visual Studio 2012.

2.  Von der **Datei** , wählen Sie im Menü **neu**, klicken Sie dann **Projekt**, klicken Sie dann **Web**, und wählen Sie dann **ASP.NET Web Service-Anwendung** .

3.  Nennen Sie das Projekt `ASPHello` , und klicken Sie auf **OK**.

4.  Entfernen Sie in der Datei Service1.asmx.cs die Kommentarzeichen vor der Zeile, die `System.Web.Script.Services.ScriptService]` enthält, damit AJAX für diesen Dienst aktiviert wird.

5.  Von der **erstellen** , wählen Sie im Menü **Projektmappe**.

6.  Wählen Sie im Menü **Debuggen** die Option **Starten ohne Debuggen** aus.

7.  Wählen Sie auf der generierten Webseite den Vorgang `HelloWorld` aus.

8.  Klicken Sie auf die **Invoke** Schaltfläche der `HelloWorld` Seite "Test". Sie sollten die folgende XML-Antwort empfangen.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Diese Antwort bestätigt Ihnen, dass Sie nun über einen funktionierenden ASP.NET AJAX-Dienst verfügen und insbesondere, dass der Dienst jetzt einen Endpunkt unter Service1.asmx/HelloWorld verfügbar gemacht hat, der auf HTTP POST-Anforderungen antwortet und XML zurückgibt.

     Jetzt sind Sie bereit ist, konvertiert diesen Dienst, um einen WCF AJAX-Dienst verwenden.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>So erstellen Sie eine äquivalente WCF AJAX-Dienstanwendung

1.  Mit der rechten Maustaste die **ASPHello** Projekt, und wählen **hinzufügen**, klicken Sie dann **neues Element**, und klicken Sie dann **AJAX-aktivierter WCF-Dienst**.

2.  Nennen Sie den Dienst `WCFHello` , und klicken Sie auf **hinzufügen**.

3.  Öffnen Sie die Datei WCFHello.svc.cs.

4.  Kopieren Sie die folgende Implementierung der in der Datei Service1.asmx.cs die `HelloWorld` Vorgang.

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

6.  Geben Sie die `Namespace` Attribut für <xref:System.ServiceModel.ServiceContractAttribute> als `WCFHello`.

    ```
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7.  Hinzufügen der <xref:System.ServiceModel.Web.WebInvokeAttribute> auf die `HelloWorld` Vorgang, und legen die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> zurückzugebende Eigenschaft <xref:System.ServiceModel.Web.WebMessageFormat.Xml>. Beachten Sie, dass der Standardrückgabetyp <xref:System.ServiceModel.Web.WebMessageFormat.Json> ist, sofern nichts anderes festgelegt wird.

    ```
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8.  Von der **erstellen** , wählen Sie im Menü **Projektmappe**.

9. Öffnen Sie die Datei WCFHello.svc und von der **Debuggen** , wählen Sie im Menü **Starten ohne Debugging**.

10. Der Dienst stellt jetzt einen Endpunkt an `WCFHello.svc/HelloWorld`, die auf HTTP POST-Anforderungen reagiert. HTTP POST-Anforderungen können im Browser nicht getestet werden, aber der Endpunkt gibt die folgenden XML-Daten zurück.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. Die `WCFHello.svc/HelloWorld` und `Service1.aspx/HelloWorld` Endpunkte sind jetzt funktional äquivalent.

## <a name="example"></a>Beispiel
 Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird im folgenden Beispiel bereitgestellt.

```csharp
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

 Wenn ASMX-Webdienste aktualisiert werden und migriert Seite-an-Seite für WCF-Dienste, vermeiden Sie die Zuordnung von zwei Arten auf dem gleichen Namen auf dem Client. Denn andernfalls wird beim Serialisieren eine Ausnahme ausgelöst, wenn der gleiche Typ in einem <xref:System.Web.Services.WebMethodAttribute> und einem <xref:System.ServiceModel.ServiceContractAttribute> verwendet wird.

-   Wenn WCF-Dienst zuerst hinzugefügt wird, wird eine Aufruf der Methode ASMX-Webdienst Ausnahme im <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> da die WCF-Formatdefinition der Reihenfolge im Proxy Vorrang hat.

-   Wenn ASMX-Webdienst zuerst hinzugefügt wird, wird eine Methode für WCF-Dienst aufrufen Ausnahme in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> da die Webdienst-Formatdefinition der Reihenfolge im Proxy Vorrang hat.

 Es gibt bedeutende Unterschiede im Verhalten von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und dem ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>. Beispielsweise stellt der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ein Wörterbuch als Array von Schlüssel-Wert-Paaren dar, wohingegen der ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> ein Wörterbuch als tatsächliche JSON-Objekte darstellt. Deshalb ist das Folgende die Darstellung eines Wörterbuchs in ASP.NET AJAX.

```
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Dieses Wörterbuch wird entsprechend der folgenden Liste in JSON-Objekten dargestellt:

-   [{"Key": "one", "Value": 1}, {"Key": "two", "Value": 2}] von der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

-   {"one": 1, "two": 2} vom ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>

 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ist insofern leistungsfähiger, als dass er Wörterbücher handhaben kann, bei denen der Schlüsseltyp keine Zeichenfolge ist. Der <xref:System.Web.Script.Serialization.JavaScriptSerializer> kann dies nicht. Letzterer ist jedoch JSON-freundlicher.

 Die wichtigsten Unterschiede zwischen diesen Serialisierern werden in der folgenden Tabelle zusammengefasst.

|Unterschiedskategorie|DataContractJsonSerializer|ASP.NET AJAX JavaScriptSerializer|
|-----------------------------|--------------------------------|---------------------------------------|
|Deserialisieren des leeren Puffers (new byte[0]) in <xref:System.Object> (oder <xref:System.Uri> oder andere Klassen).|SerializationException|NULL|
|Serialisierung von <xref:System.DBNull.Value>|{} (or {"__type":"#System"})|Null|
|Serialisierung der privaten Member von [Serializable]-Typen.|serialisiert|nicht serialisiert|
|Serialisierung der öffentlichen Eigenschaften von <xref:System.Runtime.Serialization.ISerializable>-Typen|nicht serialisiert|serialisiert|
|"Erweiterungen" von JSON|Entspricht der JSON-Spezifikation, die erfordert, dass Objektmembernamen in Anführungszeichen gesetzt werden müssen ({"a":"hello"}).|Lässt Namen von Objektmembern ohne Anführungszeichen zu ({a:"hello"}).|
|<xref:System.DateTime> Koordinierte Weltzeit (UTC)|Unterstützt nicht die Formate "\\/Date(123456789U)\\/" oder "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".|Unterstützt die Formate "\\/Date(123456789U)\\/" und "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "als DateTime-Werte.|
|Darstellung von Wörterbüchern|Ein Array von KeyValuePair\<K, V >, behandelt Schlüsseltypen, die keine Zeichenfolgen sind.|Als tatsächliche JSON-Objekte, behandelt aber nur Schlüsseltypen, die Zeichenfolgen sind.|
|Escapezeichen|Immer mit einem Schrägstrich (/) als Escapezeichen; lässt nie ungültige JSON-Zeichen ohne Escapezeichen wie "\n" zu.|Mit einem Schrägstrich (/) als Escapezeichen für DateTime-Werte.|

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
