---
title: Verwenden von Auflistungsaktivitäten
ms.date: 03/30/2017
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
ms.openlocfilehash: a92208583ddf1c0d5d85b5af6a250a15ac8851b9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422626"
---
# <a name="using-collection-activities"></a>Verwenden von Auflistungsaktivitäten
In diesem Beispiel wird veranschaulicht, wie die Auflistungsaktivitäten mit (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601> und <xref:System.Activities.Statements.RemoveFromCollection%601>) mit einer Klasse verwendet werden, die die <xref:System.Collections.ICollection>-Schnittstelle implementiert, und wie eine benutzerdefinierte Aktivität erstellt wird, die eine Auflistung durchläuft, um den Inhalt jedes Elements in der Auflistung auszugeben. Die benutzerdefinierte Aktivität mit dem Namen `PrintCollection` gibt die Elementmember einer Auflistung mit dem Namen `Numbers` in der Konsole aus.  
  
 In der folgenden Tabelle werden die vier Aktivitäten beschrieben, die eine Auflistungsbearbeitung für Workflows bereitstellen.  
  
|Name der Aktivität|Beschreibung|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|Fügt einer Auflistung ein Element hinzu.|  
|<xref:System.Activities.Statements.ClearCollection%601>|Löscht alle Elemente aus einer Auflistung.|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|Gibt `true` zurück, wenn das angegebene Element in einer Auflistung vorhanden ist.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|Entfernt ein Element aus einer Auflistung.|  
  
 Das Beispiel besteht aus zwei Projektmappen, eine im Verzeichnis "CodedWorkflow", und die andere im Verzeichnis "DesignerWorkflow". Diese veranschaulichen zwei verschiedene Möglichkeiten der Verwendung der Aktivitäten zu den gleichen Zwecken.  
  
|Lösung|Beschreibung|Hauptdateien|  
|-|-|-|  
|CodedWorkflow|Beispielclientanwendung, die veranschaulicht, wie die Auflistungsaktivitäten programmgesteuert aufgerufen werden.|**PrintCollection.cs**: hilfsaktivität an die Konsole ausgeben jedes Element in einer Auflistung.<br /><br /> **"Program.cs"**: erstellt programmgesteuert eine Sequenzaktivität, die eine Reihe von auflistungsaktivitäten enthält, und führt diese.|  
|DesignerWorkflow|Beispielclientanwendung, die veranschaulicht, wie die Auflistungsaktivitäten im Workflow-Designer deklarativ verwendet werden.|**CollectionWorkflow.xaml**: eines Workflows deklarativ erstellt, mit dem Designer, der die auflistungsaktivitäten verwendet.<br /><br /> **PrintCollection.cs**: hilfsaktivität an die Konsole ausgeben jedes Element in einer Auflistung.<br /><br /> **"Program.cs"**: Ruft den Workflow in CollectionWorkflow.xaml beschrieben.|  
  
 In der Demo werden die Elementmember der Auflistung `Numbers` mit einer individuell definierten Aktivität mit dem Namen `PrintCollection` in der Konsole ausgegeben.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "Collection.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`