---
title: "Erstellen von Konsolenanwendungen in .NET Framework | Microsoft Docs"
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
  - ".NET Framework, Erstellen von Konsolenanwendungen"
  - "Anwendungsentwicklung [.NET Framework], Konsole"
  - "Konsolenanwendungen"
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Erstellen von Konsolenanwendungen in .NET Framework
Anwendungen in .NET Framework können die <xref:System.Console?displayProperty=fullName>\-Klasse verwenden, um Zeichen aus der Konsole zu lesen und in ihr zu schreiben.  Daten aus der Konsole werden aus dem Standardeingabestream gelesen, in die Konsole eingehende Daten werden in den Standardausgabestream geschrieben. In die Konsole eingehende Fehlerdaten werden in den Standard\-Fehlerausgabestream geschrieben.  Diese Streams werden automatisch mit der Konsole verknüpft, wenn die Anwendung gestartet wird, und werden entsprechend als Eigenschaften <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> und <xref:System.Console.Error%2A> dargestellt.  
  
 Der Wert der <xref:System.Console.In%2A?displayProperty=fullName>\-Eigenschaft ist ein <xref:System.IO.TextReader?displayProperty=fullName>\-Objekt. Die Werte der Eigenschaften <xref:System.Console.Out%2A?displayProperty=fullName> und <xref:System.Console.Error%2A?displayProperty=fullName> hingegen sind <xref:System.IO.TextWriter?displayProperty=fullName>\-Objekte.  Sie können diese Eigenschaften mit Streams verknüpfen, die nicht für die Konsole stehen. So können Sie den Stream auf einen anderen Ort für eingehende oder ausgehende Daten lenken.  Sie können die Ausgabe zum Beispiel zu einer Datei umlenken, indem Sie die <xref:System.Console.Out%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.IO.StreamWriter?displayProperty=fullName> einstellen. Dadurch wird ein <xref:System.IO.FileStream?displayProperty=fullName> mit der <xref:System.Console.SetOut%2A?displayProperty=fullName>\-Methode gekapselt.  Die Eigenschaften <xref:System.Console.In%2A?displayProperty=fullName> und <xref:System.Console.Out%2A?displayProperty=fullName> müssen sich nicht auf denselben Stream beziehen.  
  
> [!NOTE]
>  Weitere Informationen zum Erstellen von Konsolenanwendungen, einschließlich Beispielen in C\#, Visual Basic und C\+\+, finden Sie in der Dokumentation zur <xref:System.Console>\-Klasse.  
  
 Wenn keine Konsole vorhanden ist, wie beispielsweise in einer Windows\-basierten Anwendung, ist die Ausgabe, die in den Standardausgabestream geschrieben wird, nicht sichtbar. Dies liegt daran, dass keine Konsole vorhanden ist, in die die Information geschrieben werden kann.  Werden Informationen in eine Konsole geschrieben, auf die nicht zugegriffen werden kann, wird keine Ausnahme ausgelöst.  
  
 Alternativ können Sie die Konsole für Lese\- und Schreibzugriff in einer Windows\-basierten Anwendung aktivieren, die mit Visual Studio entwickelt wurde. Öffnen Sie hierzu im Projekt das Dialogfenster **Eigenschaften**, klicken Sie auf die Registerkarte **Anwendung**, und stellen Sie den **Anwendungstyp** auf **Konsolenanwendung** ein.  
  
 Konsolenanwendungen verfügen nicht über eine Meldungsverteilschleife, die standardmäßig gestartet wird.  Daher können Konsolenaufrufe von Microsoft Win32\-Zeitgebern möglicherweise fehlschlagen.  
  
 Die **System.Console**\-Klasse verfügt über Methoden, die individuelle Zeichen oder ganze Zeilen aus der Konsole lesen können.  Andere Methoden konvertieren Daten und formatieren Zeichenfolgen. Dann schreiben sie die formatierten Zeichenfolgen in die Konsole.  Weitere Informationen zum Formatieren von Zeichenfolgen finden Sie unter [Formatierung von Typen](../../docs/standard/base-types/formatting-types.md).  
  
## Siehe auch  
 <xref:System.Console?displayProperty=fullName>   
 [Formatierung von Typen](../../docs/standard/base-types/formatting-types.md)