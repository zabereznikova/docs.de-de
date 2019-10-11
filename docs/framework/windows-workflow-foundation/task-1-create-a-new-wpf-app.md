---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031895"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung

In dieser Aufgabe erstellen Sie eine leere Windows Presentation Foundation (WPF)-Anwendung mithilfe der Visual Studio-Vorlage WPF-Anwendung und fügen Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflowassemblys hinzu.  
  
## <a name="to-create-the-wpf-application-project"></a>So erstellen Sie das WPF-Anwendungsprojekt

1. Öffnen Sie Visual Studio, zeigen Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt**.

2. Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **installierte Vorlagen** auf der linken Seite des Fensters entweder  **C# Visual** oder **Visual Basic** aus. Wenn die gewünschte Sprache nicht angezeigt wird, suchen Sie unter **andere Sprachen**.

3. Wählen Sie im Bereich **installierte Vorlagen** die Option **Windows** aus.

4. Vergewissern Sie sich im oberen Bereich, dass (der Standardwert) **.NET Framework 4** im Dropdown-Listenfeld ausgewählt wurde, und wählen Sie dann **WPF-Anwendung**aus.

5. Legen Sie den Namen des Projekts im unteren Bereich des Fensters auf **HostingApplication** fest.

6. Legen Sie den Projektmappennamen auf **rehostingder Designer**fest.

7. Klicken Sie auf **OK** , um das Anwendungsprojekt zu erstellen. Visual Studio erstellt eine einfache WPF-Benutzeroberfläche für Ihre Anwendung und enthält die entsprechenden XAML-und Code Behind-Dateien.

8. Fügen Sie Verweise auf **Workflow Model** -Assemblys hinzu. Klicken Sie hierzu in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **HostingApplication** , und wählen Sie **Verweis hinzufügen**aus.

9. Klicken Sie im Dialogfeld **Verweis hinzufügen** auf die Registerkarte **.net** , halten Sie die STRG-Taste gedrückt, wählen Sie die folgenden Assemblys aus, und klicken Sie dann auf **OK**:

    - System.Activities
    - System.Activities.Presentation
    - System.Activities.Core.Presentation

10. Weitere Informationen finden Sie unter [task 2: Hosten Sie den Workflow-Designer @ no__t-0, um zu erfahren, wie Sie den Workflow Designer-Entwurfs Bereich hosten.

## <a name="see-also"></a>Siehe auch

- [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)
- [aufgabe 2: Hosten des Workflow-Designer @ no__t-0
