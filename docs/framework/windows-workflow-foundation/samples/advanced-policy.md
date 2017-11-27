---
title: Erweiterte Richtlinie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dd941509c37618480a20530d3f5239750917e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="advanced-policy"></a>Erweiterte Richtlinie
Dieses Beispiel erweitert das Beispiel für einfache Richtlinien. Zusätzlich zu den Rabattregeln für Privat- und Geschäftskunden aus dem Beispiel für eine einfache Richtlinie wurden mehrere neue Regeln hinzugefügt.  
  
 Es wurde eine Regel für hohe Werte hinzugefügt, wodurch ein höherer Rabatt für Bestellungen mit hohem Wert gewährt wird. Diese Regel erhält einen höheren Prioritätswert als die beiden vorhergehenden Regeln, sodass das Rabattfeld überschrieben wird und diese Regel Vorrang vor der Rabattregel für Privatkunden und Geschäftskunden hat.  
  
 Es wurde ebenso eine Regel zum Berechnen der Gesamtsumme hinzugefügt, mit der die Gesamtsumme hinsichtlich der Rabattstufe berechnet wird. Sie zeigt, wie eine in der Workflowaktivität definierte Methode referenziert und wie else-Aktionen verwendet werden. Diese Regel veranschaulicht außerdem das Verkettungsverhalten, da sie jedes Mal dann ausgewertet wird, wenn eine Änderung im Rabattfeld auftritt. Darüber hinaus wird die Attributzuweisung für Methoden mit RuleWriteAttribute für die CalculateTotal-Methode dargestellt. Dies führt dazu, dass betroffene Regeln (ErrorTotalRule) immer dann neu ausgewertet werden, wenn die Methode ausgeführt wird.  
  
 Die letzte hinzugefügte Regel dient der Fehlererkennung (in diesem Fall, wenn die Gesamtsumme geringer als 0 (null) ist). Wenn dies auftritt, wird die Richtlinienausführung unterbrochen.  
  
 Zuletzt wurden jeder Regel `Console.Writeline`-Aufrufe als Aktionen hinzugefügt, um die Sichtbarkeit der Regelausführung zu erhöhen, während ebenfalls aufgezeigt wird, dass es möglich ist, auf statische Methoden in referenzierten Typen zuzugreifen. Sie könnten die Überwachung auch verwenden, um die Sichtbarkeit von Regeln bei deren Ausführung zu erhöhen.  
  
 In diesem Beispiel werden die folgenden Regeln verwendet:  
  
 **ResidentialDiscountRule:**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule:**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule:**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule:**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **ErrorTotalRule:**  
  
 IF insgesamt \< 0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 Die Auswertung und Ausführung von Regeln kann außerdem über die Verfolgung und Überwachung beobachtet werden.  
  
### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1.  Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG+F5 drücken.  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
-   Führen Sie im Eingabeaufforderungsfenster des SDK die EXE-Datei im Ordner AdvancedPolicy\bin\debug aus (bzw. im Ordner AdvancedPolicy\bin für die Visual Basic-Version des Beispiels), der sich unter dem Hauptordner des Beispiels befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Einfache Richtlinie](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
