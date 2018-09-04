---
title: Muster der automatischen Bestätigung
ms.date: 03/30/2017
ms.assetid: 668aec65-78d3-4636-9c7b-deed643a18f9
ms.openlocfilehash: a032c05743b64fe58b0b187328b5216080ba6e19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552269"
---
# <a name="auto-confirm-pattern"></a>Muster der automatischen Bestätigung
Dieses Beispiel besteht aus drei Szenarien, die zur Veranschaulichung eine benutzerdefinierte `AutoConfirmScope`-Aktivität ausführen. Im ersten Beispiel wird die erfolgreiche Ausführung einer Sequenz von vier kompensierbaren Aktivitäten veranschaulicht, bei denen die zweite und dritte in `AutoConfirmScope` geschachtelt sind. Im zweiten Beispiel wird die gleiche Sequenz mit einer Ausnahme veranschaulicht, die nach der Ausführung der vierten <xref:System.Activities.Statements.CompensableActivity> auftritt. Das dritte Szenario zeigt die gleiche Sequenz mit einer Ausnahme, die in `AutoConfirmScope` auftritt, nachdem die zweite <xref:System.Activities.Statements.CompensableActivity> abgeschlossen wurde.  
  
 Im Beispiel wird das Muster der automatischen Bestätigung veranschaulicht, bei dem alle untergeordneten kompensierbaren Aktivitäten nach dem erfolgreichen Abschluss des Bereichs bestätigt werden. Dieses Muster definiert die Lebensdauer aller untergeordneten kompensierbaren Aktivitäten, da sie nicht mehr kompensiert oder bestätigt werden können.  
  
 Der Bereich besteht aus <xref:System.Activities.Statements.TryCatch>, wobei <xref:System.Activities.Statements.TryCatch.Try%2A> eine interne <xref:System.Activities.Statements.CompensableActivity> ist. Der vom Benutzer angegebene Text von `AutoConfirmScope` ist der Text der inneren <xref:System.Activities.Statements.CompensableActivity>. Wenn diese interne <xref:System.Activities.Statements.CompensableActivity> abgeschlossen ist, erzeugt sie <xref:System.Activities.Statements.CompensationToken> als out-Argument. `AutoConfirmScope` verwendet <xref:System.Activities.Statements.TryCatch.Finally%2A>, um zu überprüfen, ob das Token erzeugt wurde. Ist dies der Fall, wird die innere <xref:System.Activities.Statements.CompensableActivity> bestätigt. Die innere <xref:System.Activities.Statements.CompensableActivity> ruft die Standardkompensierung für kompensierbare Aktivitäten auf, die möglicherweise im Text vorhanden sind.  
  
 Das erste Szenario zeigt die erfolgreiche Ausführung des Workflows und veranschaulicht, dass die zweite und dritte kompensierbare Aktivität bereits bestätigt sind, wenn der Workflow abgeschlossen wird, und die erste und vierte werden bestätigt. Dies erzeugt die Bestätigungsreihenfolge drei, zwei, vier und eins.  
  
 Das zweite Szenario zeigt eine Ausnahme, nachdem die vier kompensierbaren Aktivitäten abgeschlossen wurden. Da die kompensierbaren Aktivitäten zwei und drei bereits bestätigt wurden, bleiben sie unbeeinflusst, aber eins und vier werden kompensiert. Dies erzeugt die Bestätigung von drei und zwei und die Kompensierung von vier und eins.  
  
 Das abschließende Szenario zeigt die fehlgeschlagene Ausführung von `AutoConfirmScope`. In diesem Szenario tritt eine Ausnahme nach Abschluss der zweiten <xref:System.Activities.Statements.CompensableActivity> auf. Da die dritte und vierte kompensierbare Aktivität nicht ausgeführt wurden, bleiben sie unbeeinflusst. Da der Bereich nicht erfolgreich abgeschlossen wurde, wird die zweite <xref:System.Activities.Statements.CompensableActivity> nicht bestätigt. Dies erzeugt die Kompensierungsreihenfolge zwei dann eins.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "AutoConfirmSample.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Compensation\AutoConfirm`