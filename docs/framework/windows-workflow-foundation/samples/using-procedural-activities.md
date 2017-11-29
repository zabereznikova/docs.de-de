---
title: "Verwenden von Verfahrensaktivitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c391316959829c77d16dd87af51d9fe1915dc88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-procedural-activities"></a>Verwenden von Verfahrensaktivitäten
Im Beispiel werden die Aktivitäten <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> und <xref:System.Activities.Statements.WriteLine> verwendet, um ein Ratespiel zu implementieren. Bei dem Ratespiel wird eine Zufallszahl ausgewählt, die der Spieler erraten muss. Wenn der Spieler die falsche Zahl eingibt, stellt der Workflow einen Hinweis bereit, ob die zu erratende Zahl höher oder niedriger ist. Wenn der Spieler die Zahl in weniger als sieben Versuchen errät, wird eine Glückwunschmeldung angezeigt.  
  
## <a name="custom-activities-in-this-sample"></a>Benutzerdefinierte Aktivitäten in diesem Beispiel  
  
### <a name="readline"></a>ReadLine  
 Liest eine Textzeile aus der Konsole. Diese Aktivität ist von der <xref:System.Activities.NativeActivity>-Klasse abgeleitet und erstellt ein Lesezeichen zur Wiederaufnahme durch die Konsolenanwendung nach dem Lesen einer Zeile.  
  
### <a name="promptint"></a>PromptInt  
 Fordert den Benutzer auf, eine Zahl einzugeben, und liest diese aus einem Konsolenfenster. Die Aktivität ist von <xref:System.Activities.Activity%601> abgeleitet und verwendet die <xref:System.Activities.Statements.WriteLine>-Aktivität und die `ReadLine`-Aktivität.  
  
##### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "GuessingGame.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## <a name="see-also"></a>Siehe auch
