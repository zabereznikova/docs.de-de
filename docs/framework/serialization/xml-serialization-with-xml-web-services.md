---
title: "XML-Serialisierung mit XML-Webdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "ASMX-Dateien"
  - "ASMX-Dateien"
  - "Attribute [.NET Framework], XML-Serialisierung"
  - "Codierte XML-Serialisierung"
  - "Literale XML-Serialisierung"
  - "Serialisierung, Attribute"
  - "Serialisierung, SOAP"
  - "SOAP, XML-Serialisierung"
  - "XML-Serialisierung, Attribute"
  - "XML-Serialisierung, XML-Webdienste"
  - "XML-Webdienste, XML-Serialisierung"
ms.assetid: a416192f-8102-458e-bc0a-0b8f3f784da9
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# XML-Serialisierung mit XML-Webdiensten
Bei der XML\-Serialisierung handelt es sich um den durch die [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)\-Klasse ausgeführten Transportmechanismus, der die Grundlage für die Architektur der XML\-Webdienste ist.Zum Steuern des mit einem XML\-Webdienst generierten XML\-Streams können Sie sowohl die unter [Attribute zur Steuerung der XML\-Serialisierung](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md) als auch die unter [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md) aufgelisteten Attribute auf die Klassen, Rückgabewerte, Parameter und Felder einer Datei anwenden, die zum Erstellen eines XML\-Webdiensts \(ASMX\) verwendet wurden.Weitere Informationen zum Erstellen eines XML\-Webdiensts finden Sie unter [Building XML Web Services Using ASP.NET](http://msdn.microsoft.com/de-de/01dfc27c-c68e-4910-a0aa-5e4c2a766b0c).  
  
## Literalformat und codiertes Format  
 Der mit einem XML\-Webdienst generierte XML\-Stream kann entweder im Literalformat oder codiert, wie unter [Customizing SOAP Messages](http://msdn.microsoft.com/de-de/1d777288-c0d9-4e6a-b638-f010da031952) beschrieben, formatiert werden.Daher wird die XML\-Serialisierung durch zwei Gruppen von Attributen gesteuert.Die unter [Attribute zur Steuerung der XML\-Serialisierung](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md) aufgelisteten Attribute sind für die Steuerung von XML im Literalformat vorgesehen.Durch die unter [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md) aufgeführten Attribute wird das codierte Format gesteuert.Durch die gezielte Anwendung dieser Attribute können Sie eine Anwendung so anpassen, dass sie eines dieser Formate oder beide Formate zurückgibt.Zudem können diese Attribute gegebenenfalls auch auf Rückgabewerte und Parameter angewendet werden.  
  
### Beispiel für die Verwendung beider Formate  
 Bei der Erstellung eines XML\-Webdienstes können Sie beide Sätze von Attributen auf die Methoden anwenden.Im folgenden Codebeispiel enthält die Klasse `MyService` die beiden XML\-Webdienstmethoden `MyLiteralMethod` und `MyEncodedMethod`.Beide Methoden führen dieselbe Funktion aus: Zurückgeben einer Instanz der `Order`\-Klasse.In der `Order` \-Klasse werden sowohl das [XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic)\-Attribut als auch das [SoapTypeAttribute](frlrfSystemXmlSerializationSoapTypeAttributeClassTopic)\-Attribut auf das `OrderID`\-Feld angewendet. Für beide Attribute wurden hierbei verschiedene Werte für die `ElementName`\-Eigenschaft festgelegt.  
  
 Um das Beispiel auszuführen, fügen Sie den Code in eine ASMX\-Datei ein, und speichern Sie die Datei in einem virtuellen Verzeichnis, das durch Internetinformationsdienste \(Internet Information Services, IIS\) verwaltet wird.Geben Sie über einen HTML\-Browser wie Internet Explorer den Namen des Computers, des virtuellen Verzeichnisses und der Datei ein.  
  
```vb  
<%@ WebService Language="VB" Class="MyService" %>  
Imports System  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports System.Xml.Serialization  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which type  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
  
Public Class MyService  
    <WebMethod, SoapDocumentMethod> _  
    public Function MyLiteralMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
    <WebMethod, SoapRpcMethod> _  
    public Function MyEncodedMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
End Class  
  
```  
  
```csharp  
<%@ WebService Language="C#" Class="MyService" %>  
using System;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Serialization;  
public class Order{  
    // Both types of attributes can be applied. Depending on which type  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
public class MyService{  
    [WebMethod][SoapDocumentMethod]  
    public Order MyLiteralMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
    [WebMethod][SoapRpcMethod]  
    public Order MyEncodedMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
}  
```  
  
 Im folgenden Codebeispiel wird `MyLiteralMethod` aufgerufen.Der Elementname wird in "LiteralOrderID" geändert.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <MyLiteralMethodResult>  
                <LiteralOrderID>string</LiteralOrderID>  
            </MyLiteralMethodResult>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 Im folgenden Codebeispiel wird `MyEncodedMethod` aufgerufen.Der Elementname ist "EncodedOrderID".  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tns="http://tempuri.org/" xmlns:types="http://tempuri.org/encodedTypes" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body soap:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
        <tns:MyEncodedMethodResponse>  
            <MyEncodedMethodResult href="#id1" />  
        </tns:MyEncodedMethodResponse>  
        <types:Order id="id1" xsi:type="types:Order">  
            <EncodedOrderID xsi:type="xsd:string">string</EncodedOrderID>  
        </types:Order>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### Anwenden von Attributen auf Rückgabewerte  
 Sie können auch Attribute für Rückgabewerte anwenden, um Namespace, Elementnamen usw. zu steuern.Im folgenden Codebeispiel wird das `XmlElementAttribute`\-Attribut auf den Rückgabewert der `MyLiteralMethod`\-Methode angewendet.Auf diese Weise können Sie den Namespace und den Elementnamen steuern.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod() As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    return myOrder  
End Function  
  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod(){  
    Order myOrder = new Order();  
    return myOrder;  
}  
```  
  
 Wenn er aufgerufen wird, gibt der Code einen XML\-Stream zurück, der dem folgenden Beispiel ähnelt.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <BookOrder xmlns="http://www.cohowinery.com">  
                <LiteralOrderID>string</LiteralOrderID>  
            </BookOrder>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### Auf Parameter angewendete Attribute  
 Sie können Attribute auch auf Parameter anwenden, um Namespace, Elementnamen usw. anzugeben.Im folgenden Beispiel wird der `MyLiteralMethodResponse`\-Methode ein Parameter hinzugefügt und das `XmlAttributeAttribute`\-Attribut auf den Parameter angewendet.Sowohl der Elementname als auch der Namespace werden für den Parameter festgelegt.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod(<XmlElement _  
("MyOrderID", Namespace:="http://www.microsoft.com")>ID As String) As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    myOrder.OrderID = ID  
    return myOrder  
End Function  
  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod([XmlElement("MyOrderID",   
Namespace="http://www.microsoft.com")] string ID){  
    Order myOrder = new Order();  
    myOrder.OrderID = ID;  
    return myOrder;  
}   
```  
  
 Die SOAP\-Anforderung sollte etwa folgendermaßen aussehen.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethod xmlns="http://tempuri.org/">  
            <MyOrderID xmlns="http://www.microsoft.com">string</MyOrderID>  
        </MyLiteralMethod>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### Anwenden von Attributen auf Klassen  
 Um den Namespace von Elementen zu steuern, die in Beziehung zu Klassen stehen, können Sie je nach Elementtyp `XmlTypeAttribute`, `XmlRootAttribute` und `SoapTypeAttribute` anwenden.Im folgenden Codebeispiel werden alle drei Attribute auf die `Order`\-Klasse angewendet.  
  
```vb  
<XmlType("BigBookService"), _  
SoapType("SoapBookService"), _  
XmlRoot("BookOrderForm")> _  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
  
```  
  
```csharp  
[XmlType("BigBooksService", Namespace = "http://www.cpandl.com")]  
[SoapType("SoapBookService")]  
[XmlRoot("BookOrderForm")]  
public class Order{  
    // Both types of attributes can be applied. Depending on which  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
```  
  
 Die Auswirkungen der Anwendungen von `XmlTypeAttribute` und `SoapTypeAttribute` werden erkennbar, wenn Sie die Dienstbeschreibung untersuchen. Dies wird im folgenden Codebeispiel gezeigt.  
  
```  
    <s:element name="BookOrderForm" type="s0:BigBookService" />   
- <s:complexType name="BigBookService">  
- <s:sequence>  
    <s:element minOccurs="0" maxOccurs="1" name="LiteralOrderID" type="s:string" />   
    </s:sequence>  
  
- <s:schema targetNamespace="http://tempuri.org/encodedTypes">  
- <s:complexType name="SoapBookService">  
- <s:sequence>  
    <s:element minOccurs="1" maxOccurs="1" name="EncodedOrderID" type="s:string" />   
    </s:sequence>  
    </s:complexType>  
    </s:schema>  
```  
  
 Die Auswirkungen des `XmlRootAttribute`\-Attributs werden auch in den HTTP GET\- und HTTP POST\-Ergebnissen deutlich, wie nachfolgend gezeigt wird.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<BookOrderForm xmlns="http://tempuri.org/">  
    <LiteralOrderID>string</LiteralOrderID>  
</BookOrderForm>  
```  
  
## Siehe auch  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [Vorgehensweise: Serialisieren eines Objekts als SOAP\-codierter XML\-Stream](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)   
 [Vorgehensweise: Überschreiben von codierter SOAP\-XML\-Serialisierung](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)   
 [Einführung in die XML\-Serialisierung](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)