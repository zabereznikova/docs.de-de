---
title: 'Gewusst wie: Erstellen einer benutzerdefinierten Aktivitätsvorlage'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: b455f8a763859d31405380e25cd7516856e8da2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-custom-activity-template"></a>Gewusst wie: Erstellen einer benutzerdefinierten Aktivitätsvorlage
Benutzerdefinierte Aktivitätsvorlagen werden verwendet, um die Konfiguration von Aktivitäten, einschließlich benutzerdefinierter zusammengesetzter Aktivitäten, anzupassen. Dadurch müssen Benutzer die Aktivitäten nicht einzeln erstellen und alle zugehörigen Eigenschaften und anderen Einstellungen manuell konfigurieren. Diese benutzerdefinierten Vorlagen können in zur Verfügung gestellt werden die **Toolbox** auf die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] oder in einem neu gehosteten Designer, von dem Benutzer auf können sie die vorkonfigurierte Entwurfsoberfläche ziehen. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] im Lieferumfang von gute Beispiele für solche Vorlagen: die [SendAndReceiveReply-Vorlagendesigner](/visualstudio/workflow-designer/sendandreceivereply-template-designer) und [ReceiveAndSendReply-Vorlagendesigner](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in die [Messaging-Aktivitätsdesigner](/visualstudio/workflow-designer/messaging-activity-designers) Kategorie.  
  
 Das erste Verfahren in diesem Thema wird beschrieben, wie zum Erstellen einer benutzerdefinierten Aktivitätsvorlage für eine **Verzögerung** Aktivität und das zweite Verfahren beschreibt kurz, wie in verfügbar zu machen eine [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] um sicherzustellen, dass die benutzerdefinierte Vorlage aus.  
  
 Benutzerdefinierte Aktivitätsvorlagen müssen <xref:System.Activities.Presentation.IActivityTemplateFactory> implementieren. Die Schnittstelle verfügt über eine einzelne <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>-Methode, mit der Sie die in der Vorlage verwendeten Aktivitätsinstanzen erstellen und konfigurieren können.  
  
### <a name="to-create-a-template-for-the-delay-activity"></a>So erstellen Sie eine Vorlage für die Delay-Aktivität  
  
1.  Starten Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  In der **Projekttypen** klicken Sie im Bereich **Workflow** entweder aus der **Visual C#-** Projekte oder **Visual Basic** Gruppierungen je nach Ihrer Bevorzugte Sprache.  
  
4.  In der **Vorlagen** klicken Sie im Bereich **Aktivitätsbibliothek**.  
  
5.  In der **Namen** geben `DelayActivityTemplate`.  
  
6.  Übernehmen Sie die Standardwerte in den **Speicherort** und **Projektmappenname** Textfelder, und klicken Sie dann auf **OK**.  
  
7.  Mit der rechten Maustaste in das Verzeichnis "Verweise" des Projekts "delayactivitytemplate" im **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen** So öffnen die **Verweis hinzufügen** (Dialogfeld).  
  
8.  Wechseln Sie zu der **.NET** Registerkarte, und wählen Sie **PresentationFramework** aus der **Komponentenname** Spalte auf der linken Seite und auf **OK** einen Verweis hinzu um die Datei "PresentationFramework.dll".  
  
9. Wiederholen Sie dieses Verfahren, um Verweise auf die Dateien "System.Activities.Presentation.dll" und "WindowsBase.dll" hinzuzufügen.  
  
10. Mit der rechten Maustaste des Projekts "delayactivitytemplate" im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **neues Element** So öffnen die **neues Element hinzufügen**(Dialogfeld).  
  
11. Wählen Sie die **Klasse** Vorlage, nennen Sie sie "mydelaytemplate", und klicken Sie dann auf **OK**.  
  
12. Öffnen Sie die Datei "MyDelayTemplate.cs", und fügen Sie die folgenden Anweisungen hinzu.  
  
    ```  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
    ```  
  
13. Implementieren Sie <xref:System.Activities.Presentation.IActivityTemplateFactory> mit der `MyDelayActivity`-Klasse mit dem folgenden Code. Damit wird die Verzögerung mit einer Dauer von 10 Sekunden konfiguriert.  
  
    ```  
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
  
14. Wählen Sie **Projektmappe** aus der **erstellen** -Menü, um die Datei "DelayActivityTemplate.dll" zu generieren.  
  
### <a name="to-make-the-template-available-in-a-workflow-designer"></a>So machen Sie die Vorlage in einem Workflow-Designer verfügbar  
  
1.  Mit der rechten Maustaste in die Projektmappe "delayactivitytemplate" im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **neues Projekt** So öffnen die **neues Projekt hinzufügen** (Dialogfeld).  
  
2.  Wählen Sie die **Workflowkonsolenanwendung** Vorlage, nennen Sie sie `CustomActivityTemplateApp`, und klicken Sie dann auf **OK**.  
  
3.  Mit der rechten Maustaste in das Verzeichnis "Verweise" des CustomActivityTemplateApp-Projekts in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen** So öffnen die **Verweis hinzufügen** Dialogfeld Box.  
  
4.  Wechseln Sie zu der **Projekte** Registerkarte, und wählen Sie **"delayactivitytemplate"** aus der **Projektname** Spalte auf der linken Seite und auf **OK** Hinzufügen einer einen Verweis auf die Datei "DelayActivityTemplate.dll", die Sie im ersten Verfahren erstellt haben.  
  
5.  Mit der rechten Maustaste des Projekts "customactivitytemplateapp" im **Projektmappen-Explorer** , und wählen Sie **erstellen** zum Kompilieren der Anwendung.  
  
6.  Mit der rechten Maustaste des Projekts "customactivitytemplateapp" im **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.  
  
7.  Wählen Sie **Starten ohne Debugging** aus der **Debuggen** ein und drücken Sie eine beliebige Taste, um den Vorgang fortzusetzen Aufforderung aus dem Fenster "cmd.exe".  
  
8.  Öffnen Sie die Datei "Workflow1.xaml", und öffnen Sie die **Toolbox**.  
  
9. Suchen Sie die **MyDelayActivity** Vorlage in der **"delayactivitytemplate"** Kategorie. Ziehen Sie sie auf die Entwurfsoberfläche. Vergewissern Sie sich der **Eigenschaften** Fenster, die die `Duration` -Eigenschaft auf 10 Sekunden festgelegt wurde.  
  
## <a name="example"></a>Beispiel  
 Die Datei "MyDelayActivity.cs" sollte den folgenden Code enthalten.  
  
```  
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
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
 [Anpassen des Workflowentwurfsvorgangs](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
