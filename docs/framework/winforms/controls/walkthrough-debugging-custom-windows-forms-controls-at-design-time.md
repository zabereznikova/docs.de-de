---
title: 'Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4dfdc102a5aeb2e3eaccde28a8ce57a1878141e4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit
Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, werden häufig finden Sie es zum Debuggen des Verhaltens zur Entwurfszeit. Dies gilt vor allem, wenn Sie einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement erstellen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass akzeptiert Vorteil von Visual Studio zur Entwurfszeit-Funktionen](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 Sie können Ihre benutzerdefinierten Steuerelemente, die mit Visual Studio debuggen, wie andere .NET Framework-Klassen Debuggen. Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen möchten, die das benutzerdefinierte Steuerelement Code ausgeführt wird  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen eines Windows Forms-Projekts zum Hosten des benutzerdefinierten Steuerelements  
  
-   Erstellen eines Projekts für eine Bibliothek  
  
-   Hinzufügen einer Eigenschaft, um das benutzerdefinierte Steuerelement  
  
-   Das benutzerdefinierte Steuerelement hinzufügen dem Formular host  
  
-   Einrichten des Projekts zum Debuggen zur Entwurfszeit  
  
-   Debuggen des benutzerdefinierten Steuerelements zur Entwurfszeit  
  
 Wenn Sie fertig sind, müssen Sie einen Überblick über die Aufgaben zum Debuggen der Entwurfszeitverhalten eines benutzerdefinierten Steuerelements erforderlich.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Der erste Schritt besteht darin das Anwendungsprojekt zu erstellen. Verwenden Sie dieses Projekt zum Erstellen der Anwendung, die das benutzerdefinierte Steuerelement hostet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
-   Erstellen Sie ein Windows-Anwendungsprojekt mit dem Namen "DebuggingExample". Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## <a name="creating-a-control-library-project"></a>Erstellen eines Projekts für eine Bibliothek  
 Der nächste Schritt ist zur-Steuerelementbibliothek-Projekt erstellen und richten Sie das benutzerdefinierte Steuerelement.  
  
#### <a name="to-create-the-control-library-project"></a>-Steuerelementbibliothek-Projekt erstellen  
  
1.  Hinzufügen einer **Windows-Steuerelementbibliothek** Projekt der Projektmappe.  
  
2.  Fügen Sie einen neuen **UserControl** dem DebugControlLibrary-Projekt. Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen neuer Projektelemente](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Benennen Sie die neue Quelldatei Basis von "DebugControl".  
  
3.  Mithilfe der **Projektmappen-Explorer**, Standardsteuerelement für das Projekt löschen, indem Sie die Codedatei mit dem Basisnamen der löschen "`UserControl1`". Weitere Informationen finden Sie unter [NIB: Vorgehensweise: entfernen, löschen und Ausschließen von Elementen](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Erstellen Sie die Projektmappe.  
  
## <a name="checkpoint"></a>Checkpoint  
 Sehen Sie das benutzerdefinierte Steuerelement im an diesem Punkt werden die **Toolbox**.  
  
#### <a name="to-check-your-progress"></a>Um den Status zu überprüfen  
  
-   Suchen Sie die neue Registerkarte **DebugControlLibrary Komponenten** , und klicken Sie hier, um ihn auszuwählen. Wenn sie geöffnet wird, sehen Sie das Steuerelement als aufgeführt **DebugControl** mit dem Standardsymbol daneben.  
  
## <a name="adding-a-property-to-your-custom-control"></a>Hinzufügen einer Eigenschaft, um das benutzerdefinierte Steuerelement  
 Um zu zeigen, dass Ihr Code des benutzerdefinierten Steuerelements zur Entwurfszeit ausgeführt wird, Sie fügen eine Eigenschaft hinzu und legen Sie einen Haltepunkt im Code, der die Eigenschaft implementiert.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>Das benutzerdefinierte Steuerelement eine Eigenschaft hinzu  
  
1.  Open **DebugControl** in der **Code-Editor**. Fügen Sie der Klassendefinition den folgenden Code hinzu:  
  
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
  
## <a name="adding-your-custom-control-to-the-host-form"></a>Das benutzerdefinierte Steuerelement hinzufügen dem Formular Host  
 Um das Entwurfszeitverhalten des benutzerdefinierten Steuerelements zu debuggen, geben Sie eine Instanz der Klasse des benutzerdefinierten Steuerelements auf einem Hostformular an.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>Das benutzerdefinierte Steuerelement dem Formular Host hinzufügen  
  
1.  Öffnen Sie im Projekt "DebuggingExample" Form1 in der **Windows Forms-Designer**.  
  
2.  In der **Toolbox**öffnen die **DebugControlLibrary Komponenten** Registerkarte, und ziehen Sie eine **DebugControl** Instanz auf das Formular.  
  
3.  Suchen der `DemoString` benutzerdefinierte Eigenschaft in der **Eigenschaften** Fenster. Beachten Sie, dass Sie den Wert ändern können, wie Sie eine andere Eigenschaft. Beachten Sie außerdem, dass bei der `DemoString` Eigenschaft aktiviert ist, die Eigenschaft Beschreibungszeichenfolge angezeigt wird, am unteren Rand der **Eigenschaften** Fenster.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts zum Debuggen zur Entwurfszeit  
 Um das benutzerdefinierte Steuerelement Entwurfszeitverhalten zu debuggen, Debuggen Sie eine separate Instanz von Visual Studio, die das benutzerdefinierte Steuerelement Code ausgeführt wird.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>So richten Sie das Projekt zum Debuggen zur Entwurfszeit ein  
  
1.  Mit der rechten Maustaste auf die **DebugControlLibrary** -Projekt in der **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.  
  
2.  In der **DebugControlLibrary** Eigenschaftenblatt, wählen die **Debuggen** Registerkarte.  
  
     In der **Startaktion** Abschnitt **externes Programm starten**. Sie Debuggen eine separate Instanz von Visual Studio, klicken Sie auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) Schaltfläche, um für die Visual Studio-IDE zu navigieren. Der Name der ausführbaren Datei ist **devenv.exe**, und wenn Sie am Standardspeicherort installiert haben, lautet %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.  
  
3.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
4.  Mit der rechten Maustaste die **DebugControlLibrary** Projekt, und wählen Sie **als Startprojekt festlegen** um diese Konfiguration für Remotedebugging zu aktivieren.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>Debuggen des benutzerdefinierten Steuerelements zur Entwurfszeit  
 Jetzt können Sie Ihr benutzerdefinierte Steuerelement zu debuggen, wie er im Entwurfsmodus ausgeführt wird. Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt werden, und verwenden Sie es zum Laden der Projektmappe "DebuggingExample". Beim Öffnen Sie Form1 in der **Forms-Designer**, eine Instanz eines benutzerdefinierten Steuerelements erstellt und ausgeführt.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>So debuggen Sie das benutzerdefinierte Steuerelement zur Entwurfszeit  
  
1.  Öffnen der **DebugControl** -Quelldatei in die **Code-Editor** und fügen Sie einen Haltepunkt auf der `Set` Accessor, der die `DemoString` Eigenschaft.  
  
2.  Drücken Sie F5, um die Debugsitzung zu starten. Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird. Sie können zwischen den Instanzen auf zwei Arten unterschieden:  
  
    -   Die debugging-Instanz hat das Wort **ausführen** in der Titelleiste  
  
    -   Die debugging-Instanz hat die **starten** Schaltfläche auf seine **Debuggen** Symbolleiste deaktiviert  
  
     Der Haltepunkt wird in der debugging-Instanz festgelegt.  
  
3.  Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "DebuggingExample". Sie können auswählen, um die Projektmappe leicht zu finden **zuletzt geöffnete Projekte** aus der **Datei** Menü. Die Projektmappendatei "DebuggingExample.sln" werden die zuletzt verwendeten Datei aufgeführt.  
  
4.  Öffnen Sie Form1 in der **Forms-Designer** , und wählen Sie die **DebugControl** Steuerelement.  
  
5.  Ändern Sie den Wert, der die `DemoString` Eigenschaft. Beachten Sie, dass wenn Sie die Änderung zu bestätigen, das Debuggen Instanz von Visual Studio den Fokus erhält, und die Ausführung am Haltepunkt hält. Können Sie Schritt für Schritt durch den Eigenschaftenaccessor ebenso wie die anderen Code würde.  
  
6.  Wenn Sie mit der Debugsitzung fertig sind, können Sie beenden, schließen die gehostete Instanz von Visual Studio oder durch Klicken auf die **Beenden des Debuggens** Schaltfläche in der debugging-Instanz.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Nun, dass Sie der benutzerdefinierten Steuerelemente zur Entwurfszeit Debuggen können, gibt es viele Möglichkeiten für die Erweiterung des Steuerelements Interaktion mit der Visual Studio-IDE.  
  
-   Können Sie die <xref:System.ComponentModel.Component.DesignMode%2A> Eigenschaft von der <xref:System.ComponentModel.Component> Klasse zum Schreiben von Code, der nur zur Entwurfszeit ausgeführt wird. Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Es sind mehrere Attribute können Sie auf die Eigenschaften des Steuerelements zum Bearbeiten des benutzerdefinierten Steuerelements Interaktion mit dem Designer anwenden. Sie finden diese Attribute in der <xref:System.ComponentModel?displayProperty=nameWithType> Namespace.  
  
-   Sie können einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement schreiben. Dies bietet Ihnen die vollständige Kontrolle über die entwurfsumgebung, die über die erweiterbare Designer-Infrastruktur, die von Visual Studio verfügbar gemacht werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass akzeptiert Vorteil von Visual Studio zur Entwurfszeit-Funktionen](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [Vorgehensweise: Zugriff auf Entwurfszeitdienste](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [Vorgehensweise: Zugriff auf Entwurfszeitunterstützung in Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
