---
title: HTTP
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
ms.openlocfilehash: c8c799a50e5d63bbf411c338eb9e93f85a942bb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048010"
---
# <a name="http"></a>HTTP
.NET Framework bietet durch die Klassen <xref:System.Net.HttpWebRequest> und <xref:System.Net.HttpWebResponse> eine umfassende Unterstützung für das HTTP-Protokoll an, das den Großteil des gesamten Internetverkehrs ausmacht. Diese Klassen, die von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet wurden, werden standardmäßig zurückgegeben, wenn die statische Methode <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> eine URI findet, die mit „http“ oder „https“ beginnt. In den meisten Klassen stellen die Klassen **WebRequest** und **WebResponse** alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die HTTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen in **HttpWebRequest** oder **HttpWebResponse** umwandeln.  
  
 **HttpWebRequest** und **HttpWebResponse** kapseln eine Standard-HTTP-Anforderung für Anforderung und Antwort ein und bieten Zugriff auf allgemeine HTTP-Header. Diese Klassen unterstützen auch die meisten HTTP 1.1-Features, einschließlich der Pipeline, dem Senden und Empfangen von Nachrichten in Segmenten, der Authentifizierung, der Präauthentifizierung, der Verschlüsselung, der Proxyunterstützung, der Überprüfung von Serverzertifikaten und der Verbindungsverwaltung. Benutzerdefinierte Header und Header, die nicht von Eigenschaften bereitgestellt werden, können in der **Header**-Eigenschaft gespeichert und abgerufen werden.  
  
 **HttpWebRequest** ist die Standardklasse, die von **WebRequest** verwendet wird und muss nicht registriert werden, bevor Sie eine URI an die Methode **WebRequest.Create** übergeben können.  
  
 Ihre Anwendung kann HTTP-Umleitungen automatisch folgen, indem Sie die <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A>-Eigenschaft auf **TRUE** (Standardeinstellung) festlegen. Die Anwendung leitet dann Anforderungen um, und die <xref:System.Net.HttpWebResponse.ResponseUri%2A>-Eigenschaft von **HttpWebResponse** enthält die tatsächliche Webressource, die auf die Anforderung reagiert hat. Wenn Sie **AllowAutoRedirect** auf **FALSE** festlegen, muss Ihre Anwendung dazu in der Lage sein, Umleitungen als HTTP-Protokollfehler zu behandeln.  
  
 Anwendungen erhalten HTTP-Protokollfehler, indem Sie <xref:System.Net.WebException> abfangen, wenn <xref:System.Net.WebException.Status%2A> auf <xref:System.Net.WebExceptionStatus> festgelegt ist. Die <xref:System.Net.WebException.Response%2A>-Eigenschaft enthält **WebResponse**. Dieses wurde vom Server gesendet und gibt den tatsächlich aufgetretenen HTTP-Fehler an.  
  
## <a name="see-also"></a>Weitere Informationen

- [Accessing the Internet Through a Proxy (Zugreifen auf das Internet über einen Proxy)](accessing-the-internet-through-a-proxy.md)
- [Using Application Protocols (Verwenden von Anwendungsprotokollen)](using-application-protocols.md)
- [Vorgehensweise: Zugreifen auf HTTP-spezifische Eigenschaften](how-to-access-http-specific-properties.md)
