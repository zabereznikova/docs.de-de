---
title: Toolboxdienst
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b3ea56d28d202bd8356fea1783b6675a708631d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516190"
---
# <a name="toolbox-service"></a>Toolboxdienst
Dieses Beispiel veranschaulicht, wie die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Toolboxaktivitäten auf Grundlage des Kontexts des Workflows aktualisiert werden. Das Beispiel enthält einen Workflow, der den Toolboxinhalt danach ändert, ob eine benutzerdefinierte Aktivität ausgewählt wird.  
  
## <a name="discussion"></a>Diskussion  
 Während der Workflowerstellung soll die Toolbox im Allgemeinen kontextbezogen sein. Der Benutzer möchte z. B. sicherstellen, dass die Toolbox einige zusätzliche Aktivitäten anzeigt, wenn dem Workflow eine bestimmte Aktivität hinzugefügt wird. Wenn die Aktivitäten aus dem Workflow entfernt werden, sollte die Toolbox angemessen auf Grundlage der Domänenanforderungen reagieren.  
  
 In einem neu gehosteten Workflow-Designer steuern Sie das Toolbox-Steuerelement und können sicherstellen, dass der Host entsprechende Änderungen im Toolbox-Steuerelement auf Grundlage der Modelländerungen im Workflow auslöst. In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] wird die Toolbox jedoch nicht vom Benutzer gesteuert, und deshalb ist eine Schnittstelle erforderlich, um den Inhalt zu ändern. `IActivityToolboxService` ist diese Schnittstelle.  
  
 Die API stellt die folgenden vier Methoden bereit.  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "WorkflowSimulator.sln".  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Öffnen Sie die Datei "Workflow.xaml".  
  
4.  Hinzufügen einer **CustomActivity** per Drag & Drop aus der Toolbox. Beachten Sie, die eine zusätzliche Toolboxkategorie: **neue WF-Kategorie** mit einer zusätzlichen Aktivität **zuweisen**.  
  
5.  Deaktivieren Sie nun die **CustomActivity** durch eine andere Aktivität hinein ziehen.  
  
6.  Das Element **zuweisen** in der Kategorie **neue WF-Kategorie** in der Toolbox wird jetzt entfernt. Da es in der Kategorie keine Elemente mehr gibt, wird auch die Kategorie entfernt.  
  
7.  Wählen Sie die **CustomActivity** erneut und die Kategorie und **zuweisen** Aktivität wieder hinzugefügt wird.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
