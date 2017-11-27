---
title: Verwenden des Bearbeitungsbereichs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79306f9e-318b-4687-9863-8b93d1841716
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6aec54cef13bcd99fb65a6305e086fe577b6bc13
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-editing-scope"></a>Verwenden des Bearbeitungsbereichs
In diesem Beispiel wird veranschaulicht, wie eine Gruppe von Änderungen stapelverarbeitet wird, sodass diese in einer einzigen automatischen Einheit rückgängig gemacht werden können. Die von einem Aktivitätsdesigner vorgenommenen Änderungen werden standardmäßig automatisch in das Rückgängig/Wiederholen-System integriert.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Bearbeitungsbereich und Rückgängig und Wiederholen.  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird veranschaulicht wie ein Satz von Änderungen an der <xref:System.Activities.Presentation.Model.ModelItem>-Struktur in einem einzelnen Arbeitsschritt als Stapel verarbeitet wird. Beachten Sie, dass beim Binden an <xref:System.Activities.Presentation.Model.ModelItem>-Werte direkt von einem WPF-Designer Änderungen automatisch übernommen werden. In diesem Beispiel wird veranschaulicht, was erforderlich ist, wenn mehrere Änderungen, die als Stapel verarbeitet werden sollen, durch imperativen Code vorgenommen werden, und nicht als eine Änderung.  
  
 In diesem Beispiel werden drei Aktivitäten hinzugefügt. Wenn Bearbeitung beginnt, wird <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> in einer Instanz von <xref:System.Activities.Presentation.Model.ModelItem> aufgerufen. An der <xref:System.Activities.Presentation.Model.ModelItem>-Struktur innerhalb dieses Bearbeitungsbereichs vorgenommene Änderungen werden als Stapel verarbeitet. Der <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>-Befehl gibt einen <xref:System.Activities.Presentation.Model.EditingScope> zurück, der verwendet werden kann, um diese Instanz zu steuern. <xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> oder <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A> kann aufgerufen werden, um einen Commit für den Bearbeitungsbereich auszuführen oder ihn wiederherzustellen.  
  
 Sie können auch <xref:System.Activities.Presentation.Model.EditingScope>-Objekte schachteln, sodass mehrere Sätze von Änderungen als Teil eines größeren Bearbeitungsbereichs verfolgt werden und einzeln gesteuert werden können. Ein Szenario für diese Funktion wäre, wenn ein Commit für Änderungen von mehreren Dialogfeldern ausgeführt werden muss oder sie getrennt wiederhergestellt werden müssen, wobei alle Änderungen als einzelner atomarischer Vorgang behandelt werden. In diesem Beispiel werden die Bearbeitungsbereiche mit <xref:System.Collections.ObjectModel.ObservableCollection%601> des Typs <xref:System.Activities.Presentation.Model.ModelEditingScope> gestapelt. <xref:System.Collections.ObjectModel.ObservableCollection%601> wird verwendet, damit die Tiefe der Schachtelung auf der Designeroberfläche angezeigt werden kann.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Erstellen Sie das Beispiel, und führen Sie es aus. Verwenden Sie dann die Schaltflächen links, um den Workflow zu ändern.  
  
2.  Klicken Sie auf **Bearbeitungsbereich öffnen**.  
  
    1.  Dieser Befehl ruft <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> auf, womit ein Bearbeitungsbereich erstellt und auf den Bearbeitungsstapel verschoben wird.  
  
    2.  Dem ausgewählten <xref:System.Activities.Presentation.Model.ModelItem> werden dann drei Aktivitäten hinzugefügt. Beachten Sie, dass, wenn der Bearbeitungsbereich nicht mit <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> geöffnet worden wäre, drei neue Aktivitäten auf dem Designerzeichenbereich angezeigt werden würden. Da dieser Vorgang immer noch in <xref:System.Activities.Presentation.Model.EditingScope> aussteht, wird der Designer noch nicht aktualisiert.  
  
3.  Drücken Sie **Bearbeitungsbereich schließen** um den Bearbeitungsbereich zu übernehmen. Drei Aktivitäten werden im Designer angezeigt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\UsingEditingScope`
