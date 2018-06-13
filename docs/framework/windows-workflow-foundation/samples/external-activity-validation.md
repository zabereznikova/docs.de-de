---
title: Externe Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
ms.openlocfilehash: 1ceb1d2b2f7e8926479fa4c53cfb82a5cdb3a83f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517799"
---
# <a name="external-activity-validation"></a>Externe Aktivitätsvalidierung
In diesem Beispiel wird gezeigt, wie einer integrierten Aktivität Validierungslogik hinzugefügt wird, die Sie nicht erstellt haben. Mit der Validierungslogik wird erzwungen, dass für alle im Workflow vorhandenen <xref:System.Activities.Statements.If>-Aktivitäten entweder die <xref:System.Activities.Statements.If.Then%2A>-Eigenschaft oder die <xref:System.Activities.Statements.If.Else%2A>-Eigenschaft festgelegt wird. Darüber hinaus wird mit der Validierungslogik geprüft, ob alle <xref:System.Activities.Statements.Pick>-Aktivitäten im Workflow mehr als eine Verzweigung aufweisen. Wenn das nicht der Fall ist, wird eine Warnung ausgegeben.  
  
## <a name="sample-details"></a>Beispieldetails  
 In diesem Beispiel wird ein Workflow mit einer Instanz der einzelnen zu prüfenden Aktivitäten erstellt: die <xref:System.Activities.Statements.If>-Aktivität und die <xref:System.Activities.Statements.Pick>-Aktivität. Für jedes Validierungsverhalten wird eine neue <xref:System.Activities.Validation.Constraint> erstellt. Die in diesem Beispiel erstellten Einschränkungen sind `ConstraintError_IfShouldHaveThenOrElse` und `ConstraintWarning_PickHasOneBranch`. Dann werden diese Einschränkungen der `AdditionalConstraints`-Auflistung einer <xref:System.Activities.Validation.ValidationSettings>-Instanz hinzugefügt. Abschließend wird die `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>-Methode von <xref:System.Activities.Validation.ActivityValidationServices> aufgerufen, um die Aktivitäten im Workflow zu überprüfen, und die Validierungsergebnisse werden auf der Konsole ausgegeben.  
  
> [!NOTE]
>  Sie können jeder Aktivität Richtlinieneinschränkungen hinzufügen. Sie können z. B. einer <xref:System.Activities.Statements.Sequence>-Aktivität oder einer <xref:System.Activities.Statements.Parallel>-Aktivität eine Richtlinieneinschränkung hinzufügen.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ExternalActivityValidation.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`