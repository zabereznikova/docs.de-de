---
title: "Benutzerdefinierte Aktivit&#228;t „Hello World“ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Benutzerdefinierte Aktivit&#228;t „Hello World“
In diesem Beispiel werden mehrere Hauptfunktionen von [!INCLUDE[wf](../../../../includes/wf-md.md)] veranschaulicht, einschließlich der Erstellung einer einfachen benutzerdefinierten Aktivität.Einige der Funktionen, die in diesem Beispiel veranschaulicht werden, erstellen eine benutzerdefinierte Aktivität in C\# und verwenden `in`\-Argumente und `out`\-Argumente \(<xref:System.Activities.InArgument> und <xref:System.Activities.OutArgument>\).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## Erstellen eines Workflows in Code  
 In diesem Beispiel werden zwei benutzerdefinierte Aktivitäten mit C\#\-Code erstellt.Beide benutzerdefinierten Aktivitäten erben direkt oder indirekt von <xref:System.Activities.Activity%601>, um einen einzelnen Wert zurückzugeben.Der Vorteil der Verwendung des generischen Rückgabewerts, statt von der nicht generischen <xref:System.Activities.Activity>\-Klasse zu erben, ist, dass einige Aktivitäten \(z. B. <xref:System.Activities.Statements.Assign>\) in der Lage sind, auf den Rückgabewert zuzugreifen, wenn sie als Teil einer zusammengesetzten Aktivität verwendet werden.  
  
 AppendString  
 Diese Aktivität erbt von <xref:System.Activities.Activity%601> und verwendet eine <xref:System.Activities.Statements.Assign>\-Aktivität, die zwei Zeichenfolgen verkettet.  
  
 PrependString  
 Diese Aktivität erbt direkt von <xref:System.Activities.CodeActivity%601> und erstellt eine ähnliche Funktionalität wie die `AppendString`\-Aktivität, die in Code implementierte Logik verwendet, und nicht aus einer bereits vorhandenen Aktivität zusammengesetzt wird.  
  
 Die folgenden Dateien sind in diesem Projekt enthalten.  
  
 AppendString.cs  
 Die benutzerdefinierte Aktivität, die Zeichenfolgen zusammenfügt.Sie nimmt eine Zeichenfolge an und kombiniert sie mit einer literalen Textzeichenfolge "Hello World", sodass eine vollständige Meldung als Ausgabe gebildet wird.  
  
 PrependString.cs  
 Diese Aktivität stellt einer Eingabezeichenfolge eine vordefinierte Zeichenfolge voran.  
  
 Sequence1.xaml  
 Ein Workflow, der die benutzerdefinierten Aktivitäten `AppendString` und `PrependString` verwendet.  
  
 Program.cs  
 Ein Programm, das den Workflow ausführt.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "HelloWorld.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
## Siehe auch