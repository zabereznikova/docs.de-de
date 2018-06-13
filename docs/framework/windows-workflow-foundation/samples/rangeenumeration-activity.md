---
title: RangeEnumeration-Aktivität
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: 9aa04c80f20e2d410fb49e2d07d836c8c5ab1b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516577"
---
# <a name="rangeenumeration-activity"></a>RangeEnumeration-Aktivität
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die eine Auflistung von Zahlen durchläuft. In der folgenden Tabelle sind die wichtigsten in dem Beispiel enthaltenen Dateien aufgeführt.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|RangeEnumeration.cs|Definiert eine benutzerdefinierte Aktivität mit dem Namen `RangeEnumeration`, die die<xref:System.Activities.NativeActivity>-Klasse überschreibt und eine Reihe von Zahlen durchläuft.|  
|RangeEnumerationSample.cs|Eine Clientanwendung, die die `RangeEnumeration`-Aktivität verwendet, um eine Auflistung von Zahlen zu durchlaufen.|  
  
 In der folgenden Tabelle sind die Eigenschaften der `RangeEnumeration`-Aktivität aufgeführt.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|Starten|Die Ganzzahl, bei der die Schleife gestartet wird.|  
|Stop|Die Ganzzahl, bei der die Schleife beendet wird.|  
|Schritt|Gibt den Umfang für jedes Durchlaufen an.|  
|Body|Gibt den während jeder Iteration auszuführenden Code an.|  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "RangeEnumeration.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`