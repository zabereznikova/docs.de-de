---
title: "InvokeMethod | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# InvokeMethod
In diesem Beispiel werden die verschiedenen Möglichkeiten zum Aufrufen von Methoden einer Klasse mit der <xref:System.Activities.Statements.InvokeMethod>\-Aktivität veranschaulicht.  
  
 Eine Methode gehört zu einer Klasse und stellt eine in sich abgeschlossene Gruppe von Vorgängen dar.Mit der <xref:System.Activities.Statements.InvokeMethod>\-Aktivität können Sie Methoden für Objekte oder Typen aufrufen, Parameter übergeben und den Rückgabewert abrufen.Methoden können synchron oder asynchron aufgerufen werden.  
  
## Beispieldetails  
 In diesem Beispiel werden die folgenden Szenarios mit der <xref:System.Activities.Statements.InvokeMethod>\-Aktivität ausgeführt:  
  
1.  Aufrufen einer Instanzmethode ohne Parameter.  
  
2.  Aufrufen einer Instanzmethode mit zwei Parametern \(<xref:System.String> und <xref:System.Int32>\).  
  
3.  Aufrufen einer Instanzmethode mit zwei Parametern \(<xref:System.String> und <xref:System.Int32>\) und einem Parameterarray vom Typ <xref:System.String>\[\].  
  
4.  Aufrufen einer Instanzmethode mit zwei Parametern vom Typ <xref:System.Int32> und einem Ergebnis vom Typ <xref:System.Int32>.In diesem Szenario wird der Ergebniswert an eine Variable gebunden und in einer anderen Aktivität verwendet.Der Wert wird mit der <xref:System.Activities.Statements.WriteLine>\-Aktivität in der Konsole angezeigt.  
  
5.  Aufrufen einer statischen Methode mit zwei Parametern vom Typ <xref:System.String> und <xref:System.Int32>.  
  
6.  Aufrufen einer Instanzmethode mit einem generischen Parameter vom Typ <xref:System.String>.  
  
7.  Aufrufen einer statischen Methode mit zwei generischen Parametern vom Typ <xref:System.String> und <xref:System.Int32>.  
  
8.  Aufrufen einer Instanzmethode mit einem als Verweis übergebenen Parameter vom Typ <xref:System.String>.In diesem Szenario wird der Verweisparameter an eine Variable \(`outParam`\) gebunden und in einer anderen Aktivität verwendet.Der Wert wird mit der <xref:System.Activities.Statements.WriteLine>\-Aktivität in der Konsole angezeigt.  
  
9. Aufrufen einer asynchronen Instanzmethode.  
  
10. Aufrufen von zwei unterschiedlichen Methoden für dieselbe Instanz eines Objekts mit zwei <xref:System.Activities.Statements.InvokeMethod>\-Aktivitäten.  
  
11. Speichern eines Werts in einer Objektinstanz.  
  
12. Abrufen eines Werts aus einer Objektinstanz.  
  
## So verwenden Sie dieses Beispiel  
 Dieses Beispiel wird in zwei Versionen bereitgestellt.Die erste Version dieses Beispiels veranschaulicht die Verwendung von <xref:System.Activities.Statements.InvokeMethod> mit C\#\-Code und dem [!INCLUDE[wf](../../../../includes/wf-md.md)]\-Programmiermodell und befindet sich im Ordner "CodedWorkflow\\CS".Die zweite Version veranschaulicht die Verwendung von <xref:System.Activities.Statements.InvokeMethod> mit XAML und befindet sich im Ordner "DesignerWorkflow\\CS".  
  
#### So führen Sie das Codebeispiel aus  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "InvokeMethodUsage.sln" im Ordner "CodedWorkflow\\CS".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
#### So führen Sie das XAML\-Beispiel aus  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "InvokeMethodUsage.sln" im Ordner "DesignerWorkflow\\CS".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie den Vorgang fortsetzen.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`  
  
## Siehe auch