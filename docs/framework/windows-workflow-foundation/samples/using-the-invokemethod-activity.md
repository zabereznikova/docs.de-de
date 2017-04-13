---
title: "Verwenden der InvokeMethod-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Verwenden der InvokeMethod-Aktivit&#228;t
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Activities.Statements.InvokeMethod%601>\-Aktivität verwendet wird, um öffentliche Methoden in öffentlichen Klassen aufzurufen.Die <xref:System.Activities.Statements.InvokeMethod%601>\-Aktivität ermöglicht einem Workflow, Methoden für Objekte aufzurufen, Parameter zu übergeben, den Rückgabewert abzurufen, Typen für generische Methoden anzugeben und anzugeben, ob die Methode synchron oder asynchron ist.  
  
 Es gibt eine nicht generische Version der <xref:System.Activities.Statements.InvokeMethod>\-Aktivität, bei der der Rückgabewert auf die <xref:System.Activities.Statements.InvokeMethod.Result%2A>\-Eigenschaft und eine generische Version der <xref:System.Activities.Statements.InvokeMethod%601>\-Aktivität festgelegt wird, wobei der Rückgabewert durch die <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A>\-Eigenschaft vom Typ `TResult` zurückgegeben wird.  
  
 In diesem Beispiel wird veranschaulicht, wie verschiedene Methodentypen aufgerufen werden.In der folgenden Liste sind die in diesem Beispiel veranschaulichten Methodentypen aufgeführt:  
  
-   Rufen Sie eine Instanzmethode ohne Parameter auf.  
  
-   Rufen Sie eine Instanzmethode mit zwei Parametern \(System.String und System.Int32\) auf.  
  
-   Rufen Sie eine Instanzmethode mit zwei Parametern \(System.String und System.Int32\) und einem Parameterarray vom Typ System.String\[\] auf.  
  
-   Rufen Sie eine Instanzmethode mit zwei Parametern \(zwei System.Int32\-Nummern\) und einem Ergebnis vom Typ System.Int32 auf.  
  
     Der Rückgabewert ist an eine Variable gebunden und wird mit der <xref:System.Activities.Statements.WriteLine>\-Aktivität auf der Konsole ausgegeben.  
  
-   Rufen Sie eine statische Methode mit zwei Parametern \(System.String und System.Int32\) auf.  
  
-   Rufen Sie eine Instanzmethode mit einem generischen Parameter \(System.String\) auf.  
  
-   Rufen Sie eine statische Methode mit zwei generischen Parametern \(System.String und System.Int32\) auf.  
  
-   Rufen Sie eine Instanzmethode auf, bei der ein Parameter als Verweis übergeben wird \(System.String\).  
  
     Der Parameter, auf den verwiesen wird, ist an eine Variable gebunden und wird mit der <xref:System.Activities.Statements.WriteLine>\-Aktivität auf der Konsole ausgegeben.  
  
-   Rufen Sie eine asynchrone Instanzmethode auf.  
  
## So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei InvokeMethodUsage.sln.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`  
  
## Siehe auch