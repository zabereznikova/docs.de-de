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
# <a name="using-jsonp"></a><span data-ttu-id="f664f-102">Verwenden von JSONP</span><span class="sxs-lookup"><span data-stu-id="f664f-102">Using JSONP</span></span>

<span data-ttu-id="f664f-103">JSON Padding (JSONP) ist ein Mechanismus, der in Webbrowsern die siteübergreifende Skriptunterstützung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f664f-103">JSON Padding (JSONP) is a mechanism that enables cross-site scripting support in Web browsers.</span></span> <span data-ttu-id="f664f-104">Das Design von JSONP basiert darauf, dass Webbrowser Skripts von einer Website laden können, die sich von der Website unterscheidet, von der das momentan geladene Dokument abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="f664f-104">JSONP is designed around the ability of Web browsers to load scripts from a site different from the one the current loaded document was retrieved from.</span></span> <span data-ttu-id="f664f-105">Der Mechanismus funktioniert, indem die JSON-Nutzlast als Padding den Namen einer benutzerdefinierten Rückruffunktion (callback) erhält. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f664f-105">The mechanism works by padding the JSON payload with a user-defined callback function name, as shown in the following example.</span></span>

```javascript
callback({"a" = \\"b\\"});
```

<span data-ttu-id="f664f-106">Im obigen Beispiel wird die JSON-Nutzlast, `{"a" = \\"b\\"}`, mit einem Funktionsaufruf, `callback`, als Wrapper versehen.</span><span class="sxs-lookup"><span data-stu-id="f664f-106">In the preceding example the JSON payload, `{"a" = \\"b\\"}`, is wrapped in a function call, `callback`.</span></span> <span data-ttu-id="f664f-107">Die Rückruffunktion muss auf der aktuellen Webseite bereits definiert sein.</span><span class="sxs-lookup"><span data-stu-id="f664f-107">The callback function must already be defined in the current Web page.</span></span> <span data-ttu-id="f664f-108">Der Inhaltstyp einer JSONP-Antwort ist `application/javascript` .</span><span class="sxs-lookup"><span data-stu-id="f664f-108">The content type of a JSONP response is `application/javascript`.</span></span>

<span data-ttu-id="f664f-109">JSONP ist nicht automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f664f-109">JSONP is not automatically enabled.</span></span> <span data-ttu-id="f664f-110">Legen Sie zum Aktivieren auf einem der HTTP Standardendpunkte (`javascriptCallbackEnabled` oder `true`) das <xref:System.ServiceModel.Description.WebHttpEndpoint>-Attribut auf <xref:System.ServiceModel.Description.WebScriptEndpoint> fest. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f664f-110">To enable it, set the `javascriptCallbackEnabled` attribute to `true` on one of the HTTP standard endpoints (<xref:System.ServiceModel.Description.WebHttpEndpoint> or <xref:System.ServiceModel.Description.WebScriptEndpoint>), as shown in the following example.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint name="" javascriptCallbackEnabled="true"/>
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="f664f-111">Sie können den Namen der Rückruffunktion in einer Abfragevariable mit dem Namen "callback" angeben, wie in der folgenden URL gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f664f-111">The name of the callback function can be specified in a query variable called callback as shown in the following URL.</span></span>

`http://baseaddress/Service/RestService?callback=functionName`

<span data-ttu-id="f664f-112">Nach dem Aufrufen sendet der Dienst eine Antwort wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f664f-112">When invoked, the service sends a response like the following.</span></span>

```javascript
functionName({"root":"Something"});
```  

<span data-ttu-id="f664f-113">Sie können den Rückruffunktionsnamen auch angeben, indem Sie das <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> auf die Dienstklasse anwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f664f-113">You can also specify the callback function name by applying the <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> to the service class, as shown in the following example.</span></span>

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

<span data-ttu-id="f664f-114">Für den oben gezeigten Dienst sieht eine Anforderung wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="f664f-114">For the service shown previously, a request looks like the following.</span></span>

`http://baseaddress/Service/RestService?$callback=anotherFunction`

<span data-ttu-id="f664f-115">Nach dem Aufrufen reagiert der Dienst wie folgt.</span><span class="sxs-lookup"><span data-stu-id="f664f-115">When invoked, the service responds with the following.</span></span>

```javascript
anotherFunction ({"root":"Something"});
```

## <a name="http-status-codes"></a><span data-ttu-id="f664f-116">HTTP-Statuscodes</span><span class="sxs-lookup"><span data-stu-id="f664f-116">HTTP Status Codes</span></span>

<span data-ttu-id="f664f-117">JSONP-Antworten mit anderen HTTP-Statuscodes als 200 enthalten einen zweiten Parameter mit der numerischen Darstellung des HTTP-Statuscodes, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f664f-117">JSONP responses with HTTP status codes other than 200 include a second parameter with the numeric representation of the HTTP status code, as shown in the following example.</span></span>

```javascript
anotherFunction ({"root":"Something"}, 201);
```

## <a name="validations"></a><span data-ttu-id="f664f-118">Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="f664f-118">Validations</span></span>

<span data-ttu-id="f664f-119">Wenn JSONP aktiviert ist, werden die folgenden Validierungen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="f664f-119">The following validations are performed when JSONP is enabled:</span></span>

- <span data-ttu-id="f664f-120">Die WCF-Infrastruktur löst eine Ausnahme aus, wenn `javascriptCallback` aktiviert, in der Anforderung der Abfragezeichenfolgenparameter "callback" vorhanden und das Antwortformat auf JSON festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f664f-120">The WCF infrastructure throws an exception if `javascriptCallback` is enabled, a callback query-string parameter is present in the request and the response format is set to JSON.</span></span>

- <span data-ttu-id="f664f-121">Falls die Anforderung den Abfragezeichenfolgenparameter "callback" enthält, der Vorgang jedoch nicht vom Typ HTTP GET ist, wird der Parameter "callback" ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f664f-121">If the request contains the callback query string parameter but the operation is not an HTTP GET, the callback parameter is ignored.</span></span>

- <span data-ttu-id="f664f-122">Falls der Rückrufname `null` lautet oder eine leere Zeichenfolge ist, wird die Antwort nicht als JSONP formatiert.</span><span class="sxs-lookup"><span data-stu-id="f664f-122">If the callback name is `null` or empty string the response is not formatted as JSONP.</span></span>

## <a name="see-also"></a><span data-ttu-id="f664f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f664f-123">See also</span></span>

- [<span data-ttu-id="f664f-124">Überblick über WCF-Web-HTTP-Programmiermodelle</span><span class="sxs-lookup"><span data-stu-id="f664f-124">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
