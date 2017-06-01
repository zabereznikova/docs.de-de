---
title: "Erstellen von Workflowaktivit&#228;ten mit der Aktivit&#228;tsklasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Erstellen von Workflowaktivit&#228;ten mit der Aktivit&#228;tsklasse
Die einfachste Möglichkeit, eine Aktivität mit [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] zu erstellen, besteht darin, eine Klasse zu erstellen, die vom <xref:System.Activities.Activity>\-Objekt erbt. Dieses erzeugt Funktionalität, indem benutzerdefinierte Aktivitäten oder Aktivitäten aus der [Integrierte Aktivitätsbibliothek](../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md) zusammengesetzt werden.In diesem Thema wird veranschaulicht, wie eine Aktivität erstellt wird, die zwei Meldungen in die Konsole schreibt.  
  
### So erstellen Sie eine benutzerdefinierte Aktivität mit dem Aktivitätsdesigner  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Wählen Sie "Datei", "Neu" und "Projekt" aus.Wählen Sie unter **Visual C\#** im Fenster **Projekttypen** die Option **Workflow 4.0** und danach den Knoten **v2010** aus.Wählen Sie im Fenster **Vorlagen** die Option **Aktivitätsbibliothek** aus.Geben Sie dem neuen Projekt den Namen "HelloActivity".  
  
3.  Öffnen Sie die neue Aktivität.Ziehen Sie eine <xref:System.Activities.Statements.Sequence>\-Aktivität von der Toolbox auf die Designeroberfläche.  
  
4.  Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität in die <xref:System.Activities.Statements.Sequence>\-Aktivität.Geben Sie `"Hello World"` \(mit Anführungszeichen\) in das Feld **Text** ein.  
  
5.  Ziehen Sie eine zweite <xref:System.Activities.Statements.WriteLine>\-Aktivität in die <xref:System.Activities.Statements.Sequence>\-Aktivität \(unter die erste\).Geben Sie `"Goodbye"` \(mit Anführungszeichen\) in das Feld **Text** ein.