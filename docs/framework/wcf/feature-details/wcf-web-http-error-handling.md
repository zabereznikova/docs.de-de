---
title: WCF-Web-HTTP-Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: b1d41bebafa2795d390b120ad84475417389479b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598644"
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="34a0c-102">WCF-Web-HTTP-Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="34a0c-102">WCF Web HTTP Error Handling</span></span>
<span data-ttu-id="34a0c-103">Windows Communication Foundation (WCF)-Web-http-Fehlerbehandlung ermöglicht es Ihnen, Fehler von WCF-Web-http-Diensten zurückzugeben, die einen HTTP-Statuscode angeben und Fehlerdetails im gleichen Format wie der Vorgang (z. b. XML oder JSON) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="34a0c-103">Windows Communication Foundation (WCF) Web HTTP error handling enables you to return errors from WCF Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="34a0c-104">WCF-Web-HTTP-Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="34a0c-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="34a0c-105">Die <xref:System.ServiceModel.Web.WebFaultException>-Klasse definiert einen Konstruktor, der Ihnen das Angeben eines HTTP-Statuscodes ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="34a0c-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="34a0c-106">Dieser Statuscode wird dann an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="34a0c-106">This status code is then returned to the client.</span></span> <span data-ttu-id="34a0c-107">Dies ist eine generische Version der <xref:System.ServiceModel.Web.WebFaultException>-Klasse. Mit <xref:System.ServiceModel.Web.WebFaultException%601> können Sie einen benutzerdefinierten Typ zurückgeben, der Informationen zum aufgetretenen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="34a0c-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="34a0c-108">Dieses benutzerdefinierte Objekt wird in dem Format serialisiert, das vom Vorgang angegeben und an den Client zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="34a0c-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="34a0c-109">Im folgenden Beispiel wird gezeigt, wie Sie einen HTTP-Statuscode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="34a0c-109">The following example shows how to return an HTTP status code.</span></span>  
  
```csharp
public string Operation1()
{
    // Operation logic  
   // ...
   throw new WebFaultException(HttpStatusCode.Forbidden);
}  
```  
  
 <span data-ttu-id="34a0c-110">Im folgenden Beispiel wird gezeigt, wie Sie einen HTTP-Statuscode und zusätzliche Informationen in einem benutzerdefinierten Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="34a0c-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="34a0c-111">`MyErrorDetail` ist ein benutzerdefinierter Typ, der zusätzliche Informationen zum aufgetretenen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="34a0c-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
```csharp
public string Operation2()
{
   // Operation logic  
   // ...
   MyErrorDetail detail = new MyErrorDetail()
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="34a0c-112">Der oben angegebene Code gibt eine HTTP-Antwort mit dem unzulässigen Statuscode und einem Text zurück, in der eine Instanz des `MyErrorDetails`-Objekts enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="34a0c-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="34a0c-113">Zum Bestimmen des Formats des `MyErrorDetails`-Objekts werden folgende Komponenten herangezogen:</span><span class="sxs-lookup"><span data-stu-id="34a0c-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
- <span data-ttu-id="34a0c-114">Der Wert des `ResponseFormat`-Parameters des <xref:System.ServiceModel.Web.WebGetAttribute>- oder <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attributs, das für den Dienstvorgang angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="34a0c-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
- <span data-ttu-id="34a0c-115">Der Wert von <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="34a0c-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
- <span data-ttu-id="34a0c-116">Der Wert der <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>-Eigenschaft, indem auf <xref:System.ServiceModel.Web.OutgoingWebResponseContext> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="34a0c-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 <span data-ttu-id="34a0c-117">Weitere Informationen dazu, wie sich diese Werte auf die Formatierung des Vorgangs auswirken, finden Sie unter [WCF-Web-http-Formatierung](wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="34a0c-117">For more information about how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="34a0c-118"><xref:System.ServiceModel.Web.WebFaultException> ist ein <xref:System.ServiceModel.FaultException>-Objekt und kann daher als Fehlerausnahme-Programmiermodell für Dienste verwendet werden, die SOAP-Endpunkte sowie Web-HTTP-Endpunkte verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="34a0c-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a0c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34a0c-119">See also</span></span>

- [<span data-ttu-id="34a0c-120">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="34a0c-120">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="34a0c-121">WCF-Web-HTTP-Formatierung</span><span class="sxs-lookup"><span data-stu-id="34a0c-121">WCF Web HTTP Formatting</span></span>](wcf-web-http-formatting.md)
- [<span data-ttu-id="34a0c-122">Definieren und Angeben von Fehlern</span><span class="sxs-lookup"><span data-stu-id="34a0c-122">Defining and Specifying Faults</span></span>](../defining-and-specifying-faults.md)
- [<span data-ttu-id="34a0c-123">Behandeln von Ausnahmen und Fehlern</span><span class="sxs-lookup"><span data-stu-id="34a0c-123">Handling Exceptions and Faults</span></span>](../extending/handling-exceptions-and-faults.md)
- [<span data-ttu-id="34a0c-124">Senden und Empfangen von Fehlern</span><span class="sxs-lookup"><span data-stu-id="34a0c-124">Sending and Receiving Faults</span></span>](../sending-and-receiving-faults.md)
