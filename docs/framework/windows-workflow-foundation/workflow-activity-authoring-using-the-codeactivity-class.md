---
title: Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 714e0971a006db20d002b0f3a486533b1357fba7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293818"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse

Aktivitäten, die durch das Erben von <xref:System.Activities.CodeActivity> erstellt werden, können das grundlegende imperative Verhalten implementieren, indem sie die <xref:System.Activities.CodeActivity.Execute%2A>-Methode überschreiben.

## <a name="using-codeactivitycontext"></a>Verwenden von CodeActivityContext

 Innerhalb der <xref:System.Activities.CodeActivity.Execute%2A>-Methode kann mithilfe von Membern des `context`-Parameters vom Typ <xref:System.Activities.CodeActivityContext> auf Funktionen des Workflows zugegriffen werden. Über <xref:System.Activities.CodeActivityContext> sind unter anderem folgende Funktionen verfügbar:

- Abrufen und Festlegen der Werte von Variablen und Argumenten

- Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A>

- Zugreifen auf die Ausführungseigenschaften der Aktivität mithilfe von <xref:System.Activities.CodeActivityContext.GetProperty%2A>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>So erstellen Sie eine benutzerdefinierte Aktivität, die von CodeActivity erbt

1. Öffnen Sie Visual Studio 2010.

2. Wählen Sie **Datei**, **neu** und dann **Projekt** aus. Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus. Wählen Sie im Fenster **Vorlagen** die Option **Aktivitäts Bibliothek** aus. Geben Sie dem neuen Projekt den Namen "HelloActivity".

3. Klicken Sie im HelloActivity-Projekt mit der rechten Maustaste auf Activity1. XAML, und wählen Sie **Löschen** aus.

4. Klicken Sie mit der rechten Maustaste auf das Projekt HelloActivity, und wählen Sie **Hinzufügen** und dann **Klasse** aus. Nennen Sie die neue Klasse HelloActivity.cs.

5. Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`-Direktiven hinzu.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Legen Sie fest, dass die neue Klasse von <xref:System.Activities.CodeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.CodeActivity.Execute%2A>-Methode hinzufügen.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Verwenden Sie die <xref:System.Activities.CodeActivityContext>-Instanz, um einen Nachverfolgungsdatensatz zu erstellen.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
