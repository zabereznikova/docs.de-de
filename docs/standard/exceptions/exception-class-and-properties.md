---
title: "Exception-Klasse und Exception-Eigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ausnahmeklasse"
  - "Ausnahmen, Ausnahmeklasse"
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Exception-Klasse und Exception-Eigenschaften
Die <xref:System.Exception>\-Klasse ist die Basisklasse, von der Ausnahmen erben.  Die meisten Ausnahmeobjekte sind Instanzen einer von  **Exception** abgeleiteten Klasse . Es können jedoch beliebige Objekte als Ausnahme ausgelöst werden, die von der <xref:System.Object>\-Klasse abgeleitet sind.  Beachten Sie, dass nicht alle Sprachen das Auslösen und Abfangen von Objekten unterstützen, die nicht von der **Exception**\-Klasse abgeleitet wurden.  In fast allen Fällen ist es ratsam, nur **Exception**\-Objekte auszulösen und abzufangen.  
  
 Die **Exception**\-Klasse verfügt über verschiedene Eigenschaften, die zum Verständnis einer Ausnahme beitragen.  Diese Eigenschaften beinhalten:  
  
-   Die <xref:System.Exception.StackTrace%2A>\-Eigenschaft  
  
     Diese Eigenschaft enthält eine Stapelüberwachung, mit deren Hilfe ermittelt werden kann, wo ein Fehler aufgetreten ist.  Die Stapelüberwachung beinhaltet den Quelldateinamen und die Programmzeilennummer, falls Debuginformationen verfügbar sind.  
  
-   Die <xref:System.Exception.InnerException%2A>\-Eigenschaft  
  
     Mit dieser Eigenschaft können während der Ausnahmebehandlung eine Reihe von Ausnahmen erstellt und erhalten werden.  Verwenden Sie diese Eigenschaft, um eine neue Ausnahme zu erstellen, die vorher abgefangene Ausnahmen enthält.  Die ursprüngliche Ausnahme kann durch die zweite Ausnahme in der **InnerException**\-Eigenschaft abgefangen werden. Dadurch können die zusätzlichen Informationen von dem Code ausgewertet werden, der die zweite Ausnahme behandelt.  
  
     Ein Beispiel: Angenommen, Sie verfügen über eine Methode, die eine Datei liest und die Daten formatiert.  Der Code versucht, die Datei zu lesen, aber eine FileException\-Ausnahme wird ausgelöst.  Diese Ausnahme wird durch die Methode abgefangen, und es wird eine BadFormatException\-Ausnahme ausgelöst.  In diesem Fall kann die FileException\-Ausnahme in der **InnerException**\-Eigenschaft der BadFormatException\-Ausnahme gespeichert werden.  
  
     Damit der Aufrufer leichter ermitteln kann, warum eine Ausnahme ausgelöst wurde, ist es für eine Methode manchmal nützlich, die von einer Hilfsfunktion ausgelöste Ausnahme abzufangen und dann eine Ausnahme auszulösen, die den aufgetretenen Fehler besser verdeutlicht.  Eine neue, aussagekräftigere Ausnahme kann erstellt werden, wobei als Verweis zur inneren Ausnahme die ursprüngliche Ausnahme festgelegt werden kann.  Diese aussagekräftige Ausnahme kann dann für den Aufrufer ausgelöst werden.  Beachten Sie, dass Sie mit dieser Funktion eine Reihe von verknüpften Ausnahmen erstellen können, die mit der zuerst ausgelösten Ausnahme endet.  
  
-   Die <xref:System.Exception.Message%2A>\-Eigenschaft  
  
     Diese Eigenschaft enthält nähere Angaben über die Ursache einer Ausnahme.  Die **Message** wird in der Sprache angezeigt, die in der <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=fullName>\-Eigenschaft des Threads angegeben ist, der die Ausnahme auslöst.  
  
-   Die <xref:System.Exception.HelpLink%2A>\-Eigenschaft  
  
     Diese Eigenschaft kann eine URL \(oder URN\) zu einer Hilfedatei enthalten, die ausführliche Informationen über die Ursache der Ausnahme enthält.  
  
-   Die <xref:System.Exception.Data%2A>\-Eigenschaft.  
  
     Diese Eigenschaft stellt ein IDictionary dar, in dem beliebige Daten in Schlüssel\-Wert\-Paaren enthalten sind.  
  
 Fast alle Klassen, die von der **Exception**\-Klasse erben, implementieren keine weiteren Member oder stellen keine zusätzlichen Funktionen bereit; sie erben lediglich von der **Exception**\-Klasse.  Daher sind die wichtigsten Informationen über eine Ausnahme in der Ausnahmehierarchie, in der Bezeichnung und in den in ihr selbst enthaltenen Informationen enthalten.  
  
## Siehe auch  
 [Ausnahmenhierarchie](../../../docs/standard/exceptions/exception-hierarchy.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Best Practices für Ausnahmen](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Ausnahmen](../../../docs/standard/exceptions/index.md)