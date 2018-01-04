---
title: "Erstellen von Workflowaktivitäten mit der Aktivitätsklasse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52d29f9cbed65932b3f9e97f0e9275861953b5d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Erstellen von Workflowaktivitäten mit der Aktivitätsklasse
Die einfachste Möglichkeit zum Erstellen eine Aktivität mit [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] besteht darin, eine Klasse erstellen, die von erben <xref:System.Activities.Activity> erstellt Funktionalität durch das Zusammenfügen von benutzerdefinierten Aktivitäten oder Aktivitäten aus der [integrierte Aktivitätsbibliothek ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). In diesem Thema wird veranschaulicht, wie eine Aktivität erstellt wird, die zwei Meldungen in die Konsole schreibt.  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>So erstellen Sie eine benutzerdefinierte Aktivität mit dem Aktivitätsdesigner  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Wählen Sie "Datei", "Neu" und "Projekt" aus. Wählen Sie **Workflow 4.0** unter **Visual C#-** in der **Projekttypen** , und wählen Sie die **v2010** Knoten. Wählen Sie **Aktivitätsbibliothek** in der **Vorlagen** Fenster. Geben Sie dem neuen Projekt den Namen "HelloActivity".  
  
3.  Öffnen Sie die neue Aktivität.  Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität von der Toolbox auf die Designeroberfläche.  
  
4.  Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität. Geben Sie `"Hello World"` (mit Anführungszeichen) in der **Text** Feld.  
  
5.  Ziehen Sie eine zweite <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität (unter die erste). Geben Sie `"Goodbye"` (mit Anführungszeichen) in der **Text** Feld.
