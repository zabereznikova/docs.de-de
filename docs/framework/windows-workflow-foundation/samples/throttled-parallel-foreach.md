---
title: "Parallel ForEach (eingeschr&#228;nkt) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Parallel ForEach (eingeschr&#228;nkt)
Die `ThrottleParallelForEach`\-Aktivität ist der <xref:System.Activities.Statements.ParallelForEach>\-Aktivität ähnlich, mit der einen Ausnahme, dass sie das Einstellen eines Parallelitätsfaktors zur Einschränkung der Anzahl gleichzeitiger auszuführender Verzweigungen ermöglicht.Die `ThrottleParallelForEach`\-Aktivität wird von <xref:System.Activities.NativeActivity> abgeleitet, da sie andere Aktivitäten \(die untergeordneten Aktivitäten\) planen muss und darauf nur über die <xref:System.Activities.NativeActivityContext>\-Klasse zugegriffen werden kann.  
  
## Projekte  
  
||||  
|-|-|-|  
|**ProjectName**|**Beschreibung**|**Hauptdateien**|  
|ThrottledParallelForEach|Enthält die `ThrottledParallelForEach`\-Aktivität und ihren Designer.|ThrottledParallelForEach.cs<br /><br /> Die `ThrottledParallelForEach`\-Aktivitätsdefinition.|  
|CodeTestClient|Beispielclientanwendung, die einen Workflow mithilfe von imperativem Code mit `ThrottledParallelForEach` konfiguriert ausführt.|Program.cs<br /><br /> Definiert eine Instanz des Beispielworkflows und führt sie aus.|  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei "ThrottledParallelForEach.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`  
  
## Siehe auch