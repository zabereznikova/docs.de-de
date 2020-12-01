---
title: Ableiten von WebResponse
ms.date: 03/30/2017
helpviewer_keywords:
- Deriving from WebResponse
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
ms.openlocfilehash: 793533b632952df3f0866bb6377efd0e313cd007
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287526"
---
# <a name="deriving-from-webresponse"></a>Ableiten von WebResponse

Die <xref:System.Net.WebResponse>-Klasse ist eine abstrakte Basisklasse, die die grundlegenden Methoden und Eigenschaften bereitstellt, mit denen eine protokollspezifische Antwort erstellt wird, die in das austauschbare Protokollmodell von .NET Framework passt. Anwendungen, die die <xref:System.Net.WebRequest>-Klasse zur Datenanforderung von Ressourcen verwenden, erhalten die Antworten in Form einer **WebResponse**. Protokollspezifische **WebResponse**-Nachfolger müssen die abstrakten Member der **WebResponse**-Klasse implementieren.  
  
 **WebResponse**-Nachfolger werden durch die zugeordnete **WebRequest**-Klasse erstellt. <xref:System.Net.HttpWebResponse>-Instanzen werden beispielsweise nur durch Aufrufen von <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> oder <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType> erstellt. Jede **WebResponse** enthält das Ergebnis einer Anforderung an eine Ressource und sollte nicht wiederverwendet werden.  
  
## <a name="contentlength-property"></a>ContentLength-Eigenschaft  

 Die <xref:System.Net.WebResponse.ContentLength%2A>-Eigenschaft gibt die Anzahl der Datenbytes an, die auf dem Datenstrom verfügbar sind, der von der <xref:System.Net.WebResponse.GetResponseStream%2A>-Methode zurückgegeben wird. Die **ContentLength**-Eigenschaft gibt weder die Anzahl der Bytes der vom Server zurückgegebenen Headerinformationen noch die der Metadateninformationen an. Sie gibt nur die Anzahl der Datenbytes der angeforderten Ressource selbst an.  
  
## <a name="contenttype-property"></a>ContentType-Eigenschaft  

 Die <xref:System.Net.WebResponse.ContentType%2A>-Eigenschaft stellt spezielle Informationen zur Verfügung, die Sie für Ihr Protokoll an den Client senden müssen, um den Typ des vom Server gesendeten Inhalts zu identifizieren. In der Regel ist dies der MIME-Inhaltstyp aller zurückgegebenen Daten.  
  
## <a name="headers-property"></a>Header-Eigenschaft  

 Die <xref:System.Net.WebResponse.Headers%2A>-Eigenschaft enthält eine beliebige Auflistung von Name-Wert-Paaren der Metadaten, die der Antwort zugeordnet sind. Alle für das Protokoll erforderlichen Metadaten, die als Name-Wert-Paar ausgedrückt werden, können in die **Header**-Eigenschaft aufgenommen werden.  
  
 Sie müssen die **Header**-Eigenschaft nicht verwenden, um die Header-Metadaten zu nutzen. Protokollspezifische Metadaten können als Eigenschaften verfügbar gemacht werden. So macht die <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType>-Eigenschaft z.B. den **Last-Modified**-HTTP-Header verfügbar. Wenn Sie die Header-Metadaten als Eigenschaft verfügbar machen, sollten Sie nicht zulassen, dass die gleiche Eigenschaft die **Header**-Eigenschaft verwendet.  
  
## <a name="responseuri-property"></a>ResponseUri-Eigenschaft  

 Die <xref:System.Net.WebResponse.ResponseUri%2A>-Eigenschaft enthält den URI der Ressource, die die Antwort eigentlich bereitgestellt hat. Für Protokolle, die keine Umleitung unterstützen, ist **ResponseUri** identisch mit der <xref:System.Net.WebRequest.RequestUri%2A>-Eigenschaft der **WebRequest**, von der die Antwort erstellt wurde. Unterstützt das Protokoll das Umleiten der Anforderung, enthält **ResponseUri** den URI der Antwort.  
  
## <a name="close-method"></a>Close-Methode  

 Die <xref:System.Net.WebResponse.Close%2A>-Methode schließt alle von der Anforderung und der Antwort erstellten Verbindungen und bereinigt die Ressourcen, die von der Antwort verwendet wurden. Die **Close**-Methode schließt alle von der Antwort verwendeten Streaminstanzen. Sie löst jedoch keine Ausnahme aus, wenn der Antwortstream zuvor durch einen Aufruf der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode geschlossen wurde.  
  
## <a name="getresponsestream-method"></a>GetResponseStream-Methode  

 Die <xref:System.Net.WebResponse.GetResponseStream%2A>-Methode gibt einen Datenstrom zurück, der die Antwort der angeforderten Ressource enthält. Der Antwortstream enthält nur die von der Ressource zurückgegebenen Daten. In der Antwort enthaltene Header oder Metadaten sollten aus der Antwort entfernt und der Anwendung über protokollspezifische Eigenschaften oder über die **Header**-Eigenschaft verfügbar gemacht werden.  
  
 Die von der **GetResponseStream**-Methode zurückgegebene Streaminstanz ist im Besitz der Anwendung und kann geschlossen werden, ohne **WebResponse** zu schließen. Konventionsgemäß wird durch Aufrufen der **WebResponse.Close**-Methode auch der von **GetResponse** zurückgegebene Datenstrom geschlossen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebResponse>
- <xref:System.Net.HttpWebResponse>
- <xref:System.Net.FileWebResponse>
- [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md)
- [Deriving from WebRequest (Ableiten von WebRequest)](deriving-from-webrequest.md)
