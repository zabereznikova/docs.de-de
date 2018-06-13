---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 489d27e05c96d3b3893052254a879d1c9d75788c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515622"
---
# <a name="overloadgroups"></a>OverloadGroups
Dieses Beispiel besteht aus einer Aktivität (`CreateLocation`), die zwei interessante Eigenschaften aufweist:  
  
1.  Sie verfügt über erforderliche und optionale Argumente.  
  
2.  Sie ermöglicht dem Benutzer, einen von zwei unterschiedlichen Argumentsätzen bereitzustellen.  
  
 Dieses Verhalten wird mit den folgenden beiden Funktionen erzielt:  
  
-   `[isRequired]` überprüft, ob eine Eigenschaft einer bestimmten Aktivität zugewiesen ist; falls nicht, wird eine Ausnahme ausgelöst.  
  
-   `[OverloadGroup]` setzt einen Satz von Argumenten zusammen, damit der Benutzer der Aktivität eine Auswahl zwischen diesen treffen kann. Der Benutzer kann keine Argumente aus anderen Überladungsgruppen in der gleichen Instanz verwenden.  
  
 Rufen Sie nach dem Einrichtigen unterschiedlicher Workflows <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> auf, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.Constraint> zurückgegeben wird. Geben Sie die <xref:System.Activities.Validation.Constraint>-Objekte auf der Konsole aus.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen der **OverloadGroups.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
