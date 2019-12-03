---
title: 'Gewusst wie: Erstellen einer benutzerdefinierten Aktivitätsvorlage'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: f910d1367c941dbc319421d402cae8f4194872e5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715256"
---
# <a name="how-to-create-a-custom-activity-template"></a>Gewusst wie: Erstellen einer benutzerdefinierten Aktivitätsvorlage

Benutzerdefinierte Aktivitätsvorlagen werden verwendet, um die Konfiguration von Aktivitäten, einschließlich benutzerdefinierter zusammengesetzter Aktivitäten, anzupassen. Dadurch müssen Benutzer die Aktivitäten nicht einzeln erstellen und alle zugehörigen Eigenschaften und anderen Einstellungen manuell konfigurieren. Diese benutzerdefinierten Vorlagen können in der **Toolbox** auf dem Windows-Workflow-Designer oder einem neu gehosteten Designer verfügbar gemacht werden, über den Benutzer Sie auf die vorkonfigurierte Entwurfs Oberfläche ziehen können. Workflow-Designer enthält gute Beispiele für solche Vorlagen: den [sendandreceivereply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) -Vorlagen Designer und den [receiveandsendreply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) -Vorlagen Designer in der Kategorie der [Messaging-Aktivitäts Designer](/visualstudio/workflow-designer/messaging-activity-designers) .

 Das erste Verfahren in diesem Thema beschreibt, wie eine benutzerdefinierte Aktivitäts Vorlage für eine **Verzögerungs** Aktivität erstellt wird, und das zweite Verfahren beschreibt kurz, wie Sie in einem Workflow-Designer verfügbar gemacht wird, um zu überprüfen, ob die benutzerdefinierte Vorlage funktioniert.

 Benutzerdefinierte Aktivitätsvorlagen müssen <xref:System.Activities.Presentation.IActivityTemplateFactory> implementieren. Die Schnittstelle verfügt über eine einzelne <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>-Methode, mit der Sie die in der Vorlage verwendeten Aktivitätsinstanzen erstellen und konfigurieren können.

## <a name="to-create-a-template-for-the-delay-activity"></a>So erstellen Sie eine Vorlage für die Delay-Aktivität

1. Starten Sie Visual Studio 2010.

2. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Wählen Sie im Bereich **Projekttypen** die Option **Workflow** aus den **visuellen C#**  Projekten oder **Visual Basic** Gruppierungen abhängig von ihrer bevorzugte Sprache aus.

4. Wählen Sie im Bereich **Vorlagen** die Option **Aktivitäts Bibliothek**aus.

5. Geben Sie im Feld **Name** `DelayActivityTemplate`ein.

6. Akzeptieren Sie die Standardwerte in den Textfeldern **Speicherort** und Projektmappenname, und klicken Sie dann auf **OK**.

7. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis Verweise, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.

8. Wechseln Sie zur Registerkarte **.net** , wählen Sie in der Spalte **Komponenten Name** auf der linken Seite **presentationframework** aus, und klicken Sie auf **OK** , um einen Verweis auf die Datei "presentationframework. dll" hinzuzufügen.

9. Wiederholen Sie dieses Verfahren, um Verweise auf die Dateien "System.Activities.Presentation.dll" und "WindowsBase.dll" hinzuzufügen.

10. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Delta activitytemplate, und wählen Sie **Hinzufügen** und dann **Neues Element** aus, um das Dialogfeld **Neues Element hinzufügen** zu öffnen.

11. Wählen Sie die **Klassen** Vorlage aus, benennen Sie Sie mydelta-Template, und klicken Sie dann auf **OK**.

12. Öffnen Sie die Datei "MyDelayTemplate.cs", und fügen Sie die folgenden Anweisungen hinzu.

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. Implementieren Sie <xref:System.Activities.Presentation.IActivityTemplateFactory> mit der `MyDelayActivity`-Klasse mit dem folgenden Code. Damit wird die Verzögerung mit einer Dauer von 10 Sekunden konfiguriert.

    ```csharp
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus, um die Datei "Delta activitytemplate. dll" zu generieren.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>So machen Sie die Vorlage in einem Workflow-Designer verfügbar

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf die Projekt Mappe Delta activitytemplate, und wählen Sie **Hinzufügen** und dann **Neues Projekt** aus, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen

2. Wählen Sie die Vorlage **Konsolenanwendung für Workflows** aus, benennen Sie Sie `CustomActivityTemplateApp`, und klicken Sie dann auf **OK**.

3. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis Verweise des Projekts customactivitytemplateapp, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.

4. Wechseln Sie zur Registerkarte **Projekte** , und wählen Sie in der Spalte **Project Name** auf der linken Seite die Option **Delta activitytemplate** aus, und klicken Sie auf **OK** , um einen Verweis auf die Datei "Delta activitytemplate. dll" hinzuzufügen, die Sie im ersten Verfahren erstellt haben.

5. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt customactivitytemplateapp, und wählen Sie **Erstellen** , um die Anwendung zu kompilieren.

6. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt customactivitytemplateapp, und wählen Sie **als Startprojekt festlegen**aus.

7. Wählen Sie im Menü **Debuggen** die Option **Starten ohne Debugging** aus, und drücken Sie eine beliebige Taste, um fortzufahren, wenn Sie im Fenster "cmd

8. Öffnen Sie die Datei Workflow1. XAML, und öffnen Sie die **Toolbox**.

9. Suchen Sie in der Kategorie " **Delta activitytemplate** " die Vorlage **mydelta-Activity** . Ziehen Sie sie auf die Entwurfsoberfläche. Vergewissern Sie sich im **Eigenschaften** Fenster, dass die `Duration`-Eigenschaft auf 10 Sekunden festgelegt wurde.

## <a name="example"></a>Beispiel
 Die Datei "MyDelayActivity.cs" sollte den folgenden Code enthalten.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [Anpassen des Workflowentwurfsvorgangs](customizing-the-workflow-design-experience.md)
