---
title: 'Gewusst wie: Erstellen von untergeordneten MDI-Formularen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: bdfbe59ef779de242e32be11ca28c84f68437240
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43658924"
---
# <a name="how-to-create-mdi-child-forms"></a>Gewusst wie: Erstellen von untergeordneten MDI-Formularen
Untergeordnete MDI-Formulare sind ein wesentliches Element der [Multiple Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), wie diese Formulare den Mittelpunkt der Benutzerinteraktion sind.  
  
 Im folgenden Verfahren erstellen Sie ein untergeordnetes MDI-Formular, das ein <xref:System.Windows.Forms.RichTextBox>-Steuerelement anzeigt, das den meisten Textverarbeitungsprogrammen ähnelt. Durch Ersetzen des <xref:System.Windows.Forms>-Steuerelements durch andere Steuerelementen (z. B. das <xref:System.Windows.Forms.DataGridView>-Steuerelement oder eine Kombination von Steuerelementen können Sie untergeordnete MDI-Fenster (und durch Erweiterung auch MDI-Anwendungen) mit vielfältigen Möglichkeiten erstellen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-mdi-child-forms"></a>So erstellen Sie untergeordnete MDI-Formulare  
  
1.  Erstellen Sie ein neues Windows Forms-Projekt. In **der Eigenschaften Windows** legen Sie für das Formular seine <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft, um `true`, und die zugehörige `WindowsState` Eigenschaft, um `Maximized`.  
  
     Dies kennzeichnet das Formular als MDI-Container für untergeordnete Fenster.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der `Toolbox` in das Formular. Legen Sie dessen `Text` Eigenschaft **Datei**.  
  
3.  Klicken Sie auf die Auslassungspunkte (...) neben dem **Elemente** -Eigenschaft, und klicken Sie auf **hinzufügen** um zwei untergeordnete Menüelemente der Toolleiste hinzuzufügen. Legen Sie die `Text` -Eigenschaft für diese Elemente auf **neu** und **Fenster**.  
  
4.  In **Projektmappen-Explorer**, mit der rechten Maustaste in des Projekts, zeigen Sie auf **hinzufügen**, und wählen Sie dann **neues Element hinzufügen**.  
  
5.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Windows Form** (in Visual Basic oder Visual c#) oder **Windows Forms-Anwendung (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) aus der  **Vorlagen** Bereich. In der **Namen** benennen Sie das Formular **Form2**. Klicken Sie auf die **öffnen** , um das Formular zum Projekt hinzuzufügen.  
  
    > [!NOTE]
    >  Das untergeordnete MDI-Formular, das Sie in diesem Schritt erstellten haben, ist ein Standard-Windows Form. Als solches besitzt es eine Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A>, mit der Sie die Transparenz des Formulars steuern können. Allerdings wurde die Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A> für Fenster der obersten Ebene entwickelt. Verwenden Sie sie nicht mit untergeordneten MDI-Formularen, da Darstellungsprobleme auftreten können.  
  
     Dieses Formular wird die Vorlage für Ihre untergeordneten MDI-Formulare.  
  
     Die **Windows Forms-Designer** wird geöffnet und zeigt **Form2**.  
  
6.  Von der **Toolbox**, ziehen Sie eine **RichTextBox** -Steuerelement auf das Formular.  
  
7.  In der **Eigenschaften** legen die `Anchor` Eigenschaft **oberen, linken** und die `Dock` Eigenschaft **füllen**.  
  
     Dies bewirkt, dass das <xref:System.Windows.Forms.RichTextBox>-Steuerelement den Bereich des untergeordneten MDI-Formulars selbst dann vollständig ausgefüllt, wenn die Größe des Formulars geändert wird.  
  
8.  Doppelklicken dem **neu** Menüelement zum Erstellen einer <xref:System.Windows.Forms.Control.Click> -Ereignishandler.  
  
9. Fügen Sie Code wie folgt, um ein neues untergeordnetes MDI-Formular zu erstellen, wenn der Benutzer klickt auf die **neu** Menüelement.  
  
    > [!NOTE]
    >  Im folgenden Beispiel verarbeitet der Ereignishandler das <xref:System.Windows.Forms.Control.Click>-Ereignis für `MenuItem2`. Beachten Sie, abhängig von den gegebenheiten Ihrer Anwendungsarchitektur Ihr **neu** Menüelement möglicherweise nicht `MenuItem2`.  
  
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
  
     Fügen Sie in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] die folgende `#include`-Direktive am Anfang von "Form1.h" hinzu:  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. In der Dropdownliste am oberen Rand der **Eigenschaften** Fenster, wählen Sie die Menüleiste, die entspricht, der **Datei** Menüleiste, und legen die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft, um das Fenster <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
     Dadurch werden die **Fenster** Menü, um eine Liste der geöffneten untergeordneten MDI-Fenster mit einem Häkchen neben dem aktiven untergeordneten Fenster verwalten.  
  
11. Drücken Sie F5, um die Anwendung auszuführen. Durch Auswahl **neu** aus der **Datei** im Menü Erstellen Sie neue untergeordnete MDI-Formulare, die bleiben im Überblick darüber, sind die **Fenster** Menüelement.  
  
    > [!NOTE]
    >  Wenn ein untergeordnetes MDI-Formular eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt und innerhalb eines übergeordneten MDI-Formulars geöffnet wird, das eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt, werden die Menüelemente automatisch zusammengeführt, wenn Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> (und optional die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>) festgelegt haben. Legen Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> -beider <xref:System.Windows.Forms.MainMenu>-Komponenten sowie alle Menüelemente des untergeordneten Formulars auf <xref:System.Windows.Forms.MenuMerge.MergeItems> fest. Legen Sie außerdem die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> so fest, dass die Menüelemente aus beiden Menüs in der gewünschten Reihenfolge angezeigt werden. Bedenken Sie außerdem, dass beim Schließen eines übergeordneten MDI-Formulars jedes untergeordnete MDI-Formular ein Ereignis <xref:System.Windows.Forms.Form.Closing> auslöst, bevor das Ereignis <xref:System.Windows.Forms.Form.Closing> für das übergeordnete MDI-Formular ausgelöst wird. Durch das Abbrechen des <xref:System.Windows.Forms.Form.Closing>-Ereignisses eines untergeordneten MDI-Formulars wird nicht verhindert, dass das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars ausgelöst wird. Allerdings ist das <xref:System.ComponentModel.CancelEventArgs>-Argument für das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars jetzt auf `true` festgelegt. Sie können erzwingen, dass das übergeordnete MDI-Element und alle untergeordneten MDI-Formulare geschlossen werden, indem Sie das <xref:System.ComponentModel.CancelEventArgs>-Argument auf `false` festlegen.  
  
## <a name="see-also"></a>Siehe auch  
 [MDI-Anwendungen (Multiple Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Gewusst wie: Anordnen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
