---
title: Verwenden von JSONP
ms.date: 03/30/2017
ms.assetid: f386718c-b4ba-4931-a610-40c27a46672a
ms.openlocfilehash: 82290319b5d8b58708f0b2ebf40522ee76127b84
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594958"
---
# <a name="using-jsonp"></a>Verwenden von JSONP

JSON Padding (JSONP) ist ein Mechanismus, der in Webbrowsern die siteübergreifende Skriptunterstützung ermöglicht. Das Design von JSONP basiert darauf, dass Webbrowser Skripts von einer Website laden können, die sich von der Website unterscheidet, von der das momentan geladene Dokument abgerufen wurde. Der Mechanismus funktioniert, indem die JSON-Nutzlast als Padding den Namen einer benutzerdefinierten Rückruffunktion (callback) erhält. Dies wird im folgenden Beispiel veranschaulicht.

```javascript
callback({"a" = \\"b\\"});
```

Im obigen Beispiel wird die JSON-Nutzlast, `{"a" = \\"b\\"}`, mit einem Funktionsaufruf, `callback`, als Wrapper versehen. Die Rückruffunktion muss auf der aktuellen Webseite bereits definiert sein. Der Inhaltstyp einer JSONP-Antwort ist `application/javascript` .

JSONP ist nicht automatisch aktiviert. Legen Sie zum Aktivieren auf einem der HTTP Standardendpunkte (`javascriptCallbackEnabled` oder `true`) das <xref:System.ServiceModel.Description.WebHttpEndpoint>-Attribut auf <xref:System.ServiceModel.Description.WebScriptEndpoint> fest. Dies wird im folgenden Beispiel veranschaulicht.

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint name="" javascriptCallbackEnabled="true"/>
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

Sie können den Namen der Rückruffunktion in einer Abfragevariable mit dem Namen "callback" angeben, wie in der folgenden URL gezeigt.

`http://baseaddress/Service/RestService?callback=functionName`

Nach dem Aufrufen sendet der Dienst eine Antwort wie im folgenden Beispiel.

```javascript
functionName({"root":"Something"});
```  

Sie können den Rückruffunktionsnamen auch angeben, indem Sie das <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> auf die Dienstklasse anwenden, wie im folgenden Beispiel gezeigt.

```csharp
[ServiceContract]
[JavascriptCallbackBehavior(ParameterName = "$callback")]
public class Service1
{
    [OperationContract]
    [WebGet(ResponseFormat=WebMessageFormat.Json)]
    public string GetData()
    {
    }
}
```

Für den oben gezeigten Dienst sieht eine Anforderung wie folgt aus.

`http://baseaddress/Service/RestService?$callback=anotherFunction`

Nach dem Aufrufen reagiert der Dienst wie folgt.

```javascript
anotherFunction ({"root":"Something"});
```

## <a name="http-status-codes"></a>HTTP-Statuscodes

JSONP-Antworten mit anderen HTTP-Statuscodes als 200 enthalten einen zweiten Parameter mit der numerischen Darstellung des HTTP-Statuscodes, wie im folgenden Beispiel gezeigt.

```javascript
anotherFunction ({"root":"Something"}, 201);
```

## <a name="validations"></a>Überprüfungen

Wenn JSONP aktiviert ist, werden die folgenden Validierungen ausgeführt:

- Die WCF-Infrastruktur löst eine Ausnahme aus, wenn `javascriptCallback` aktiviert, in der Anforderung der Abfragezeichenfolgenparameter "callback" vorhanden und das Antwortformat auf JSON festgelegt ist.

- Falls die Anforderung den Abfragezeichenfolgenparameter "callback" enthält, der Vorgang jedoch nicht vom Typ HTTP GET ist, wird der Parameter "callback" ignoriert.

- Falls der Rückrufname `null` lautet oder eine leere Zeichenfolge ist, wird die Antwort nicht als JSONP formatiert.

## <a name="see-also"></a>Weitere Informationen

- [Überblick über WCF-Web-HTTP-Programmiermodelle](wcf-web-http-programming-model-overview.md)
