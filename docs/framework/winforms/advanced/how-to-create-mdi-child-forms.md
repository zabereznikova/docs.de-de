---
title: "Gewusst wie: Erstellen von untergeordneten MDI-Formularen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Untergeordnete Formulare"
  - "MDI, Erstellen von Formularen"
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Gewusst wie: Erstellen von untergeordneten MDI-Formularen
Untergeordnete MDI\-Formulare sind ein wesentliches Element von [MDI\-Anwendungen \(Multiple Document Interface\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), weil diese Formulare den Mittelpunkt der Benutzerinteraktion darstellen.  
  
 Im folgenden Verfahren erstellen Sie ein untergeordnetes MDI\-Formular, das ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement anzeigt, das den meisten Textverarbeitungsprogrammen ähnelt.  Durch Ersetzen des <xref:System.Windows.Forms>\-Steuerelements durch andere Steuerelementen \(z. B. das <xref:System.Windows.Forms.DataGridView>\-Steuerelement oder eine Kombination von Steuerelementen können Sie untergeordnete MDI\-Fenster \(und durch Erweiterung auch MDI\-Anwendungen\) mit vielfältigen Möglichkeiten erstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie untergeordnete MDI\-Formulare  
  
1.  Erstellen Sie ein neues Windows Forms\-Projekt.  Legen Sie im Fenster **Eigenschaften** für das Formular seine Eigenschaft <xref:System.Windows.Forms.Form.IsMdiContainer%2A> auf `true`, und die Eigenschaft `WindowsState` auf `Maximized` fest.  
  
     Dies kennzeichnet das Formular als MDI\-Container für untergeordnete Fenster.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement aus der `Toolbox` in das Formular.  Legen Sie seine Eigenschaft `Text` auf **Datei** fest.  
  
3.  Klicken Sie auf die Auslassungspunkte \(...\) neben der Eigenschaft **Elemente**, und klicken Sie dann auf **Hinzufügen**, um zwei untergeordnete Menüelemente der Toolleiste hinzuzufügen.  Legen Sie die Eigenschaft `Text` für diese Elemente auf **Neu** und **Fenster** fest.  
  
4.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element hinzufügen**.  
  
5.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Windows Form** \(in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) oder **Windows Forms\-Anwendung \(.NET\)** \(in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) aus dem Bereich **Vorlagen** aus.  Geben Sie dem Formular im Feld **Name** den Namen "Form2".  Klicken Sie auf die Schaltfläche **Öffnen**, um dem Projekt das Formular hinzuzufügen.  
  
    > [!NOTE]
    >  Das untergeordnete MDI\-Formular, das Sie in diesem Schritt erstellten haben, ist ein Standard\-Windows Form.  Als solches besitzt es eine Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A>, mit der Sie die Transparenz des Formulars steuern können.  Allerdings wurde die Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A> für Fenster der obersten Ebene entwickelt.  Verwenden Sie sie nicht mit untergeordneten MDI\-Formularen, da Darstellungsprobleme auftreten können.  
  
     Dieses Formular wird die Vorlage für Ihre untergeordneten MDI\-Formulare.  
  
     Der **Windows Forms Designer** wird geöffnet und zeigt "Form2" an.  
  
6.  Ziehen Sie ein **RichTextBox**\-Steuerelement aus der **Toolbox** auf das Formular.  
  
7.  Legen Sie im Fenster **Eigenschaften** die Eigenschaft `Anchor` auf **Oben, Links** und die Eigenschaft `Dock` auf **Füllen** fest.  
  
     Dies bewirkt, dass das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement den Bereich des untergeordneten MDI\-Formulars selbst dann vollständig ausgefüllt, wenn die Größe des Formulars geändert wird.  
  
8.  Doppelklicken Sie auf das Menüelement **Neu**, um einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler zu erstellen.  
  
9. Fügen Sie Code ein, der dem folgenden ein Code ähnlich ist, um ein neues untergeordnetes MDI\-Formular zu erstellen, wenn der Benutzer auf das Menüelement **Neu** klickt.  
  
    > [!NOTE]
    >  Im folgenden Beispiel verarbeitet der Ereignishandler das <xref:System.Windows.Forms.Control.Click>\-Ereignis für `MenuItem2`.  Beachten Sie, dass abhängig von den Gegebenheiten Ihrer Anwendungsarchitektur Ihr Menüelement **Neu** ggf. nicht `MenuItem2` ist.  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     Fügen Sie in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] die folgende `#include`\-Direktive am Anfang von "Form1.h" hinzu:  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. Wählen Sie in der Dropdownliste oben im Fenster **Eigenschaften** die Menüleiste aus, die der Menüleiste **Datei** entspricht, und legen Sie die Eigenschaft <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> auf <xref:System.Windows.Forms.ToolStripMenuItem> des Fensters fest.  
  
     Auf diese Weise kann das Menü **Fenster** eine Liste der geöffneten untergeordneten MDI\-Fenster mit einem Häkchen neben dem aktiven untergeordneten Fenster verwalten.  
  
11. Drücken Sie F5, um die Anwendung auszuführen.  Durch Auswählen von **Neu** aus dem Menü **Datei** können Sie neue untergeordnete MDI\-Formulare erstellen, die im Menüelement **Fenster** nachverfolgt werden.  
  
    > [!NOTE]
    >  Wenn ein untergeordnetes MDI\-Formular eine Komponente <xref:System.Windows.Forms.MainMenu> \(in der Regel mit einer Menüstruktur aus Menüelementen\) besitzt und innerhalb eines übergeordneten MDI\-Formulars geöffnet wird, das eine Komponente <xref:System.Windows.Forms.MainMenu> \(in der Regel mit einer Menüstruktur aus Menüelementen\) besitzt, werden die Menüelemente automatisch zusammengeführt, wenn Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> \(und optional die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>\) festgelegt haben.  Legen Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> \-beider <xref:System.Windows.Forms.MainMenu>\-Komponenten sowie alle Menüelemente des untergeordneten Formulars auf <xref:System.Windows.Forms.MenuMerge> fest.  Legen Sie außerdem die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> so fest, dass die Menüelemente aus beiden Menüs in der gewünschten Reihenfolge angezeigt werden.  Bedenken Sie außerdem, dass beim Schließen eines übergeordneten MDI\-Formulars jedes untergeordnete MDI\-Formular ein Ereignis <xref:System.Windows.Forms.Form.Closing> auslöst, bevor das Ereignis <xref:System.Windows.Forms.Form.Closing> für das übergeordnete MDI\-Formular ausgelöst wird.  Durch das Abbrechen des <xref:System.Windows.Forms.Form.Closing>\-Ereignisses eines untergeordneten MDI\-Formulars wird nicht verhindert, dass das <xref:System.Windows.Forms.Form.Closing>\-Ereignis des übergeordneten MDI\-Formulars ausgelöst wird. Allerdings ist das <xref:System.ComponentModel.CancelEventArgs>\-Argument für das <xref:System.Windows.Forms.Form.Closing>\-Ereignis des übergeordneten MDI\-Formulars jetzt auf `true` festgelegt.  Sie können erzwingen, dass das übergeordnete MDI\-Element und alle untergeordneten MDI\-Formulare geschlossen werden, indem Sie das <xref:System.ComponentModel.CancelEventArgs>\-Argument auf `false` festlegen.  
  
## Siehe auch  
 [MDI\-Anwendungen \(Multiple Document Interface\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Gewusst wie: Erstellen von übergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Gewusst wie: Bestimmen des aktiven untergeordneten MDI\-Elements](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI\-Element](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Gewusst wie: Anordnen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)