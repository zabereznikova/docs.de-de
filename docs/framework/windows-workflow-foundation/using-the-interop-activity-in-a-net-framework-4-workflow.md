---
title: Verwenden der Interop-Aktivität in einem .NET Framework 4-Workflow
ms.date: 03/30/2017
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
ms.openlocfilehash: 64e8aef01aefa23dc98b42ab835de097d6c222df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520226"
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a>Verwenden der Interop-Aktivität in einem .NET Framework 4-Workflow
Mit [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] oder [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] erstellte Aktivitäten können in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflow mithilfe der <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden. Dieses Thema enthält eine Übersicht über die Verwendung der <xref:System.Activities.Statements.Interop>-Aktivität.  
  
> [!NOTE]
>  Die <xref:System.Activities.Statements.Interop> Aktivität wird nicht in der Toolbox des Workflow-Designer angezeigt, es sei denn, das Projekt des Workflows dessen **Zielframework** eingestellt **.Net Framework 4** oder höher.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>Verwenden der Interop-Aktivität in Workflows von .NET Framework 4.5  
 In diesem Thema wird eine [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivitätsbibliothek erstellt, die eine `DiscountCalculator`-Aktivität enthält. Der `DiscountCalculator` berechnet einen Rabatt auf Grundlage einer Kaufmenge. Er besteht aus einem <xref:System.Workflow.Activities.SequenceActivity>-Objekt, das ein <xref:System.Workflow.Activities.PolicyActivity>-Objekt enthält.  
  
> [!NOTE]
>  Die in diesem Thema erstellte [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivität implementiert die Logik der Aktivität mithilfe eines <xref:System.Workflow.Activities.PolicyActivity>-Objekts. Die Verwendung von Regeln in einem [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Workflow erfordert weder eine benutzerdefinierte <xref:System.Activities.Statements.Interop>-Aktivität noch die [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Aktivität. Ein Beispiel der Verwendung von Regeln in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow ohne Verwendung der <xref:System.Activities.Statements.Interop> Aktivität, finden Sie unter der [Richtlinienaktivität in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) Beispiel.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>So erstellen Sie das Projekt für die .NET Framework 3.5-Aktivitätsbibliothek  
  
1.  Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] , und wählen Sie **neu** und dann **Projekt...** aus der **Datei** Menü.  
  
2.  Erweitern Sie die **andere Projekttypen** Knoten in der **installierte Vorlagen** und wählen **Visual Studio-Projektmappen**.  
  
3.  Wählen Sie **leere Projektmappe** aus der **Visual Studio-Projektmappen** Liste. Typ `PolicyInteropDemo` in der **Namen** Feld, und klicken Sie auf **OK**.  
  
4.  Mit der rechten Maustaste **PolicyInteropDemo** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **neues Projekt...** .  
  
    > [!TIP]
    >  Wenn die **Projektmappen-Explorer** Fenster ist nicht sichtbar ist, wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.  
  
5.  In der **installierte Vorlagen** Liste **Visual C#-** und dann **Workflow**. Wählen Sie **.NET Framework 3.5** aus .NET Framework Version Dropdown-Liste, und wählen Sie dann **Workflowaktivitätsbibliothek** aus der **Vorlagen** Liste.  
  
6.  Typ `PolicyActivityLibrary` in der **Namen** Feld, und klicken Sie auf **OK**.  
  
7.  Mit der rechten Maustaste **Activity1.cs** in **Projektmappen-Explorer** , und wählen Sie **löschen**. Klicken Sie zur Bestätigung auf **OK** .  
  
#### <a name="to-create-the-discountcalculator-activity"></a>So erstellen Sie die DiscountCalculator-Aktivität  
  
1.  Mit der rechten Maustaste **PolicyActivityLibrary** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **Aktivität...** .  
  
2.  Wählen Sie **Aktivität (mit getrenntem Code)** aus der **Visual C#-Elemente** Liste. Typ `DiscountCalculator` in der **Namen** Feld, und klicken Sie auf **OK**.  
  
3.  Mit der rechten Maustaste **DiscountCalculator.xoml** in **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**.  
  
4.  Fügen Sie der `DiscountCalculator`-Klasse die folgenden drei Eigenschaften hinzu:  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  Mit der rechten Maustaste **DiscountCalculator.xoml** in **Projektmappen-Explorer** , und wählen Sie **Sicht-Designer**.  
  
6.  Ziehen Sie eine **Richtlinie** Aktivität aus der **Windows Workflow v3. 0** Teil der **Toolbox** und legen Sie sie in der **DiscountCalculator** Aktivität .  
  
    > [!TIP]
    >  Wenn die **Toolbox** Fenster ist nicht sichtbar ist, wählen **Toolbox** aus der **Ansicht** Menü.  
  
#### <a name="to-configure-the-rules"></a>So konfigurieren Sie die Regeln  
  
1.  Klicken Sie auf die neu hinzugefügte **Richtlinie** Aktivität, um diese auszuwählen, falls er nicht bereits ausgewählt ist.  
  
2.  Klicken Sie auf die **RuleSetReference** Eigenschaft in der **Eigenschaften** Fenster aus, um auszuwählen, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um die rechts neben der Eigenschaft.  
  
    > [!TIP]
    >  Wenn die **Eigenschaften** nicht sichtbar ist, wählen Sie **Fenster "Eigenschaften"** aus der **Ansicht** Menü.  
  
3.  Wählen Sie **klicken Sie auf neu...** .  
  
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
  
14. Klicken Sie auf **OK** schließen die **Regelsatz-Editor** (Dialogfeld).  
  
15. Sicherstellen, dass die neu erstellte <xref:System.Workflow.Activities.Rules.RuleSet> ausgewählt ist, der **Namen** aus, und klicken Sie auf **OK**.  
  
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
  
 Wenn das <xref:System.Workflow.Activities.PolicyActivity>-Objekt ausgeführt wird, werten diese drei Regeln die Eigenschaftswerte `Subtotal`, `DiscountPercent` und `Total` der `DiscountCalculator`-Aktivität aus und ändern sie, um den gewünschten Rabatt zu errechnen.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Verwenden der DiscountCalculator-Aktivität mit der Interop-Aktivität  
 Damit die `DiscountCalculator`-Aktivität in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflow verwendet werden kann, kommt die <xref:System.Activities.Statements.Interop>-Aktivität zum Einsatz. In diesem Abschnitt werden zwei Workflows erstellt – einer mithilfe von Code und einer mithilfe des Workflow-Designers –, um zu veranschaulichen, wie die <xref:System.Activities.Statements.Interop>-Aktivität mit der `DiscountCalculator`-Aktivität verwendet wird. Für beide Workflows wird die gleiche Hostanwendung verwendet.  
  
#### <a name="to-create-the-host-application"></a>So erstellen Sie die Hostanwendung  
  
1.  Mit der rechten Maustaste **PolicyInteropDemo** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, und klicken Sie dann **neues Projekt...** .  
  
2.  Sicherstellen, dass **.NET Framework 4.5** , die in der Dropdownliste mit den .NET Framework-Version ausgewählt ist, und wählen Sie **Workflowkonsolenanwendung** aus der **Visual C#-Elemente** Liste.  
  
3.  Typ `PolicyInteropHost` in der **Namen** Feld, und klicken Sie auf **OK**.  
  
4.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.  
  
5.  In der **Zielframework** Dropdown-Liste, ändern Sie die Auswahl von **.NET Framework 4 Client Profile** auf **.NET Framework 4.5**. Klicken Sie auf **Ja** zu bestätigen.  
  
6.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen...** .  
  
7.  Wählen Sie **PolicyActivityLibrary** aus der **Projekte** Registerkarte, und klicken Sie auf **OK**.  
  
8.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen...** .  
  
9. Wählen Sie **System.Workflow.Activities**, **System.Workflow.ComponentModel**, und klicken Sie dann **System.Workflow.ComponentModel** aus der **.NET**Registerkarte, und klicken Sie auf **OK**.  
  
10. Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.  
  
11. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
### <a name="using-the-interop-activity-in-code"></a>Verwenden der Interop-Aktivität im Code  
 In diesem Beispiel wird eine Workflowdefinition mithilfe von Code erstellt, der die <xref:System.Activities.Statements.Interop>-Aktivität und die `DiscountCalculator`-Aktivität enthält. Dieser Workflow wird mit dem <xref:System.Activities.WorkflowInvoker>-Objekt aufgerufen, und die Ergebnisse der Regelauswertung werden mithilfe der <xref:System.Activities.Statements.WriteLine>-Aktivität in die Konsole geschrieben.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>So verwenden Sie die Interop-Aktivität im Code  
  
1.  Mit der rechten Maustaste **"Program.cs"** in **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**.  
  
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
    >  Die Eigenschaften `Subtotal`, `DiscountPercent` und `Total` der `DiscountCalculator`-Aktivität werden als Argumente der <xref:System.Activities.Statements.Interop>-Aktivität verfügbar gemacht und an lokale Workflowvariablen in der <xref:System.Activities.Statements.Interop>-Auflistung der <xref:System.Activities.Statements.Interop.ActivityProperties%2A>-Aktivität gebunden. `Subtotal` wird als <xref:System.Activities.ArgumentDirection.In>-Argument hinzugefügt, da die `Subtotal`-Daten in die <xref:System.Activities.Statements.Interop>-Aktivität übertragen werden, und `DiscountPercent` und `Total` werden als <xref:System.Activities.ArgumentDirection.Out>-Argumente hinzugefügt, da ihre Daten aus der <xref:System.Activities.Statements.Interop>-Aktivität übertragen werden. Beachten Sie, dass die zwei <xref:System.Activities.ArgumentDirection.Out>-Argumente unter den Namen `DiscountPercentOut` und `TotalOut` hinzugefügt werden, um zu kennzeichnen, dass sie <xref:System.Activities.ArgumentDirection.Out>-Argumente darstellen. Der `DiscountCalculator`-Typ wird als <xref:System.Activities.Statements.Interop> der <xref:System.Activities.Statements.Interop.ActivityType%2A>-Aktivität angegeben.  
  
5.  Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen. Probieren Sie unterschiedliche Werte für den `Subtotal`-Wert aus, um die verschiedenen Rabattstufen zu testen, die von der `DiscountCalculator`-Aktivität bereitgestellt werden.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Verwenden der Interop-Aktivität im Workflow-Designer  
 In diesem Beispiel wird ein Workflow mithilfe des Workflow-Designers erstellt. Dieser Workflow verfügt über die gleiche Funktionalität wie der Workflow im vorherigen Beispiel, hier wird der Rabatt jedoch nicht über eine <xref:System.Activities.Statements.WriteLine>-Aktivität angezeigt. Stattdessen ruft die Hostanwendung die Rabattinformationen ab, wenn der Workflow abgeschlossen wird, und zeigt sie dann an. Außerdem sind die Daten nicht in lokalen Workflowvariablen enthalten. Die Argumente werden im Workflow-Designer erstellt, und die Werte werden vom Host übergeben, wenn der Workflow aufgerufen wird.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>So hosten Sie die Policy-Aktivität mithilfe eines vom Workflow-Designer erstellten Workflows  
  
1.  Mit der rechten Maustaste **"Workflow1.xaml"** in **Projektmappen-Explorer** , und wählen Sie **löschen**. Klicken Sie zur Bestätigung auf **OK** .  
  
2.  Mit der rechten Maustaste **PolicyInteropHost** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element...** .  
  
3.  Erweitern Sie die **Visual C#-Elemente** Knoten, und wählen **Workflow**. Wählen Sie **Aktivität** aus der **Visual C#-Elemente** Liste.  
  
4.  Typ `DiscountWorkflow` in der **Namen** Feld, und klicken Sie auf **hinzufügen**.  
  
5.  Klicken Sie auf die **Argumente** Schaltfläche auf die links unten im Workflow-Designer zum Anzeigen der **Argumente** Bereich.  
  
6.  Klicken Sie auf **Argument erstellen**.  
  
7.  Typ `Subtotal` in der **Namen** wählen Sie im **In** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdownliste aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
    > [!NOTE]
    >  Wenn **doppelte** befindet sich nicht in der **Argumenttyp** Dropdown-Liste **nach Typen suchen...** , Typ `System.Double` in der **Typnamen** ein, und klicken Sie auf **OK**.  
  
8.  Klicken Sie auf **Argument erstellen**.  
  
9. Typ `DiscountPercent` in der **Namen** wählen Sie im **Out** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdownliste aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
10. Klicken Sie auf **Argument erstellen**.  
  
11. Typ `Total` in der **Namen** wählen Sie im **Out** aus der **Richtung** Dropdownliste, wählen **doppelte** aus der **Argumenttyp** Dropdownliste aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
12. Klicken Sie auf die **Argumente** Schaltfläche links unten im Workflow-Designer schließen auf die **Argumente** Bereich.  
  
13. Ziehen Sie eine **Sequenz** Aktivität aus der **Control Flow** Teil der **Toolbox** und legen ihn auf die Oberfläche des Workflow-Designers.  
  
14. Ziehen Sie ein **Interop** Aktivität aus der **Migration** Teil der **Toolbox** und legen Sie sie in der **Sequenz** Aktivität.  
  
15. Klicken Sie auf die **Interop** Aktivität auf die **klicken Sie auf Durchsuchen...** beschriften, **DiscountCalculator** in der **Typnamen** ein, und klicken Sie auf **OK**.  
  
    > [!NOTE]
    >  Wenn dem Workflow die <xref:System.Activities.Statements.Interop>-Aktivität hinzugefügt wird und der `DiscountCalculator`-Typ als <xref:System.Activities.Statements.Interop.ActivityType%2A> angegeben wird, macht die <xref:System.Activities.Statements.Interop>-Aktivität drei <xref:System.Activities.ArgumentDirection.In>-Argumente und drei <xref:System.Activities.ArgumentDirection.Out>-Argumente verfügbar. Diese stellen die drei öffentlichen Eigenschaften der `DiscountCalculator`-Aktivität dar. Die <xref:System.Activities.ArgumentDirection.In> Argumente haben den gleichen Namen wie die drei öffentlichen Eigenschaften und die drei <xref:System.Activities.ArgumentDirection.Out> -Argumente haben den gleichen Namen mit **Out** des Eigenschaftennamens angefügt. In den folgenden Schritten werden die in den vorherigen Schritten erstellten Workflowargumente an die Argumente der <xref:System.Activities.Statements.Interop>-Aktivität gebunden.  
  
16. Typ `DiscountPercent` in der **VB-Ausdruck eingeben** Feld rechts neben der **DiscountPercentOut** -Eigenschaft, und drücken Sie TAB.  
  
17. Typ `Subtotal` in der **VB-Ausdruck eingeben** Feld rechts neben der **Subtotal** -Eigenschaft, und drücken Sie TAB.  
  
18. Typ `Total` in der **VB-Ausdruck eingeben** Feld rechts neben der **TotalOut** -Eigenschaft, und drücken Sie TAB.  
  
19. Mit der rechten Maustaste **"Program.cs"** in **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**.  
  
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
|Regelverkettung|[Vorwärtsverkettung Steuerelement](http://go.microsoft.com/fwlink/?LinkId=178518) und [Vorwärtsverketten von Regeln](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|Verarbeiten von Auflistungen in Regeln|[Verarbeiten von Auflistungen in Regeln](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|Verwenden der PolicyActivity|[Verwenden der PolicyActivity-Aktivität](http://go.microsoft.com/fwlink/?LinkId=178521) und <xref:System.Workflow.Activities.PolicyActivity>|  
  
 In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] erstellte Workflows verwenden nicht alle Regelfunktionen, die von [!INCLUDE[wf1](../../../includes/wf1-md.md)] bereitgestellt werden, z. B. deklarative Aktivitätsbedingungen und Bedingungsaktivitäten wie das <xref:System.Workflow.Activities.ConditionedActivityGroup>-Objekt und das <xref:System.Workflow.Activities.ReplicatorActivity>-Objekt. Bei Bedarf ist diese Funktionalität für Workflows verfügbar, die mit [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] erstellt wurden. Weitere Informationen finden Sie unter [Migrationsanleitung](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).
