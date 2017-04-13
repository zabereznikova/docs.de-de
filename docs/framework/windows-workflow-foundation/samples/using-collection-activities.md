---
title: "Verwenden von Auflistungsaktivit&#228;ten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Verwenden von Auflistungsaktivit&#228;ten
In diesem Beispiel wird veranschaulicht, wie die Auflistungsaktivitäten mit \(<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601> und <xref:System.Activities.Statements.RemoveFromCollection%601>\) mit einer Klasse verwendet werden, die die <xref:System.Collections.ICollection>\-Schnittstelle implementiert, und wie eine benutzerdefinierte Aktivität erstellt wird, die eine Auflistung durchläuft, um den Inhalt jedes Elements in der Auflistung auszugeben.Die benutzerdefinierte Aktivität mit dem Namen `PrintCollection` gibt die Elementmember einer Auflistung mit dem Namen `Numbers` in der Konsole aus.  
  
 In der folgenden Tabelle werden die vier Aktivitäten beschrieben, die eine Auflistungsbearbeitung für Workflows bereitstellen.  
  
|Name der Aktivität|Beschreibung|  
|------------------------|------------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|Fügt einer Auflistung ein Element hinzu.|  
|<xref:System.Activities.Statements.ClearCollection%601>|Löscht alle Elemente aus einer Auflistung.|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|Gibt `true` zurück, wenn das angegebene Element in einer Auflistung vorhanden ist.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|Entfernt ein Element aus einer Auflistung.|  
  
 Das Beispiel besteht aus zwei Projektmappen, eine im Verzeichnis "CodedWorkflow", und die andere im Verzeichnis "DesignerWorkflow".Diese veranschaulichen zwei verschiedene Möglichkeiten der Verwendung der Aktivitäten zu den gleichen Zwecken.  
  
||||  
|-|-|-|  
|Projektmappe|Beschreibung|Hauptdateien|  
|CodedWorkflow|Beispielclientanwendung, die veranschaulicht, wie die Auflistungsaktivitäten programmgesteuert aufgerufen werden.|**PrintCollection.cs**: Hilfsaktivität zum Ausgeben der einzelnen Elemente in einer Auflistung auf der Konsole.<br /><br /> **Program.cs**: Erstellt programmgesteuert eine Sequenzaktivität, die eine Reihe von Auflistungsaktivitäten enthält, und führt diese aus.|  
|DesignerWorkflow|Beispielclientanwendung, die veranschaulicht, wie die Auflistungsaktivitäten im Workflow\-Designer deklarativ verwendet werden.|**CollectionWorkflow.xaml**: Ein Workflow, der deklarativ mit dem Designer erstellt wurde, der die Auflistungsaktivitäten verwendet.<br /><br /> **PrintCollection.cs**: Hilfsaktivität zum Ausgeben der einzelnen Elemente in einer Auflistung auf der Konsole.<br /><br /> **Program.cs**: Ruft den in "CollectionWorklflow.xaml" beschriebenen Workflow auf.|  
  
 In der Demo werden die Elementmember der Auflistung `Numbers` mit einer individuell definierten Aktivität mit dem Namen `PrintCollection` in der Konsole ausgegeben.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "Collection.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`  
  
## Siehe auch