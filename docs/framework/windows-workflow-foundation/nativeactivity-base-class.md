---
title: "NativeActivity-Basisklasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# NativeActivity-Basisklasse
<xref:System.Activities.NativeActivity> ist eine abstrakte Klasse mit einem geschützten Konstruktor.Wie <xref:System.Activities.CodeActivity> wird auch <xref:System.Activities.NativeActivity> zum Schreiben von imperativem Verhalten durch die Implementierung einer <xref:System.Activities.NativeActivity.Execute%2A>\-Methode verwendet.Im Gegensatz zu <xref:System.Activities.CodeActivity> verfügt <xref:System.Activities.NativeActivity> jedoch über Zugriff auf alle verfügbar gemachten Funktionen der Workflowlaufzeit durch das <xref:System.Activities.NativeActivityContext>\-Objekt, das an die <xref:System.Activities.NativeActivity.Execute%2A>\-Methode übergeben wurde.  
  
## Verwenden von NativeActivityContext  
 Innerhalb der <xref:System.Activities.NativeActivity.Execute%2A>\-Methode kann mithilfe von Membern des `context`\-Parameters des Typs <xref:System.Activities.NativeActivityContext> auf Funktionen des Workflows zugegriffen werden.Über <xref:System.Activities.NativeActivityContext> sind unter anderem folgende Funktionen verfügbar:  
  
-   Abrufen und Festlegen von Argumenten und Variablen  
  
-   Planen von untergeordneten Aktivitäten mit <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>  
  
-   Abbrechen der Ausführung von Aktivitäten mit <xref:System.Activities.NativeActivityContext.Abort%2A>.  
  
-   Abbrechen der Ausführung untergeordneter Elemente mit <xref:System.Activities.NativeActivityContext.CancelChild%2A> und <xref:System.Activities.NativeActivityContext.CancelChildren%2A>  
  
-   Zugreifen auf Aktivitätslesezeichen mit Methoden wie <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> und <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>  
  
-   Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A>  
  
-   Zugeifen auf die Ausführungseigenschaften und Werteigenschaften der Aktivität mit <xref:System.Activities.CodeActivityContext.GetProperty%2A> und <xref:System.Activities.NativeActivityContext.GetValue%2A>  
  
-   Planen von Aktivitätsaktionen und Funktionen mit <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> und <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>  
  
#### So erstellen Sie eine benutzerdefinierte Aktivität, die von NativeActivity erbt  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **Neu** und dann **Projekt** aus.Wählen Sie unter **Visual C\#** im Fenster **Projekttypen** die Option **Workflow 4.0** und danach den Knoten **v2010** aus.Wählen Sie im Fenster **Vorlagen** die Option **Aktivitätsbibliothek** aus.Geben Sie dem neuen Projekt den Namen "HelloActivity".  
  
3.  Klicken Sie mit der rechten Maustaste im HelloActivity\-Projekt auf "Activity1.xaml", und wählen Sie **Löschen** aus.  
  
4.  Klicken Sie mit der rechten Maustaste auf das HelloActivity\-Projekt, und wählen Sie **Hinzufügen** und danach **Klasse** aus.Nennen Sie die neue Klasse "HelloActivity.cs".  
  
5.  Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`\-Direktiven hinzu.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  Legen Sie fest, dass die neue Klasse von <xref:System.Activities.NativeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.  
  
    ```csharp  
    class HelloActivity : NativeActivity  
    ```  
  
7.  Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.NativeActivity.Execute%2A>\-Methode hinzufügen.  
  
    ```csharp  
    protected override void Execute(NativeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  Überschreiben Sie die <xref:System.Activities.NativeActivity.CacheMetadata%2A>\-Methode, und rufen Sie die entsprechende Add\-Methode auf, um Informationen zu den Variablen, Argumenten, untergeordneten Elementen und Delegaten der benutzerdefinierten Aktivität für die Workflowlaufzeit bereitzustellen.Weitere Informationen finden Sie unter der <xref:System.Activities.NativeActivityMetadata>\-Klasse.  
  
9. Verwenden Sie das <xref:System.Activities.NativeActivityContext>\-Objekt, um ein Lesezeichen zu planen.Nähere Informationen zum Erstellen, Planen und Fortsetzen eines Lesezeichens finden Sie unter <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>.  
  
    ```  
    protected override void Execute(NativeActivityContext context)  
        {  
            // Create a Bookmark and wait for it to be resumed.  
            context.CreateBookmark(BookmarkName.Get(context),   
                new BookmarkCallback(OnResumeBookmark));  
        }  
  
    ```