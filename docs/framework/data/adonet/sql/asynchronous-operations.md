---
title: "Asynchrone Vorg&#228;nge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Asynchrone Vorg&#228;nge
Einige Datenbankoperationen wie das Ausführen von Befehlen können einige Zeit bis zur Beendigung in Anspruch nehmen.  In diesem Fall müssen Singlethread\-Anwendungen andere Operationen blockieren und auf die Beendigung des Befehls warten, bevor sie mit eigenen Operationen fortfahren können.  Es ist jedoch auch möglich, dass der Vordergrundthread während der Operation aktiv bleibt, wenn der länger dauernde Vorgang einem Hintergrundthread zugewiesen werden kann.  In einer Windows\-Anwendung bleibt beispielsweise der Benutzeroberflächenthread beim Ausführen des Vorgangs reaktionsfähig, wenn die länger dauernde Operation an einen Hintergrundthread delegiert wird.  
  
 .NET Framework stellt mehrere asynchrone Standardentwurfsmuster bereit, mit denen Entwickler die Vorteile der Hintergrundthreads nutzen können und die dem Benutzeroberflächenthread oder Threads mit hoher Priorität die Möglichkeit geben, andere Operationen zu beenden.  ADO.NET unterstützt dieselben Entwurfsmuster in seiner <xref:System.Data.SqlClient.SqlCommand>\-Klasse.  Insbesondere die Methoden <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> und <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> stellen zusammen mit den Methoden <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> und <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A> die asynchrone Unterstützung bereit.  
  
> [!NOTE]
>  Asynchrone Programmierung ist eine grundlegende Funktion von .NET Framework, und ADO.NET nutzt die Möglichkeiten der Standardentwurfsmuster vollständig.  Weitere Informationen zu den verschiedenen asynchronen Techniken, die den Entwicklern zur Verfügung stehen, finden Sie unter [Calling Synchronous Methods Asynchronously](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
 Auch wenn durch die Verwendung asynchroner Techniken mit ADO.NET\-Funktionen keine neuen Aspekte hinzugefügt werden, ist es wahrscheinlicher, dass Entwickler asynchrone Funktionen in ADO.NET verwenden als in anderen Bereichen von .NET Framework.  Es ist wichtig, mit den Vorteilen und potenziellen Fehlerquellen beim Erstellen von Multithread\-Anwendungen vertraut zu sein.  Die in diesem Abschnitt folgenden Beispiele verdeutlichen mehrere wichtige Aspekte, die Entwickler beim Erstellen von Anwendungen mit Multithreadfunktionalität berücksichtigen sollten.  
  
## In diesem Abschnitt  
 [Windows\-Anwendungen, die Rückrufe verwenden](../../../../../docs/framework/data/adonet/sql/windows-applications-using-callbacks.md)  
 Enthält ein Beispiel, das die sichere Ausführung eines asynchronen Befehls veranschaulicht. Dabei wird die Interaktion mit einem Formular und seinem Inhalt von einem anderen Thread aus ordnungsgemäß behandelt.  
  
 [ASP.NET\-Anwendungen mit 'Wait'\-Handles](../../../../../docs/framework/data/adonet/sql/aspnet-apps-using-wait-handles.md)  
 Enthält ein Beispiel, das die gleichzeitige Ausführung mehrerer Befehle von einer ASP.NET\-Seite aus veranschaulicht. Dabei werden Wait\-Handles zum Verwalten der Operation bei Beendigung aller Befehle verwendet.  
  
 [Abrufe in Konsolenanwendungen](../../../../../docs/framework/data/adonet/sql/polling-in-console-applications.md)  
 Enthält ein Beispiel, das die Verwendung von Abfragen veranschaulicht, mit denen von einer Konsolenanwendung auf die Beendigung der Ausführung eines asynchronen Befehls gewartet wird.  Diese Technik kann auch in einer Klassenbibliothek oder anderen Anwendungen ohne Benutzeroberfläche verwendet werden.  
  
## Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Calling Synchronous Methods Asynchronously](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)