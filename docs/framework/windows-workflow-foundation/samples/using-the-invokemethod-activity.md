---
title: Verwenden der InvokeMethod-Aktivität
ms.date: 03/30/2017
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
ms.openlocfilehash: f6e32d002a4a2002037a6d74c5a2c3e275568efb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-invokemethod-activity"></a>Verwenden der InvokeMethod-Aktivität
Dieses Beispiel veranschaulicht, wie die <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Aktivität, um öffentliche Methoden in öffentlichen Klassen aufzurufen. Die <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) -Aktivität ermöglicht einem Workflow, Methoden für Objekte aufzurufen, Parameter zu übergeben, den Rückgabewert abzurufen, Typen für generische Methoden anzugeben und anzugeben, ob die Methode synchron ist oder asynchrone. 
  
Ist eine nicht generische Version der der <xref:System.Activities.Statements.InvokeMethod> Aktivität, die der Rückgabewert auf festgelegt ist, die <xref:System.Activities.Statements.InvokeMethod.Result%2A> -Eigenschaft und eine generische Version von der <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Aktivität, die der Rückgabewert zurückgegeben, über die <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) Eigenschaft vom Typ `TResult`. 
  
 In diesem Beispiel wird veranschaulicht, wie verschiedene Methodentypen aufgerufen werden. In der folgenden Liste sind die in diesem Beispiel veranschaulichten Methodentypen aufgeführt:  
  
-   Rufen Sie eine Instanzmethode ohne Parameter auf.  
  
-   Rufen Sie eine Instanzmethode mit zwei Parametern (System.String und System.Int32) auf.  
  
-   Rufen Sie eine Instanzmethode mit zwei Parametern (System.String und System.Int32) und einem Parameterarray vom Typ System.String[] auf.  
  
-   Rufen Sie eine Instanzmethode mit zwei Parametern (zwei System.Int32-Nummern) und einem Ergebnis vom Typ System.Int32 auf.  
  
     Der Rückgabewert ist an eine Variable gebunden und wird mit der <xref:System.Activities.Statements.WriteLine>-Aktivität auf der Konsole ausgegeben.  
  
-   Rufen Sie eine statische Methode mit zwei Parametern (System.String und System.Int32) auf.  
  
-   Rufen Sie eine Instanzmethode mit einem generischen Parameter (System.String) auf.  
  
-   Rufen Sie eine statische Methode mit zwei generischen Parametern (System.String und System.Int32) auf.  
  
-   Rufen Sie eine Instanzmethode auf, bei der ein Parameter als Verweis übergeben wird (System.String).  
  
     Der Parameter, auf den verwiesen wird, ist an eine Variable gebunden und wird mit der <xref:System.Activities.Statements.WriteLine>-Aktivität auf der Konsole ausgegeben.  
  
-   Rufen Sie eine asynchrone Instanzmethode auf.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei InvokeMethodUsage.sln.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`