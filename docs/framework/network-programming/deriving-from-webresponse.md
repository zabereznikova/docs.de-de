---
title: "Ableiten von WebResponse | Microsoft Docs"
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
  - "Ableiten von WebResponse"
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Ableiten von WebResponse
Die <xref:System.Net.WebResponse>\-Klasse ist eine abstrakte Basisklasse, die die grundlegenden Methoden und Eigenschaften zum Erstellen einer protokollspezifischen Antwort bereitstellt, die das austauschbare Protokollmodell .NET Framework passt.  Anwendungen, die die <xref:System.Net.WebRequest>\-Klasse verwenden, um Daten von den Ressourcen anzufordern, empfangen die Antworten in **WebResponse**.  Protokollspezifische **WebResponse** Nachfolger müssen die abstrakten Member der **WebResponse**\-Klasse implementieren.  
  
 Die zugeordnete **WebRequest**\-Klasse muss **WebResponse** Nachfolger erstellen.  Beispielsweise werden <xref:System.Net.HttpWebResponse>\-Instanzen nur als Ergebnis des Aufrufens von <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=fullName> oder von <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=fullName> erstellt.  Jedes **WebResponse** enthält das Ergebnis einer Anforderung an eine Ressource und ist nicht für wiederverwendet wird.  
  
## ContentLength\-Eigenschaft  
 Die <xref:System.Net.WebResponse.ContentLength%2A>\-Eigenschaft gibt die Anzahl der Bytes an Daten, die vom Stream verfügbar sind, der durch die <xref:System.Net.WebResponse.GetResponseStream%2A>\-Methode zurückgegeben wird.  Die **ContentLength**\-Eigenschaft gibt nicht die Anzahl der Bytes Header oder Metadateninformationen an, die vom Server zurückgegeben werden; sie gibt nur die Anzahl der Datenbytes in der angeforderten Ressource selbst an.  
  
## ContentType\-Eigenschaft  
 Die <xref:System.Net.WebResponse.ContentType%2A>\-Eigenschaft enthält spezielle Informationen, die das Protokoll verlangt, an den Client zu senden, um den Inhaltstyp zu identifizieren, der vom Server gesendet wird.  In der Regel ist dies der MIME\-Inhaltstyp aller zurückgegebenen Daten.  
  
## Header\-Eigenschaft  
 Die <xref:System.Net.WebResponse.Headers%2A>\-Eigenschaft enthält eine beliebige Auflistung Name\-Wert\-Paare Metadaten, die mit der Antwort zugeordnet werden.  Alle Metadaten, die vom Protokoll benötigt werden, das als Name\-Wert\-Paar ausgedrückt werden kann, können in der **Headers**\-Eigenschaft enthalten sind.  
  
 Es ist nicht erforderlich, die **Headers**\-Eigenschaft verwenden, um Headermetadaten zu verwenden.  Protokollspezifische Metadaten können als Eigenschaften verfügbar gemacht werden, beispielsweise macht die <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=fullName>\-Eigenschaft den Header **Last\-Modified** HTTP verfügbar.  Wenn Sie Headermetadaten als Eigenschaft verfügbar machen, sollten Sie nicht zulassen, dass die gleiche Eigenschaft mithilfe der **Headers**\-Eigenschaft festgelegt wird.  
  
## ResponseUri\-Eigenschaft  
 Die <xref:System.Net.WebResponse.ResponseUri%2A>\-Eigenschaft enthält den URI der Ressource, die eigentlich die Antwort bereitgestellt hat.  Für Protokolle, die Umleitung nicht unterstützen, ist **ResponseUri** dasselbe wie die <xref:System.Net.WebRequest.RequestUri%2A>\-Eigenschaft von **WebRequest**, das die Antwort erstellt hat.  Wenn das Protokoll das Umleiten der Anforderung unterstützt, enthält **ResponseUri** der URI der Antwort.  
  
## Klicken Sie Methode  
 Die <xref:System.Net.WebResponse.Close%2A>\-Methode schließt alle Beziehungen, die durch die Anforderung und die Antwort hergestellt werden und daher werden die Ressourcen auf, die von der Antwort verwendet werden.  Die **Schließen**\-Methode schließt alle Streaminstanzen, die durch die Antwort verwendet werden, aber sie löst keine Ausnahme aus, wenn der Antwortstream zuvor durch einen Aufruf der <xref:System.IO.Stream.Close%2A?displayProperty=fullName>\-Methode geschlossen wurde.  
  
## GetResponseStream\-Methode  
 Die <xref:System.Net.WebResponse.GetResponseStream%2A>\-Methode gibt einen Stream zurück, der die Antwort von der angeforderten Ressource enthält.  Der Antwortstream enthält nur die Daten, die durch die Ressource zurückgegeben werden; aller Header oder Metadaten, die in der Antwort enthalten sind, sollten der Antwort und verfügbar gemacht werden der Anwendung durch protokollspezifische Eigenschaften oder die **Headers**\-Eigenschaft entfernt werden.  
  
 Die Streaminstanz, die von der **GetResponseStream**\-Methode zurückgegeben wird, wird durch die Anwendung gehört und kann geschlossen werden, ohne **WebResponse** zu schließen.  Standardmäßig schließt das Aufrufen der **WebResponse.Close**\-Methode auch den Stream, der von **GetResponse** zurückgegeben wird.  
  
## Siehe auch  
 <xref:System.Net.WebResponse>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.FileWebResponse>   
 [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Ableiten von WebRequest](../../../docs/framework/network-programming/deriving-from-webrequest.md)