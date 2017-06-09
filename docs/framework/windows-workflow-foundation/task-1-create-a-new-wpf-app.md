---
title: "Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung
In dieser Aufgabe erstellen Sie eine leere [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]\-Anwendung mithilfe der WPF\-Anwendungsvorlage von Visual Studio und fügen Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]\-Workflowassemblys hinzu.  
  
### So erstellen Sie das WPF\-Anwendungsprojekt  
  
1.  Öffnen Sie [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **Installierte Vorlagen** auf der linken Seite entweder **Visual C\#** oder **Visual Basic** aus.Wenn die gewünschte Sprache nicht in der Auswahl angezeigt wird, suchen Sie unter **Andere Sprachen**.  
  
3.  Wählen Sie im Bereich **Installierte Vorlagen** die Option **Windows** aus.  
  
4.  Vergewissern Sie sich, dass im oberen Bereich im Dropdown\-Listenfeld **.NET Framework 4** \(der Standardwert\) ausgewählt ist, und wählen Sie dann **WPF\-Anwendung** aus.  
  
5.  Legen Sie den Namen des Projekts am unteren Rand des Fensters auf **HostingApplication** fest.  
  
6.  Legen Sie als Name der Projektmappe **RehostingTheDesigner** fest.  
  
7.  Klicken Sie auf **OK**, um das Anwendungsprojekt zu erstellen.[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] erstellt eine WPF\-Basisbenutzeroberfläche für Ihre Anwendung und fügt die entsprechende XAML sowie Code\-Behind\-Dateien hinzu.  
  
8.  Fügen Sie Verweise auf **WorkflowModel**\-Assemblys hinzu.Klicken Sie dazu im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **HostingApplication**, und wählen Sie **Verweis hinzufügen** aus.  
  
9. Klicken Sie im Dialogfeld **Verweis hinzufügen** auf die Registerkarte **.NET**, wählen Sie bei gedrückt gehaltener STRG\-TASTE die folgenden Assemblys aus, und klicken Sie dann auf **OK**.  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Klicken Sie auf **OK**.  
  
11. Informationen zum Hosten des Entwurfszeichnungsbereichs des Workflow\-Designers finden Sie unter [Aufgabe 2: Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md).  
  
## Siehe auch  
 [Erneutes Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Aufgabe 2: Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)