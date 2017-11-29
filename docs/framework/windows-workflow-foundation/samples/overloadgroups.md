---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a5ab416dc484dddc0b6aa0ec25757921815c723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="overloadgroups"></a>OverloadGroups
Dieses Beispiel besteht aus einer Aktivität (`CreateLocation`), die zwei interessante Eigenschaften aufweist:  
  
1.  Sie verfügt über erforderliche und optionale Argumente.  
  
2.  Sie ermöglicht dem Benutzer, einen von zwei unterschiedlichen Argumentsätzen bereitzustellen.  
  
 Dieses Verhalten wird mit den folgenden beiden Funktionen erzielt:  
  
-   `[isRequired]` überprüft, ob eine Eigenschaft einer bestimmten Aktivität zugewiesen ist; falls nicht, wird eine Ausnahme ausgelöst.  
  
-   `[OverloadGroup]` setzt einen Satz von Argumenten zusammen, damit der Benutzer der Aktivität eine Auswahl zwischen diesen treffen kann. Der Benutzer kann keine Argumente aus anderen Überladungsgruppen in der gleichen Instanz verwenden.  
  
 Rufen Sie nach dem einrichtigen unterschiedlicher Workflows, <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> welche gibt eine <xref:System.Activities.Validation.ValidationResults> Auflistung von <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`. Drucken der <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` Objekte in die Konsole.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen der **OverloadGroups.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## <a name="see-also"></a>Siehe auch
