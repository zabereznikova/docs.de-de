---
title: "Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 675997cdf44992d4eaad5cb4595fe28d3de436d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse
Aktivitäten, die durch das Erben von <xref:System.Activities.CodeActivity> erstellt werden, können das grundlegende imperative Verhalten implementieren, indem sie die <xref:System.Activities.CodeActivity.Execute%2A>-Methode überschreiben.  
  
## <a name="using-codeactivitycontext"></a>Verwenden von CodeActivityContext  
 Innerhalb der <xref:System.Activities.CodeActivity.Execute%2A>-Methode kann mithilfe von Membern des `context`-Parameters vom Typ <xref:System.Activities.CodeActivityContext> auf Funktionen des Workflows zugegriffen werden. Über <xref:System.Activities.CodeActivityContext> sind unter anderem folgende Funktionen verfügbar:  
  
-   Abrufen und Festlegen der Werte von Variablen und Argumenten  
  
-   Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A>  
  
-   Zugreifen auf die Ausführungseigenschaften der Aktivität mithilfe von <xref:System.Activities.CodeActivityContext.GetProperty%2A>  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>So erstellen Sie eine benutzerdefinierte Aktivität, die von CodeActivity erbt  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **neue**, und klicken Sie dann **Projekt**. Wählen Sie **Workflow 4.0** unter **Visual C#-** in der **Projekttypen** , und wählen Sie die **v2010** Knoten. Wählen Sie **Aktivitätsbibliothek** in der **Vorlagen** Fenster. Geben Sie dem neuen Projekt den Namen "HelloActivity".  
  
3.  Klicken Sie auf "Activity1.xaml", in das HelloActivity-Projekt, und wählen Sie **löschen**.  
  
4.  Maustaste auf das HelloActivity-Projekt, und wählen Sie **hinzufügen** , und klicken Sie dann **Klasse**. Nennen Sie die neue Klasse HelloActivity.cs.  
  
5.  Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`-Direktiven hinzu.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  Legen Sie fest, dass die neue Klasse von <xref:System.Activities.CodeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.CodeActivity.Execute%2A>-Methode hinzufügen.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  Verwenden Sie die <xref:System.Activities.CodeActivityContext>-Instanz, um einen Nachverfolgungsdatensatz zu erstellen.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
    ```
