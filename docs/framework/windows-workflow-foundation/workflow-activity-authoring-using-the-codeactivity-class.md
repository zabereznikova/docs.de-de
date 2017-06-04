---
title: "Erstellen von Workflowaktivit&#228;ten mit der CodeActivity-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Erstellen von Workflowaktivit&#228;ten mit der CodeActivity-Klasse
Aktivitäten, die durch das Erben von <xref:System.Activities.CodeActivity> erstellt werden, können das grundlegende imperative Verhalten implementieren, indem sie die <xref:System.Activities.CodeActivity.Execute%2A>\-Methode überschreiben.  
  
## Verwenden von CodeActivityContext  
 Innerhalb der <xref:System.Activities.CodeActivity.Execute%2A>\-Methode kann mithilfe von Membern des `context`\-Parameters vom Typ <xref:System.Activities.CodeActivityContext> auf Funktionen des Workflows zugegriffen werden.Über <xref:System.Activities.CodeActivityContext> sind unter anderem folgende Funktionen verfügbar:  
  
-   Abrufen und Festlegen der Werte von Variablen und Argumenten  
  
-   Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A>  
  
-   Zugreifen auf die Ausführungseigenschaften der Aktivität mithilfe von <xref:System.Activities.CodeActivityContext.GetProperty%2A>  
  
#### So erstellen Sie eine benutzerdefinierte Aktivität, die von CodeActivity erbt  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **Neu** und dann **Projekt** aus.Wählen Sie unter **Visual C\#** im Fenster **Projekttypen** die Option **Workflow 4.0** und danach den Knoten **v2010** aus.Wählen Sie im Fenster **Vorlagen** die Option **Aktivitätsbibliothek** aus.Geben Sie dem neuen Projekt den Namen "HelloActivity".  
  
3.  Klicken Sie mit der rechten Maustaste im HelloActivity\-Projekt auf "Activity1.xaml", und wählen Sie **Löschen** aus.  
  
4.  Klicken Sie mit der rechten Maustaste auf das HelloActivity\-Projekt, und wählen Sie **Hinzufügen** und danach **Klasse** aus.Nennen Sie die neue Klasse "HelloActivity.cs".  
  
5.  Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`\-Direktiven hinzu.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  Legen Sie fest, dass die neue Klasse von <xref:System.Activities.CodeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.CodeActivity.Execute%2A>\-Methode hinzufügen.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  Verwenden Sie die <xref:System.Activities.CodeActivityContext>\-Instanz, um einen Nachverfolgungsdatensatz zu erstellen.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
  
    ```