---
title: "Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Debuggen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Debuggen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Exemplarische Vorgehensweisen"
  - "Debuggen [Visual Studio], Exemplarische Vorgehensweisen"
  - "Debuggen [Visual Studio], Windows Forms"
  - "Designer"
  - "Entwurfszeitdebuggen"
  - "Visuelle Editoren"
  - "Exemplarische Vorgehensweisen [Windows Forms], Debuggen"
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit
Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, ist es häufig notwendig, sein Entwurfszeitverhalten zu debuggen.  Dies gilt insbesondere, wenn Sie für das benutzerdefinierte Steuerelement einen benutzerdefinierten Designer erstellen.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines Windows Forms\-Steuerelements, das Visual Studio\-Entwurfszeitfeatures nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 Sie können benutzerdefinierte Steuerelemente mit Visual Studio ebenso wie andere .NET Framework\-Klassen debuggen.  Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen, die den Code des benutzerdefinierten Steuerelements ausführt.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms\-Projekts, um das benutzerdefinierte Steuerelement zu hosten  
  
-   Erstellen eines Steuerelementbibliothek\-Projekts  
  
-   Hinzufügen einer Eigenschaft zum benutzerdefinierten Steuerelement  
  
-   Hinzufügen des benutzerdefinierten Steuerelements zum Hostformular  
  
-   Einrichten des Projekts zum Entwurfszeitdebuggen  
  
-   Debuggen des benutzerdefinierten Steuerelements zur Entwurfszeit  
  
 Anschließend werden Sie die Aufgaben verstehen, die zum Debuggen des Entwurfszeitverhaltens eines benutzerdefinierten Steuerelements erforderlich sind.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Zunächst muss das Anwendungsprojekt erstellt werden.  Mit diesem Projekt erstellen Sie die Anwendung, die das benutzerdefinierte Steuerelement hostet.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie ein Windows\-Anwendungsprojekt mit dem Namen "DebuggingExample".  Ausführliche Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## Erstellen eines Steuerelementbibliothek\-Projekts  
 Der nächste Schritt besteht darin, das Steuerelementbibliothek\-Projekt zu erstellen und das benutzerdefinierte Steuerelement einzurichten.  
  
#### So erstellen Sie das Steuerelementbibliothek\-Projekt  
  
1.  Fügen Sie der Projektmappe ein **Windows\-Steuerelementbibliothek**\-Projekt hinzu.  
  
2.  Fügen Sie dem DebugControlLibrary\-Projekt ein neues **UserControl**\-Element hinzu.  Ausführliche Informationen finden Sie unter [NIB:How to: Add New Project Items](http://msdn.microsoft.com/de-de/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  Weisen Sie der neuen Quelldatei den Basisnamen "DebugControl" zu.  
  
3.  Löschen Sie im **Projektmappen\-Explorer** das standardmäßige Steuerelement des Projekts, indem Sie die Codedatei mit dem Basisnamen "`UserControl1`" löschen.  Ausführliche Informationen finden Sie unter [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/de-de/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Erstellen Sie die Projektmappe.  
  
## Checkpoint  
 An diesem Punkt wird das benutzerdefinierte Steuerelement in der **Toolbox** aufgeführt.  
  
#### So überprüfen Sie den Fortschritt  
  
-   Suchen Sie die neue Registerkarte **DebugControlLibrary\-Komponenten**, und wählen Sie sie durch Anklicken aus.  Wenn sie geöffnet wird, wird das Steuerelement als **DebugControl** mit einem Standardsymbol daneben aufgeführt.  
  
## Hinzufügen einer Eigenschaft zum benutzerdefinierten Steuerelement  
 Um zu zeigen, dass das benutzerdefinierte Steuerelement zur Entwurfszeit ausgeführt wird, fügen Sie eine Eigenschaft hinzu und legen im Code einen Haltepunkt fest, mit dem die Eigenschaft implementiert wird.  
  
#### So fügen Sie dem benutzerdefinierten Steuerelement eine Eigenschaft hinzu  
  
1.  Öffnen Sie **DebugControl** im **Code\-Editor**.  Fügen Sie der Klassendefinition den folgenden Code hinzu:  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  Erstellen Sie die Projektmappe.  
  
## Hinzufügen des benutzerdefinierten Steuerelements zum Hostformular  
 Um das Entwurfszeitverhalten des benutzerdefinierten Steuerelements zu debuggen, fügen Sie einem Hostformular eine Instanz der benutzerdefinierten Steuerelementklasse hinzu.  
  
#### So fügen Sie dem Hostformular das benutzerdefinierte Steuerelement hinzu  
  
1.  Öffnen Sie im "DebuggingExample"\-Projekt Form1 im **Windows Forms\-Designer**.  
  
2.  Öffnen Sie in der **Toolbox** die Registerkarte **DebugControlLibrary\-Komponenten**, und ziehen Sie eine **DebugControl**\-Instanz auf das Formular.  
  
3.  Suchen Sie die benutzerdefinierte `DemoString`\-Eigenschaft im **Eigenschaftenfenster**.  Beachten Sie, dass Sie ihren Wert ebenso ändern können wie den einer anderen Eigenschaft.  Beachten Sie außerdem, dass bei Auswahl der `DemoString`\-Eigenschaft die Beschreibung der Eigenschaft im unteren Bereich des **Eigenschaftenfensters** angezeigt wird.  
  
## Einrichten des Projekts zum Entwurfszeitdebuggen  
 Um das Entwurfszeitverhalten des benutzerdefinierten Steuerelements zu debuggen, müssen Sie eine separate Instanz von Visual Studio debuggen, die den Code des benutzerdefinierten Steuerelements ausführt.  
  
#### So richten Sie das Projekt zum Entwurfszeitdebuggen ein  
  
1.  Klicken Sie mit der rechten Maustaste auf das **DebugControlLibrary**\-Projekt im **Projektmappen\-Explorer**, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie im **DebugControlLibrary**\-Eigenschaftenblatt die Registerkarte **Debuggen** aus.  
  
     Wählen Sie im Abschnitt **Startaktion** die Option **Externes Programm starten** aus.  Da Sie eine separate Instanz von Visual Studio debuggen, klicken Sie auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um nach der Visual Studio IDE zu suchen.  Der Name der ausführbaren Datei lautet **devenv.exe**. Bei der Installation am Standardspeicherort lautet der Pfad %programfiles%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe.  
  
3.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
4.  Klicken Sie mit der rechten Maustaste auf das **DebugControlLibrary**\-Projekt, und wählen Sie **Als Startprojekt festlegen** aus, um diese Debugkonfiguration zu ermöglichen.  
  
## Debuggen des benutzerdefinierten Steuerelements zur Entwurfszeit  
 Nun kann das benutzerdefinierte Steuerelement debuggt werden, während es im Entwurfsmodus ausgeführt wird.  Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt, die Sie zum Laden der Projektmappe "DebuggingExample" verwenden.  Wenn Sie Form1 im **Windows Forms\-Designer** öffnen, wird eine Instanz des benutzerdefinierten Steuerelements erstellt und ausgeführt.  
  
#### So debuggen Sie das benutzerdefinierte Steuerelement zur Entwurfszeit  
  
1.  Öffnen Sie die **DebugControl**\-Quelldatei im **Code\-Editor**, und fügen Sie einen Haltepunkt am `Set`\-Accessor der `DemoString`\-Eigenschaft ein.  
  
2.  Drücken Sie F5, um die Debugsitzung zu starten.  Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird.  Sie können die beiden Instanzen auf zwei Arten unterscheiden:  
  
    -   Die Debuginstanz enthält in der Titelleiste das Wort **Aktiv**  
  
    -   In der Debuginstanz ist die Schaltfläche **Starten** auf der Symbolleiste **Debuggen** deaktiviert  
  
     Der Haltepunkt ist in der Debuginstanz festgelegt.  
  
3.  Öffnen Sie in der neuen Instanz von Visual Studio die "DebuggingExample"\-Projektmappe.  Sie können die Projektmappe leicht finden, indem Sie im Menü **Datei** die Option **Zuletzt geöffnete Projekte** auswählen.  Die "DebuggingExample.sln"\-Projektmappendatei wird als zuletzt verwendete Datei aufgelistet.  
  
4.  Öffnen Sie im **Windows Forms\-Designer** Form1, und wählen Sie das **DebugControl**\-Steuerelement aus.  
  
5.  Ändern Sie den Wert der `DemoString`\-Eigenschaft.  Beachten Sie, dass beim Speichern der Änderungen die Debuginstanz von Visual Studio aktiviert und die Ausführung am Haltepunkt gestoppt wird.  Sie können ebenso wie mit anderem Code den Eigenschaftenaccessor Schritt für Schritt durchlaufen.  
  
6.  Nach Abschluss der Debugsitzung können Sie diese beenden, indem Sie die gehostete Instanz von Visual Studio schließen oder in der Debuginstanz auf die Schaltfläche **Debuggen beenden** klicken.  
  
## Nächste Schritte  
 Nachdem Sie nun ein benutzerdefiniertes Steuerelement zur Entwurfszeit debuggen können, gibt es zahlreiche Möglichkeiten, die Interaktion des Steuerelements mit der Visual Studio IDE auszuweiten.  
  
-   Sie können mithilfe der <xref:System.ComponentModel.Component.DesignMode%2A>\-Eigenschaft der <xref:System.ComponentModel.Component>\-Klasse Code schreiben, der nur zur Entwurfszeit ausgeführt wird.  Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Es gibt zahlreiche Attribute, die Sie auf die Eigenschaften des Steuerelements anwenden können, um die Interaktion des benutzerdefinierten Steuerelements mithilfe des Designers zu bearbeiten.  Diese Attribute finden Sie im <xref:System.ComponentModel?displayProperty=fullName>\-Namespace.  
  
-   Sie können einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement erstellen.  Dadurch erhalten Sie die vollständige Kontrolle über den Entwurfsvorgang mit der erweiterbaren Designer\-Infrastruktur in Visual Studio.  Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines Windows Forms\-Steuerelements, das Visual Studio\-Entwurfszeitfeatures nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen eines Windows Forms\-Steuerelements, das Visual Studio\-Entwurfszeitfeatures nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)   
 [How to: Access Design\-Time Services](../Topic/How%20to:%20Access%20Design-Time%20Services.md)   
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)