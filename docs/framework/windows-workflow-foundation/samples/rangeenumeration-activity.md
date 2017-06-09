---
title: "RangeEnumeration-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# RangeEnumeration-Aktivit&#228;t
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die eine Auflistung von Zahlen durchläuft. In der folgenden Tabelle sind die wichtigsten in dem Beispiel enthaltenen Dateien aufgeführt.  
  
|Dateiname|Beschreibung|  
|---------------|------------------|  
|RangeEnumeration.cs|Definiert eine benutzerdefinierte Aktivität mit dem Namen `RangeEnumeration`, die die<xref:System.Activities.NativeActivity>\-Klasse überschreibt und eine Reihe von Zahlen durchläuft.|  
|RangeEnumerationSample.cs|Eine Clientanwendung, die die `RangeEnumeration`\-Aktivität verwendet, um eine Auflistung von Zahlen zu durchlaufen.|  
  
 In der folgenden Tabelle sind die Eigenschaften der `RangeEnumeration`\-Aktivität aufgeführt.  
  
|Eigenschaft|Beschreibung|  
|-----------------|------------------|  
|Start|Die Ganzzahl, bei der die Schleife gestartet wird.|  
|Stop|Die Ganzzahl, bei der die Schleife beendet wird.|  
|Schritt 1|Gibt den Umfang für jedes Durchlaufen an.|  
|Body|Gibt den während jeder Iteration auszuführenden Code an.|  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "RangeEnumeration.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`  
  
## Siehe auch