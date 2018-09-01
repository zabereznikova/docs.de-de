---
title: Verwenden von Variablen mit einem .NET Framework 3.5-Ruleset
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 64d47564076e19e152e30b6ab0cb3900ce53cfa1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395153"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a>Verwenden von Variablen mit einem .NET Framework 3.5-Ruleset
Dieses Beispiel veranschaulicht, wie ein Workflow erstellt wird, der mithilfe der <xref:System.Activities.Statements.Interop>-Aktivität eine in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] geschriebene benutzerdefinierte Aktivität integriert, die eine Richtlinie und Regeln verwendet. Der Workflow übergibt Daten an die benutzerdefinierte Aktivität, indem er Variablen an die von der benutzerdefinierten Aktivität verfügbar gemachten Abhängigkeitseigenschaften bindet.  
  
## <a name="sample-walkthrough"></a>Exemplarische Vorgehensweise  
  
#### <a name="to-examine-travelrulelibrary"></a>So überprüfen Sie TravelRuleLibrary  
  
1.  Öffnen Sie mit Visual Studio die Projektmappendatei "InteropWith35RuleSet.sln".  
  
2.  Öffnen Sie "TravelRuleSet.cs" im Workflow-Designer.  
  
     Es wird eine benutzerdefinierte sequenzielle Aktivität angezeigt, die eine <xref:System.Workflow.Activities.PolicyActivity> enthält.  
  
3.  Doppelklicken Sie auf die DiscountPolicy-Richtlinienaktivität, um die Regeln zu überprüfen.  
  
     Die Regeln werden im Regel-Editor angezeigt.  
  
4.  Klicken Sie mit der rechten Maustaste auf die `DiscountPolicy` , und wählen Sie die **Ansichtscode** Option aus, um den Code-beside-C#-Code für die Aktivität zu überprüfen.  
  
     Achten Sie auf die Einstellung der Abhängigkeitseigenschaft für `DiscountLevel`. Diese entspricht den Argumenten in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]. Weitere Informationen zu Argumenten finden Sie unter [Variablen und Argumente](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 Dies ist ein sequenzielles Workflowprojekt, das die <xref:System.Activities.Statements.Interop>-Aktivität für die Integration mit dem im `TravelRuleLibrary`-Projekt erstellten benutzerdefinierten Regelsatz verwendet. Variablen werden in der <xref:System.Activities.Statements.Sequence>-Aktivität auf oberster Ebene erstellt. Die <xref:System.Activities.Statements.Interop>-Aktivität wird zur Integration mit der `TravelRuleSet`-Aktivität verwendet. Die Variablen in der <xref:System.Activities.Statements.Sequence> deklarierten Variablen werden zum Binden an die Abhängigkeitseigenschaften verwendet.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "InteropWith35RuleSet.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`