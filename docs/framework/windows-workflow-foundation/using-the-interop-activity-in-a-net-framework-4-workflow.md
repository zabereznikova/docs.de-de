---
title: "Verwenden der Interop-Aktivit&#228;t in einem .NET Framework 4-Workflow | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Verwenden der Interop-Aktivit&#228;t in einem .NET Framework 4-Workflow
Aktivitäten, die mit erstellt [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] oder [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] kann verwendet werden, eine [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow mithilfe der <xref:System.Activities.Statements.Interop> Aktivität. Dieses Thema enthält eine Übersicht über die Verwendung der <xref:System.Activities.Statements.Interop> Aktivität.  
  
> [!NOTE]
>  Die <xref:System.Activities.Statements.Interop> Aktivität wird nicht in der Toolbox des Workflow-Designers angezeigt, es sei denn, der Workflow-Projekt die **Zielframework** eingestellt **.Net Framework 4** oder höher.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>Verwenden der Interop-Aktivität in Workflows von .NET Framework 4.5  
 In diesem Thema wird eine [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivitätsbibliothek erstellt, die eine `DiscountCalculator`-Aktivität enthält. Die `DiscountCalculator` berechnet einen Rabatt auf Grundlage einer und besteht aus einem <xref:System.Workflow.Activities.SequenceActivity> enthält eine <xref:System.Workflow.Activities.PolicyActivity>.  
  
> [!NOTE]
>  Die [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] Aktivität erstellen, die in diesem Thema verwendet eine <xref:System.Workflow.Activities.PolicyActivity> zum Implementieren der Logik der Aktivität. Es ist nicht erforderlich, eine benutzerdefinierte [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] Aktivität oder die <xref:System.Activities.Statements.Interop> -Aktivität verwenden, um Regeln in einer [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow. Ein Beispiel für die Verwendung von Regeln in einer [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow ohne Verwendung der <xref:System.Activities.Statements.Interop> Aktivität finden Sie unter der [Richtlinienaktivität in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) Beispiel.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>So erstellen Sie das Projekt für die .NET Framework 3.5-Aktivitätsbibliothek  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] und wählen Sie **Neu** und anschließend **Projekt...** aus der **Datei** Menü.  
  
2.  Erweitern Sie die **Andere Projekttypen** Knoten in der **Installierte Vorlagen** und wählen Sie **Visual Studio-Projektmappen**.  
  
3.  Wählen Sie **leere Projektmappe** aus der **Visual Studio-Projektmappen** Liste. Typ `PolicyInteropDemo` in den **Namen** ein, und klicken Sie auf **OK**.  
  
4.  Mit der rechten Maustaste **PolicyInteropDemo** in **Projektmappen-Explorer** und wählen Sie **Hinzufügen** und anschließend **Neues Projekt...**.  
  
    > [!TIP]
    >  Wenn die **Projektmappen-Explorer** Fenster ist nicht sichtbar ist, wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.  
  
5.  In der **Installierte Vorlagen** Liste **Visual C#-** und **Workflows**. Wählen Sie **.NET Framework 3.5** aus der Dropdown-Liste von .NET Framework Version, und wählen Sie dann **Workflow Activity Library** aus der **Vorlagen** Liste.  
  
6.  Typ `PolicyActivityLibrary` in den **Namen** ein, und klicken Sie auf **OK**.  
  
7.  Mit der rechten Maustaste **Activity1.cs** in **Projektmappen-Explorer** und wählen Sie **Löschen**. Klicken Sie zur Bestätigung auf **OK** .  
  
#### <a name="to-create-the-discountcalculator-activity"></a>So erstellen Sie die DiscountCalculator-Aktivität  
  
1.  Mit der rechten Maustaste **PolicyActivityLibrary** in **Projektmappen-Explorer** und wählen Sie **Hinzufügen** und anschließend **Aktivität**.  
  
2.  Wählen Sie **Aktivität (mit getrenntem Code)** aus der **Visual C#-Elemente** Liste. Typ `DiscountCalculator` in den **Namen** ein, und klicken Sie auf **OK**.  
  
3.  Mit der rechten Maustaste **DiscountCalculator.xoml** in **Projektmappen-Explorer** und wählen Sie **Anzeigecode**.  
  
4.  Fügen Sie der `DiscountCalculator`-Klasse die folgenden drei Eigenschaften hinzu:  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  Mit der rechten Maustaste **DiscountCalculator.xoml** in **Projektmappen-Explorer** und wählen Sie **Ansicht-Designer**.  
  
6.  Ziehen Sie eine **Richtlinie** Aktivität aus der **Windows Workflow v3. 0** Abschnitt der **Toolbox** und legen Sie sie in der **DiscountCalculator** Aktivität.  
  
    > [!TIP]
    >  Wenn die **Toolbox** Fenster ist nicht sichtbar ist, wählen **Toolbox** aus der **Ansicht** Menü.  
  
#### <a name="to-configure-the-rules"></a>So konfigurieren Sie die Regeln  
  
1.  Klicken Sie auf die neu hinzugefügte **Richtlinie** Aktivität, um diese auszuwählen, falls es nicht bereits ausgewählt ist.  
  
2.  Klicken Sie auf die **RuleSetReference** Eigenschaft in der **Eigenschaften** Fenster, um ihn auszuwählen, und klicken Sie auf die Schaltfläche rechts neben der Eigenschaft.  
  
    > [!TIP]
    >  Wenn die **Eigenschaften** nicht sichtbar ist, wählen Sie **Eigenschaftenfenster** aus der **Ansicht** Menü.  
  
3.  Wählen Sie **Klicken Sie auf neu...**.  
  
4.  Klicken Sie auf **Regel hinzufügen**.  
  
5.  Geben Sie den folgenden Ausdruck in der **Bedingung** Feld.  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  Geben Sie den folgenden Ausdruck in der **Then-Aktionen** Feld.  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  Klicken Sie auf **Regel hinzufügen**.  
  
8.  Geben Sie den folgenden Ausdruck in der **Bedingung** Feld.  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. Geben Sie den folgenden Ausdruck in der **Then-Aktionen** Feld.  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. Klicken Sie auf **Regel hinzufügen**.  
  
11. Geben Sie den folgenden Ausdruck in der **Bedingung** Feld.  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. Geben Sie den folgenden Ausdruck in der **Then-Aktionen** Feld.  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. Geben Sie den folgenden Ausdruck in der **Else-Aktionen** Feld.  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. Klicken Sie auf **OK** Schließen die **Regelsatz-Editor** (Dialogfeld).  
  
15. Sicherstellen, dass das neu erstellte <xref:System.Workflow.Activities.Rules.RuleSet> ausgewählt ist, der **Namen** aus, und klicken Sie auf **OK**.  
  
16. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
 Die Regeln, die der `DiscountCalculator`-Aktivität in diesem Verfahren hinzugefügt wurden, sind im folgenden Codebeispiel dargestellt.  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 Wenn der <xref:System.Workflow.Activities.PolicyActivity> ausgeführt wird, handelt es sich bei dieser drei Regeln ausgewertet, und Ändern der `Subtotal`, `DiscountPercent`, und `Total` Eigenschaftswerte der `DiscountCalculator` Aktivität, um den gewünschten Rabatt zu errechnen.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Verwenden der DiscountCalculator-Aktivität mit der Interop-Aktivität  
 Verwenden der `DiscountCalculator` Aktivität innerhalb einer [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow, der <xref:System.Activities.Statements.Interop> Aktivität verwendet wird. In diesem Abschnitt zwei Workflows erstellt – einer mithilfe von Code und einer mithilfe des Workflowdesigners, die veranschaulichen, wie die <xref:System.Activities.Statements.Interop> Aktivität mit der `DiscountCalculator` Aktivität. Für beide Workflows wird die gleiche Hostanwendung verwendet.  
  
#### <a name="to-create-the-host-application"></a>So erstellen Sie die Hostanwendung  
  
1.  Mit der rechten Maustaste **PolicyInteropDemo** in **Projektmappen-Explorer** und wählen Sie **Hinzufügen**, und klicken Sie dann **Neues Projekt...**.  
  
2.  Stellen Sie sicher, **.NET Framework 4.5** die in der Dropdownliste mit den .NET Framework-Version ausgewählt ist, und wählen Sie  **Workflowkonsolenanwendung** aus der **Visual C#-Elemente** Liste.  
  
3.  Typ `PolicyInteropHost` in den **Namen** ein, und klicken Sie auf **OK**.  
  
4.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** und wählen Sie **Eigenschaften**.  
  
5.  In der **Zielframework** Dropdown-Liste, ändern Sie die Auswahl von **.NET Framework 4 Client Profile** zu **.NET Framework 4.5**. Klicken Sie auf **Ja** zu bestätigen.  
  
6.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** und wählen Sie **Verweis hinzufügen**.  
  
7.  Wählen Sie **PolicyActivityLibrary** aus der **Projekte** Registerkarte, und klicken Sie auf **OK**.  
  
8.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** und wählen Sie **Verweis hinzufügen**.  
  
9. Wählen Sie **System.Workflow.Activities**, **System.Workflow.ComponentModel**, und klicken Sie dann **System.Workflow.ComponentModel** aus der **.NET** Registerkarte, und klicken Sie auf **OK**.  
  
10. Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** und wählen Sie **Set as StartUp Project**.  
  
11. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
### <a name="using-the-interop-activity-in-code"></a>Verwenden der Interop-Aktivität im Code  
 In diesem Beispiel wird eine Workflowdefinition erstellt, mithilfe von Code, enthält die <xref:System.Activities.Statements.Interop> Aktivität und die `DiscountCalculator` Aktivität. Dieser Workflow wird aufgerufen, mit <xref:System.Activities.WorkflowInvoker> und die Ergebnisse der Auswertung der Regel in der Konsole aus mithilfe einer <xref:System.Activities.Statements.WriteLine> Aktivität.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>So verwenden Sie die Interop-Aktivität im Code  
  
1.  Mit der rechten Maustaste **Program.cs** in **Projektmappen-Explorer** und wählen Sie **Anzeigecode**.  
  
2.  Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu.  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  Entfernen Sie den Inhalt der `Main`-Methode, und ersetzen Sie ihn durch folgenden Code.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  Erstellen Sie in der `Program`-Klasse eine neue Methode namens `CalculateDiscountUsingCodeWorkflow`, die den folgenden Code enthält.  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  Die `Subtotal`, `DiscountPercent`, und `Total` Eigenschaften der `DiscountCalculator` Aktivität als Argumente angegeben sind die <xref:System.Activities.Statements.Interop> Aktivität und an lokale Workflowvariablen in der <xref:System.Activities.Statements.Interop> Aktivität <xref:System.Activities.Statements.Interop.ActivityProperties%2A> Auflistung. `Subtotal` als hinzugefügt wird ein <xref:System.Activities.ArgumentDirection> Argument da die `Subtotal` Daten fließen in die <xref:System.Activities.Statements.Interop> Aktivität und `DiscountPercent` und `Total` als hinzugefügt werden <xref:System.Activities.ArgumentDirection> Argumente da ihren von Datenflüsse der <xref:System.Activities.Statements.Interop> Aktivität. Beachten Sie, dass die beiden <xref:System.Activities.ArgumentDirection> Argumente werden hinzugefügt, mit dem Namen `DiscountPercentOut` und `TotalOut` an, dass sie darstellen <xref:System.Activities.ArgumentDirection> Argumente. Die `DiscountCalculator` Typ wird angegeben, wie die <xref:System.Activities.Statements.Interop> Aktivität <xref:System.Activities.Statements.Interop.ActivityType%2A>.  
  
5.  Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen. Probieren Sie unterschiedliche Werte für den `Subtotal`-Wert aus, um die verschiedenen Rabattstufen zu testen, die von der `DiscountCalculator`-Aktivität bereitgestellt werden.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Verwenden der Interop-Aktivität im Workflow-Designer  
 In diesem Beispiel wird ein Workflow mithilfe des Workflow-Designers erstellt. Dieser Workflow verfügt über die gleiche Funktionalität wie im vorherigen Beispiel, außer als anstelle einer <xref:System.Activities.Statements.WriteLine> Aktivität, um die Rabattinformationen die Host-Anwendung abgerufen und die Rabattinformationen angezeigt, wenn der Workflow abgeschlossen ist. Außerdem sind die Daten nicht in lokalen Workflowvariablen enthalten. Die Argumente werden im Workflow-Designer erstellt, und die Werte werden vom Host übergeben, wenn der Workflow aufgerufen wird.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>So hosten Sie die Policy-Aktivität mithilfe eines vom Workflow-Designer erstellten Workflows  
  
1.  Mit der rechten Maustaste **Workflow1.xaml** in **Projektmappen-Explorer** und wählen Sie **Löschen**. Klicken Sie zur Bestätigung auf **OK** .  
  
2.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** und wählen Sie **Hinzufügen**, **Neues Element...**.  
  
3.  Erweitern Sie die **Visual C#-Elemente** Knoten, und wählen **Workflow**. Wählen Sie **Aktivität** aus der **Visual C#-Elemente** Liste.  
  
4.  Typ `DiscountWorkflow` in den **Namen** ein, und klicken Sie auf **Hinzufügen**.  
  
5.  Klicken Sie auf die **Argumente** Schaltfläche auf der unteren linken Seite des Workflow-Designers angezeigt der **Argumente** Bereich.  
  
6.  Klicken Sie auf **Argument erstellen**.  
  
7.  Typ `Subtotal` in den **Namen** Wählen Sie im **In** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdown-Liste und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
    > [!NOTE]
    >  Wenn **doppelte** befindet sich nicht in der **Argumenttyp** Dropdown-Liste **nach Typen suchen...**, Typ `System.Double` in die **Typname** ein, und klicken Sie auf **OK**.  
  
8.  Klicken Sie auf **Argument erstellen**.  
  
9. Typ `DiscountPercent` in den **Namen** Wählen Sie im **** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdown-Liste und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
10. Klicken Sie auf **Argument erstellen**.  
  
11. Typ `Total` in den **Namen** Wählen Sie im **** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdown-Liste und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
12. Klicken Sie auf die **Argumente** Schaltfläche unten links auf der Workflow-Designer zu schließen die **Argumente** Bereich.  
  
13. Ziehen Sie eine **Sequenz** Aktivität aus der **Kontrollfluss** Teil der **Toolbox** und legen ihn auf die Oberfläche des Workflow-Designers.  
  
14. Ziehen Sie ein **Interop** Aktivität aus der **Migration** Abschnitt der **Toolbox** und legen Sie sie in der **Sequenz** Aktivität.  
  
15. Klicken Sie auf die **Interop** Aktivität auf die **Klicken Sie auf Durchsuchen...** beschriften, **DiscountCalculator** in den **Namen** ein, und klicken Sie auf **OK**.  
  
    > [!NOTE]
    >  Wenn die <xref:System.Activities.Statements.Interop> Aktivität dem Workflow hinzugefügt wird und die `DiscountCalculator` als Typ angegeben ist seine <xref:System.Activities.Statements.Interop.ActivityType%2A>, die <xref:System.Activities.Statements.Interop> Aktivität macht drei <xref:System.Activities.ArgumentDirection> -Argumente und drei <xref:System.Activities.ArgumentDirection> Argumente, die drei öffentlichen Eigenschaften des darstellen, der `DiscountCalculator` Aktivität. Die <xref:System.Activities.ArgumentDirection> Argumente haben den gleichen Namen wie die drei öffentlichen Eigenschaften und die drei <xref:System.Activities.ArgumentDirection> -Argumente haben den gleichen Namen mit **** an den Eigenschaftennamen angefügt. In den folgenden Schritten, die in den vorherigen Schritten erstellten workflowargumente gebunden sind, um die <xref:System.Activities.Statements.Interop> Argumente der Aktivität.  
  
16. Typ `DiscountPercent` in die **VB-Ausdruck eingeben** im Feld rechts neben der **DiscountPercentOut** -Eigenschaft, und drücken Sie TAB.  
  
17. Typ `Subtotal` in die **VB-Ausdruck eingeben** im Feld rechts neben der **Subtotal** -Eigenschaft, und drücken Sie TAB.  
  
18. Typ `Total` in die **VB-Ausdruck eingeben** im Feld rechts neben der **TotalOut** -Eigenschaft, und drücken Sie TAB.  
  
19. Mit der rechten Maustaste **Program.cs** in **Projektmappen-Explorer** und wählen Sie **Anzeigecode**.  
  
20. Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. Kommentieren Sie den Aufruf der `CalculateDiscountInCode`-Methode in der `Main`-Methode aus, und fügen Sie den folgenden Code hinzu.  
  
    > [!NOTE]
    >  Wenn Sie das oben beschriebene Verfahren nicht ausgeführt haben und der `Main`-Standardcode vorhanden ist, ersetzen Sie den Inhalt von `Main` durch den folgenden Code.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. Erstellen Sie in der `Program`-Klasse eine neue Methode namens `CalculateDiscountUsingDesignerWorkflow`, die den folgenden Code enthält.  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen. Ändern Sie den Wert von `Subtotal` im folgenden Code, um eine andere `SubtotalValue`-Menge anzugeben.  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a>Übersicht über die Regelfunktionen  
 Das [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Regelmodul bietet Hilfe bei der prioritätsbasierten Verarbeitung von Regeln, wobei Vorwärtsverkettung unterstützt wird. Regeln können für ein einzelnes Element oder für die Elemente einer Auflistung ausgewertet werden. Eine Übersicht über Regeln und Informationen zu einer bestimmten Regelfunktionalität finden Sie in der folgenden Tabelle.  
  
|Regelfunktionen|Dokumentation|  
|-------------------|-------------------|  
|Übersicht über Regeln|[Einführung in das Windows Workflow Foundation-Regelmodul](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|RuleSet|[Verwenden von RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) und <xref:System.Workflow.Activities.Rules.RuleSet>|  
|Auswertung von Regeln|[Regelauswertung in RuleSets](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|Regelverkettung|[Steuerelement für die Vorwärtsverkettung](http://go.microsoft.com/fwlink/?LinkId=178518) und [Vorwärtsverketten von Regeln](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|Verarbeiten von Auflistungen in Regeln|[Verarbeiten von Auflistungen in Regeln](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|Verwenden der PolicyActivity|[Verwenden der PolicyActivity-Aktivität](http://go.microsoft.com/fwlink/?LinkId=178521) und <xref:System.Workflow.Activities.PolicyActivity>|  
  
 In erstellte Workflows [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] verwenden nicht alle Regelfunktionen von bereitgestellten [!INCLUDE[wf1](../../../includes/wf1-md.md)], z. B. deklarative aktivitätsbedingungen und bedingungsaktivitäten wie das <xref:System.Workflow.Activities.ConditionedActivityGroup> und <xref:System.Workflow.Activities.ReplicatorActivity>. Bei Bedarf ist diese Funktionalität für Workflows verfügbar, die mit [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] erstellt wurden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Hinweise zur Migration](../../../docs/framework/windows-workflow-foundation//migration-guidance.md).