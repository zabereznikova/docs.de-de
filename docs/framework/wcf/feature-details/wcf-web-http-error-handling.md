---
title: WCF-Web-HTTP-Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 834c642e36e1551081dbe1f14529ed7596df1360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152697"
---
# <a name="wcf-web-http-error-handling"></a>WCF-Web-HTTP-Fehlerbehandlung
Windows Communication Foundation (WCF)-Web-HTTP-Fehlerbehandlung ermöglicht es Ihnen, Fehler von WCF-Web-HTTP-Diensten zurückzugeben, die HTTP-Statuscode angeben und die Fehlerdetails, die mit dem gleichen Format wie des Vorgangs (z. B. XML oder JSON) zurückzugeben.  
  
## <a name="wcf-web-http-error-handling"></a>WCF-Web-HTTP-Fehlerbehandlung  
 Die <xref:System.ServiceModel.Web.WebFaultException>-Klasse definiert einen Konstruktor, der Ihnen das Angeben eines HTTP-Statuscodes ermöglicht. Dieser Statuscode wird dann an den Client zurückgegeben. Dies ist eine generische Version der <xref:System.ServiceModel.Web.WebFaultException>-Klasse. Mit <xref:System.ServiceModel.Web.WebFaultException%601> können Sie einen benutzerdefinierten Typ zurückgeben, der Informationen zum aufgetretenen Fehler enthält. Dieses benutzerdefinierte Objekt wird in dem Format serialisiert, das vom Vorgang angegeben und an den Client zurückgegeben wird. Im folgenden Beispiel wird gezeigt, wie Sie einen HTTP-Statuscode zurückgeben.  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 Im folgenden Beispiel wird gezeigt, wie Sie einen HTTP-Statuscode und zusätzliche Informationen in einem benutzerdefinierten Typ zurückgeben. `MyErrorDetail` ist ein benutzerdefinierter Typ, der zusätzliche Informationen zum aufgetretenen Fehler enthält.  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 Der oben angegebene Code gibt eine HTTP-Antwort mit dem unzulässigen Statuscode und einem Text zurück, in der eine Instanz des `MyErrorDetails`-Objekts enthalten ist. Zum Bestimmen des Formats des `MyErrorDetails`-Objekts werden folgende Komponenten herangezogen:  
  
-   Der Wert des `ResponseFormat`-Parameters des <xref:System.ServiceModel.Web.WebGetAttribute>- oder <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attributs, das für den Dienstvorgang angegeben wurde.  
  
-   Der Wert von <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.  
  
-   Der Wert der <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>-Eigenschaft, indem auf <xref:System.ServiceModel.Web.OutgoingWebResponseContext> zugegriffen wird.  
  
 Weitere Informationen dazu, wie diese Werte auf die Formatierung des Vorgangs auswirken, finden Sie unter [WCF Web-HTTP-Formatierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).  
  
 <xref:System.ServiceModel.Web.WebFaultException> ist ein <xref:System.ServiceModel.FaultException>-Objekt und kann daher als Fehlerausnahme-Programmiermodell für Dienste verwendet werden, die SOAP-Endpunkte sowie Web-HTTP-Endpunkte verfügbar machen.  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [WCF-Web-HTTP-Formatierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [Definieren und Angeben von Fehlern](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [Behandeln von Ausnahmen und Fehlern](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [Senden und Empfangen von Fehlern](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
