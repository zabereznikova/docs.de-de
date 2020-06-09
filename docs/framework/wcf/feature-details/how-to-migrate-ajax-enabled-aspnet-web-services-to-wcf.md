---
title: 'Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 6f356f47922945218e02271371d9ddea36ecc5a2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597006"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF
In diesem Thema werden die Verfahren zum Migrieren eines einfachen ASP.NET-AJAX-Dienstanbieter zu einem entsprechenden AJAX-fähigen Windows Communication Foundation (WCF)-Dienst beschrieben. Es wird gezeigt, wie eine funktionell äquivalente WCF-Version eines ASP.NET AJAX-Dienstanbieter erstellt wird. Die beiden Dienste können dann nebeneinander verwendet werden, oder der WCF-Dienst kann verwendet werden, um den ASP.NET AJAX-Dienst zu ersetzen.

 Das Migrieren eines vorhandenen ASP.NET AJAX-Dienstanbieter zu einem WCF AJAX-Dienst bietet die folgenden Vorteile:

- Sie können den AJAX-Dienst mit nur minimaler zusätzlicher Konfiguration als SOAP-Dienst verfügbar machen.

- Sie können von WCF-Features profitieren, wie z. b. Ablauf Verfolgung, usw.

 Bei den folgenden Prozeduren wird davon ausgegangen, dass Sie Visual Studio 2012 verwenden.

 Der Code, der sich aus den hier besprochenen Verfahren ergibt, wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.

 Weitere Informationen zum verfügbar machen eines WCF-Dienstanbieter über einen AJAX-fähigen Endpunkt finden Sie im Thema Gewusst [wie: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) .

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>So erstellen und testen Sie die ASP.NET-Webdienstanwendung

1. Öffnen Sie Visual Studio 2012.

2. Wählen Sie im Menü **Datei** die Option **neu**, dann **Projekt**und dann **Web**aus, und wählen Sie dann **ASP.NET-Webdienst Anwendung**aus.

3. Benennen Sie das Projekt, `ASPHello` und klicken Sie auf **OK**.

4. Entfernen Sie in der Datei Service1.asmx.cs die Kommentarzeichen vor der Zeile, die `System.Web.Script.Services.ScriptService]` enthält, damit AJAX für diesen Dienst aktiviert wird.

5. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen**aus.

6. Wählen Sie im Menü **Debuggen** die Option **Starten ohne Debuggen** aus.

7. Wählen Sie auf der generierten Webseite den Vorgang `HelloWorld` aus.

8. Klicken Sie auf der Testseite auf die Schaltfläche **aufrufen** `HelloWorld` . Sie sollten die folgende XML-Antwort empfangen.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Diese Antwort bestätigt Ihnen, dass Sie nun über einen funktionierenden ASP.NET AJAX-Dienst verfügen und insbesondere, dass der Dienst jetzt einen Endpunkt unter Service1.asmx/HelloWorld verfügbar gemacht hat, der auf HTTP POST-Anforderungen antwortet und XML zurückgibt.

     Nun können Sie diesen Dienst für die Verwendung eines WCF AJAX-Dienstanbieter konvertieren.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>So erstellen Sie eine äquivalente WCF AJAX-Dienstanwendung

1. Klicken Sie mit der rechten Maustaste auf das Projekt **ASPHello** , und wählen Sie **Hinzufügen**, **Neues Element**und anschließend **AJAX-aktivierter WCF-Dienst**aus.

2. Benennen Sie den Dienst, `WCFHello` und klicken Sie auf **Hinzufügen**.

3. Öffnen Sie die Datei WCFHello.svc.cs.

4. Kopieren Sie in Service1.asmx.cs die folgende Implementierung des `HelloWorld` Vorgangs.

    ```csharp
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

5. Fügen Sie `HelloWorld` in die Datei "WCFHello.svc.cs" anstelle des folgenden Codes in die kopierte Implementierung des Vorgangs ein.

    ```csharp
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. Legen Sie das- `Namespace` Attribut für <xref:System.ServiceModel.ServiceContractAttribute> als fest `WCFHello` .

    ```csharp
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. Fügen Sie dem Vorgang das hinzu <xref:System.ServiceModel.Web.WebInvokeAttribute> , `HelloWorld` und legen Sie die- <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> Eigenschaft auf Return fest <xref:System.ServiceModel.Web.WebMessageFormat.Xml> . Beachten Sie, dass der Standardrückgabetyp <xref:System.ServiceModel.Web.WebMessageFormat.Json> ist, sofern nichts anderes festgelegt wird.

    ```csharp
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen**aus.

9. Öffnen Sie die Datei WCFHello. svc, und wählen Sie im Menü **Debuggen** die Option **Starten ohne Debugging**aus.

10. Der Dienst macht jetzt einen Endpunkt bei verfügbar `WCFHello.svc/HelloWorld` , der auf HTTP POST-Anforderungen antwortet. HTTP POST-Anforderungen können im Browser nicht getestet werden, aber der Endpunkt gibt die folgenden XML-Daten zurück.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. Die `WCFHello.svc/HelloWorld` -und- `Service1.aspx/HelloWorld` Endpunkte sind nun funktional äquivalent.

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

 Wenn ASMX-Webdienste aktualisiert und parallel zu WCF-Diensten migriert werden, sollten Sie die Zuordnung von zwei Typen zum gleichen Namen auf dem Client vermeiden. Denn andernfalls wird beim Serialisieren eine Ausnahme ausgelöst, wenn der gleiche Typ in einem <xref:System.Web.Services.WebMethodAttribute> und einem <xref:System.ServiceModel.ServiceContractAttribute> verwendet wird.

- Wenn zuerst der WCF-Dienst hinzugefügt wird, wird beim Aufrufen der-Methode für den ASMX-Webdienst eine Ausnahme in ausgelöst, <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> da die WCF-Format Definition der Reihenfolge im Proxy Vorrang hat.

- Wenn der ASMX-Webdienst zuerst hinzugefügt wird, wird beim Aufrufen der-Methode für den WCF-Dienst eine Ausnahme in ausgelöst, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> da die Webdienst-Format Definition der Reihenfolge im Proxy Vorrang hat.

 Es gibt bedeutende Unterschiede im Verhalten von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und dem ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>. Beispielsweise stellt der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ein Wörterbuch als Array von Schlüssel-Wert-Paaren dar, wohingegen der ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> ein Wörterbuch als tatsächliche JSON-Objekte darstellt. Deshalb ist das Folgende die Darstellung eines Wörterbuchs in ASP.NET AJAX.

```csharp
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Dieses Wörterbuch wird entsprechend der folgenden Liste in JSON-Objekten dargestellt:

- [{"Key":"one","Value":1},{"Key":"two","Value":2}] vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

- {"One": 1, "Two": 2} von ASP.NET AJAX<xref:System.Web.Script.Serialization.JavaScriptSerializer>

 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ist insofern leistungsfähiger, als dass er Wörterbücher handhaben kann, bei denen der Schlüsseltyp keine Zeichenfolge ist. Der <xref:System.Web.Script.Serialization.JavaScriptSerializer> kann dies nicht. Letzterer ist jedoch JSON-freundlicher.

 Die wichtigsten Unterschiede zwischen diesen Serialisierern werden in der folgenden Tabelle zusammengefasst.

|Unterschiedskategorie|DataContractJsonSerializer|ASP.NET AJAX JavaScriptSerializer|
|-----------------------------|--------------------------------|---------------------------------------|
|Deserialisieren des leeren Puffers (new byte[0]) in <xref:System.Object> (oder <xref:System.Uri> oder andere Klassen).|SerializationException|NULL|
|Serialisierung von <xref:System.DBNull.Value>|{}(oder {"__type": "#System"})|Null|
|Serialisierung der privaten Member von [Serializable]-Typen.|serialisiert|nicht serialisiert|
|Serialisierung der öffentlichen Eigenschaften von <xref:System.Runtime.Serialization.ISerializable>-Typen|nicht serialisiert|serialisiert|
|"Erweiterungen" von JSON|Entspricht der JSON-Spezifikation, die erfordert, dass Objektmembernamen in Anführungszeichen gesetzt werden müssen ({"a":"hello"}).|Lässt Namen von Objektmembern ohne Anführungszeichen zu ({a:"hello"}).|
|<xref:System.DateTime> UTC (Coordinated Universal Time)|Das Format " \\ /Date (123456789U) \\ /" oder " \\ /Date \\ (\d + (U&#124; ( \\ + \\ -[\d {4} ])) \\ \\ \\ " wird von nicht unterstützt. /)".|Unterstützt das Format " \\ /Date (123456789U) \\ /" und " \\ /Date \\ (\d + (U&#124; ( \\ + \\ -[\d {4} ]))? \\ ) \\ \\ /) "als DateTime-Werte.|
|Darstellung von Wörterbüchern|Ein Array von KeyValuePair \<K,V> behandelt Schlüsseltypen, die keine Zeichen folgen sind.|Als tatsächliche JSON-Objekte, behandelt aber nur Schlüsseltypen, die Zeichenfolgen sind.|
|Escapezeichen|Immer mit einem Schrägstrich (/) als Escapezeichen; lässt nie ungültige JSON-Zeichen ohne Escapezeichen wie "\n" zu.|Mit einem Schrägstrich (/) als Escapezeichen für DateTime-Werte.|

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
