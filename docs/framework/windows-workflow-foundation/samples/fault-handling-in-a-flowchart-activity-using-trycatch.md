---
title: "Fehlerbehandlung in einer Flussdiagrammaktivit&#228;t mit TryCatch | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Fehlerbehandlung in einer Flussdiagrammaktivit&#228;t mit TryCatch
In diesem Beispiel wird gezeigt, wie die <xref:System.Activities.Statements.TryCatch>\-Aktivität innerhalb einer komplexen Ablaufsteuerungsaktivität verwendet werden kann.  
  
 In diesem Beispiel werden ein Promotionscode und eine Anzahl von Kindern als Variablen an eine <xref:System.Activities.Statements.Flowchart>\-Aktivität übergeben, die einen Rabatt auf Grundlage von Formeln berechnet, die dem Promotioncode entsprechen.Zum Beispiel gehören obligatorischer Code und Workflow\-Designer\-Versionen des Beispiels.  
  
 In der folgenden Tabelle werden die Variablen für die `CreateFlowchartWithFaults`\-Aktivität aufgelistet.  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|promoCode|Der Promotionscode.Typ: Zeichenfolge<br /><br /> Die möglichen Werte mit einer Beschreibung in Klammern:<br /><br /> -   Single \(Single\)<br />-   MNK \(verheiratet ohne Kinder\)<br />-   MWK \(verheiratet mit Kindern\)|  
|numKids|Die Anzahl der Kinder.Typ: int|  
  
 Die `CreateFlowchartWithFaults`\-Aktivität verwendet eine <xref:System.Activities.Statements.FlowSwitch%601>\-Aktivität, die auf das `promoCode`\-Argument umschaltet und den Rabatt mit der folgenden Formel berechnet.  
  
|Wert von `promoCode`|Rabatt \(%\)|  
|--------------------------|------------------|  
|Single|10|  
|MNK|15|  
|MWK|15 \+ \(1 – 1\/`numberOfKids`\)\*10 **Note:**  Potenziell kann diese Berechnung eine <xref:System.DivideByZeroException> auslösen.Deshalb wird die Rabattberechnung in eine <xref:System.Activities.Statements.TryCatch>\-Aktivität eingeschlossen, die die <xref:System.DivideByZeroException>\-Ausnahme abfängt und den Rabatt auf 0 \(null\) festlegt.|  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "FlowchartWithFaultHandling.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## Siehe auch  
 [Flussdiagrammworkflows](../../../../docs/framework/windows-workflow-foundation//flowchart-workflows.md)   
 [Ausnahmen](../../../../docs/framework/windows-workflow-foundation//exceptions.md)