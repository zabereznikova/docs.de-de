---
title: "Gewusst wie: Erstellen einer benutzerdefinierten Aktivit&#228;tsvorlage | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Gewusst wie: Erstellen einer benutzerdefinierten Aktivit&#228;tsvorlage
Benutzerdefinierte Aktivitätsvorlagen werden verwendet, um die Konfiguration von Aktivitäten, einschließlich benutzerdefinierter zusammengesetzter Aktivitäten, anzupassen. Dadurch müssen Benutzer die Aktivitäten nicht einzeln erstellen und alle zugehörigen Eigenschaften und anderen Einstellungen manuell konfigurieren.Diese benutzerdefinierten Vorlagen können in der **Toolbox** im [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] oder in einem neu gehosteten Designer bereitgestellt werden, aus dem Benutzer sie auf die vorkonfigurierte Entwurfsoberfläche ziehen können.Zu [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] gehören anschauliche Beispiele für solche Vorlagen: [SendAndReceiveReply\-Vorlagendesigner](../Topic/SendAndReceiveReply%20Template%20Designer.md) und [ReceiveAndSendReply\-Vorlagendesigner](../Topic/ReceiveAndSendReply%20Template%20Designer.md) in der [Messaging\-Aktivitätsdesigner](../Topic/Messaging%20Activity%20Designers.md)\-Kategorie.  
  
 Das erste Verfahren in diesem Thema beschreibt, wie eine benutzerdefinierte Aktivitätsvorlage für eine **Delay**\-Aktivität erstellt wird, und das zweite Verfahren beschreibt kurz, wie sie in [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] verfügbar gemacht wird, um die Funktionsfähigkeit der benutzerdefinierten Vorlage zu überprüfen.  
  
 Benutzerdefinierte Aktivitätsvorlagen müssen <xref:System.Activities.Presentation.IActivityTemplateFactory> implementieren.Die Schnittstelle verfügt über eine einzelne <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>\-Methode, mit der Sie die in der Vorlage verwendeten Aktivitätsinstanzen erstellen und konfigurieren können.  
  
### So erstellen Sie eine Vorlage für die Delay\-Aktivität  
  
1.  Starten Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Wählen Sie im Bereich **Projekttypen** die Option **Workflow** für **Visual C\#**\-Projekte oder **Visual Basic**\-Gruppierungen aus, abhängig von der bevorzugten Sprache.  
  
4.  Wählen Sie im Bereich **Vorlagen** die Option **Aktivitätsbibliothek** aus.  
  
5.  Geben Sie im Feld **Name** den Wert `DelayActivityTemplate` ein.  
  
6.  Übernehmen Sie die Standardwerte in den Textfeldern **Speicherort** und **Projektmappenname**, und klicken Sie dann auf **OK**.  
  
7.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Verzeichnis "Verweise" des DelayActivityTemplate\-Projekts, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.  
  
8.  Wechseln Sie zur Registerkarte **.NET**, und wählen Sie **PresentationFramework** in der Spalte **Komponentenname** auf der linken Seite aus, und klicken Sie auf **OK**, um einen Verweis auf die Datei "PresentationFramework.dll" hinzuzufügen.  
  
9. Wiederholen Sie dieses Verfahren, um Verweise auf die Dateien "System.Activities.Presentation.dll" und "WindowsBase.dll" hinzuzufügen.  
  
10. Klicken Sie mit der rechten Maustaste auf das Projekt "DelayActivityTemplate" im **Projektmappen\-Explorer**, und wählen Sie **Hinzufügen** und dann **Neues Element** aus, um das Dialogfeld **Neues Element hinzufügen** zu öffnen.  
  
11. Wählen Sie die Vorlage **Klasse** aus, nennen Sie sie "MyDelayTemplate", und klicken Sie dann auf **OK**.  
  
12. Öffnen Sie die Datei "MyDelayTemplate.cs", und fügen Sie die folgenden Anweisungen hinzu.  
  
    ```  
  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
  
    ```  
  
13. Implementieren Sie <xref:System.Activities.Presentation.IActivityTemplateFactory> mit der `MyDelayActivity`\-Klasse mit dem folgenden Code.Damit wird die Verzögerung mit einer Dauer von 10 Sekunden konfiguriert.  
  
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
  
14. Wählen Sie **Projektmappe erstellen** im Menü **Erstellen** aus, um die Datei "DelayActivityTemplate.dll" zu generieren.  
  
### So machen Sie die Vorlage in einem Workflow\-Designer verfügbar  
  
1.  Klicken Sie mit der rechten Maustaste auf die Projektmappe "DelayActivityTemplate" im **Projektmappen\-Explorer**, und wählen Sie **Hinzufügen** und dann **Neues Projekt** aus, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.  
  
2.  Wählen Sie die Vorlage **Konsolenanwendung für Workflows** aus, nennen Sie sie `CustomActivityTemplateApp`, und klicken Sie dann auf **OK**.  
  
3.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Verzeichnis "Verweise" des CustomActivityTemplateApp\-Projekts, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.  
  
4.  Wechseln Sie zur Registerkarte **Projekte**, wählen Sie **DelayActivityTemplate** in der Spalte **Projektname** auf der linken Seite aus, und klicken Sie auf **OK**, um einen Verweis auf die Datei "DelayActivityTemplate.dll" hinzuzufügen, die Sie im ersten Verfahren erstellt haben.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projekt "CustomActivityTemplateApp" im **Projektmappen\-Explorer**, und wählen Sie **Erstellen** aus, um die Anwendung zu kompilieren.  
  
6.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt "CustomActivityTemplateApp", und wählen Sie **Als Startprojekt festlegen** aus.  
  
7.  Wählen Sie **Starten ohne Debugging** im Menü **Debuggen** aus, und drücken Sie eine beliebige Taste, um fortzufahren, wenn Sie im Fenster "cmd.exe" dazu aufgefordert werden.  
  
8.  Öffnen Sie die Datei "Workflow1.xaml", und öffnen Sie die **Toolbox**.  
  
9. Suchen Sie die Vorlage **MyDelayActivity** in der Kategorie **DelayActivityTemplate**.Ziehen Sie sie auf die Entwurfsoberfläche.Bestätigen Sie im Fenster **Eigenschaften**, dass die `Duration`\-Eigenschaft auf 10 Sekunden festgelegt wurde.  
  
## Beispiel  
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
  
## Siehe auch  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>   
 [Anpassen des Workflowentwurfsvorgangs](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md)