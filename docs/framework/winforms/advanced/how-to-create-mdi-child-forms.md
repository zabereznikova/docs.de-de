---
title: 'Vorgehensweise: Erstellen von untergeordneten MDI-Formularen'
description: Erfahren Sie, wie Sie Visual Studio verwenden, um ein untergeordnetes MDI-Formular (Multiple Document Interface) zu erstellen, das ein RichTextBox-Steuerelement anzeigt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 7fe5cde342f0f5ee078f888b7492cd4618bea5c4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903180"
---
# <a name="how-to-create-mdi-child-forms"></a>Gewusst wie: Erstellen von untergeordneten MDI-Formularen

Untergeordnete MDI-Formulare sind ein wesentliches Element von [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md), da diese Formen den Mittelpunkt der Benutzerinteraktion bilden.

Im folgenden Verfahren verwenden Sie Visual Studio, um ein untergeordnetes MDI-Formular zu erstellen, in dem ein- <xref:System.Windows.Forms.RichTextBox> Steuerelement ähnlich wie bei den meisten Textverarbeitungsanwendungen angezeigt wird. Indem Sie das Steuerelement durch <xref:System.Windows.Forms> andere Steuerelemente ersetzen, z. b. das-Steuerelement <xref:System.Windows.Forms.DataGridView> oder eine Kombination von Steuerelementen, können Sie untergeordnete MDI-Fenster (und durch Erweiterung MDI-Anwendungen) mit unterschiedlichen Möglichkeiten erstellen.

## <a name="create-mdi-child-forms"></a>Erstellen von untergeordneten MDI-Formularen

1. Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Studio. Legen Sie im Fenster **Eigenschaften** für das Formular seine <xref:System.Windows.Forms.Form.IsMdiContainer%2A> -Eigenschaft auf `true` und die- `WindowsState` Eigenschaft auf fest `Maximized` .

   Dies kennzeichnet das Formular als MDI-Container für untergeordnete Fenster.

2. Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der `Toolbox` in das Formular. Legen Sie die- `Text` Eigenschaft auf **File**fest.

3. Klicken Sie auf die Schaltfläche mit den Auslassungs Zeichen (...) neben der Eigenschaft **Items** , und klicken Sie auf **Hinzufügen** , um zwei untergeordnete Menü Elemente für Tool Legen `Text` Sie die-Eigenschaft für diese Elemente auf **neu** und **Window**fest.

4. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

5. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Windows Form** (in Visual Basic oder in Visual c#) oder **Windows Forms Anwendung (.net)** (in Visual C++) aus dem Bereich **Vorlagen** aus. Benennen Sie im Feld **Name** das Formular **Form2**. Wählen Sie **Öffnen** aus, um das Formular dem Projekt hinzuzufügen.

    > [!NOTE]
    > Das untergeordnete MDI-Formular, das Sie in diesem Schritt erstellten haben, ist ein Standard-Windows Form. Als solches besitzt es eine Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A>, mit der Sie die Transparenz des Formulars steuern können. Allerdings wurde die Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A> für Fenster der obersten Ebene entwickelt. Verwenden Sie sie nicht mit untergeordneten MDI-Formularen, da Darstellungsprobleme auftreten können.

     Dieses Formular wird die Vorlage für Ihre untergeordneten MDI-Formulare.

     Der **Windows Forms-Designer** wird geöffnet und zeigt **Form2**an.

6. Ziehen Sie ein **RichTextBox** -Steuerelement aus der **Toolbox**auf das Formular.

7. Legen Sie im Fenster **Eigenschaften** die `Anchor` -Eigenschaft auf **oben, Links** und die- `Dock` Eigenschaft auf **Fill**fest.

   Dies bewirkt, dass das <xref:System.Windows.Forms.RichTextBox>-Steuerelement den Bereich des untergeordneten MDI-Formulars selbst dann vollständig ausgefüllt, wenn die Größe des Formulars geändert wird.

8. Doppelklicken Sie auf das **neue** Menü Element, um einen- <xref:System.Windows.Forms.Control.Click> Ereignishandler dafür zu erstellen.

9. Fügen Sie Code ähnlich dem folgenden ein, um ein neues untergeordnetes MDI-Formular zu erstellen, wenn der Benutzer auf das **neue** Menü Element klickt.

   > [!NOTE]
   > Im folgenden Beispiel verarbeitet der Ereignishandler das <xref:System.Windows.Forms.Control.Click>-Ereignis für `MenuItem2`. Beachten Sie, dass das **neue** Menü Element abhängig von den Besonderheiten ihrer Anwendungsarchitektur möglicherweise nicht ist `MenuItem2` .

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

   Fügen Sie in C++ `#include` am Anfang von Form1. h die folgende Direktive hinzu:

   ```cpp
   #include "Form2.h"
   ```

10. Wählen Sie in der Dropdown Liste am oberen Rand des Fensters **Eigenschaften** die Menüleiste aus, die der **Datei** Menüleiste entspricht, und legen Sie die- <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft auf das Fenster fest <xref:System.Windows.Forms.ToolStripMenuItem> .

    Dadurch kann das **Fenster** Menü eine Liste mit geöffneten untergeordneten MDI-Fenstern mit einem Häkchen neben dem aktiven untergeordneten Fenster verwalten.

11. Drücken Sie **F5**, um die Anwendung auszuführen. Wenn Sie im Menü **Datei** die Option **neu** auswählen, können Sie neue untergeordnete MDI-Formulare erstellen, die im **Fenster** Menü Element nachverfolgt werden.

    > [!NOTE]
    > Wenn ein untergeordnetes MDI-Formular eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt und innerhalb eines übergeordneten MDI-Formulars geöffnet wird, das eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt, werden die Menüelemente automatisch zusammengeführt, wenn Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> (und optional die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>) festgelegt haben. Legen Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> -beider <xref:System.Windows.Forms.MainMenu>-Komponenten sowie alle Menüelemente des untergeordneten Formulars auf <xref:System.Windows.Forms.MenuMerge.MergeItems> fest. Legen Sie außerdem die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> so fest, dass die Menüelemente aus beiden Menüs in der gewünschten Reihenfolge angezeigt werden. Bedenken Sie außerdem, dass beim Schließen eines übergeordneten MDI-Formulars jedes untergeordnete MDI-Formular ein Ereignis <xref:System.Windows.Forms.Form.Closing> auslöst, bevor das Ereignis <xref:System.Windows.Forms.Form.Closing> für das übergeordnete MDI-Formular ausgelöst wird. Durch das Abbrechen des <xref:System.Windows.Forms.Form.Closing>-Ereignisses eines untergeordneten MDI-Formulars wird nicht verhindert, dass das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars ausgelöst wird. Allerdings ist das <xref:System.ComponentModel.CancelEventArgs>-Argument für das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars jetzt auf `true` festgelegt. Sie können erzwingen, dass das übergeordnete MDI-Element und alle untergeordneten MDI-Formulare geschlossen werden, indem Sie das <xref:System.ComponentModel.CancelEventArgs>-Argument auf `false` festlegen.

## <a name="see-also"></a>Weitere Informationen

- [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)
- [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements](how-to-determine-the-active-mdi-child.md)
- [Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md)
- [Vorgehensweise: Anordnen von untergeordneten MDI-Formularen](how-to-arrange-mdi-child-forms.md)
