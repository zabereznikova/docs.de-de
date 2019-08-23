---
title: 'Vorgehensweise: Deaktivieren von Registerkartenseiten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 888228c28dce591b237be16b6a321afee0105208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967149"
---
# <a name="how-to-disable-tab-pages"></a>Vorgehensweise: Deaktivieren von Registerkartenseiten
In manchen Fällen möchten Sie den Zugriff auf Daten einschränken, die in Ihrer Windows Forms Anwendung verfügbar sind. Ein Beispiel hierfür ist, wenn auf den Registerkarten Seiten eines Registerkarten-Steuer Elements Daten angezeigt werden. Administratoren könnten Informationen auf einer Registerkarte haben, die Sie von Gast-oder unterebenendbenutzern einschränken möchten.  
  
### <a name="to-disable-tab-pages-programmatically"></a>So deaktivieren Sie Registerkarten Programm gesteuert  
  
1. Schreiben Sie Code zur Behandlung des-Ereignisses <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> des Registerkarten-Steuer Elements. Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.  
  
2. Anmelde Informationen überprüfen. Abhängig von den dargestellten Informationen können Sie den Benutzernamen, mit dem sich der Benutzer angemeldet hat, oder eine andere Form von Anmelde Informationen überprüfen, bevor Sie dem Benutzer gestatten, die Registerkarte anzuzeigen.  
  
3. Wenn der Benutzer über die entsprechenden Anmelde Informationen verfügt, zeigen Sie die Registerkarte an Wenn der Benutzer nicht über die entsprechenden Anmelde Informationen verfügt, zeigen Sie ein Meldungs Feld oder eine andere Benutzeroberfläche an, die darauf hinweist, dass Sie keinen Zugriff haben, und kehren Sie zur ursprünglichen Registerkarte zurück.  
  
    > [!NOTE]
    > Wenn Sie diese Funktionalität in ihren Produktionsanwendungen implementieren, können Sie diese Überprüfung der Anmelde Informationen während des <xref:System.Windows.Forms.Form.Load> Ereignisses des Formulars durchführen. Auf diese Weise können Sie die Registerkarte ausblenden, bevor eine Benutzeroberfläche angezeigt wird. Dies ist ein viel saubererer Ansatz für die Programmierung. Die unten verwendete Methodik (Überprüfen der Anmelde Informationen und Deaktivieren der Register <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Karte während des Ereignisses) dient zur Veranschaulichung.  
  
4. Wenn Sie über mehr als zwei Registerkarten verfügen, können Sie optional eine Registerkarte anzeigen, die sich von der ursprünglichen Seite unterscheidet.  
  
     Im folgenden Beispiel wird ein <xref:System.Windows.Forms.CheckBox> -Steuerelement anstelle der Überprüfung der Anmelde Informationen verwendet, da die Kriterien für den Zugriff auf die Registerkarte je nach Anwendung variieren. Wenn das- `TabPage2` `TabPage2` Ereignis ausgelöst wird, wenn die Überprüfung der Anmelde Informationen true ist (das heißt, das Kontrollkästchen ist aktiviert), und die ausgewählte Registerkarte (in diesem Beispiel die Registerkarte mit den vertraulichen Informationen) angezeigt wird, wird angezeigt. <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> `TabPage3` Andernfalls wird angezeigt, und dem Benutzer wird ein Meldungs Feld angezeigt, das angibt, dass Sie nicht über die entsprechenden Zugriffsberechtigungen verfügen. Der folgende Code nimmt ein Formular mit einem <xref:System.Windows.Forms.CheckBox> -Steuer`CredentialCheck`Element () <xref:System.Windows.Forms.TabControl> und einem-Steuerelement mit drei Registerkarten Seiten an.  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das TabControl-Steuerelement](tabcontrol-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen eines Steuer Elements zu einer Registerkarte](how-to-add-a-control-to-a-tab-page.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Vorgehensweise: Ändern des Erscheinungs Bilds der Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
