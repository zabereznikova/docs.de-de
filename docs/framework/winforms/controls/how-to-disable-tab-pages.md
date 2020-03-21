---
title: 'Gewusst wie: Deaktivieren von Registerkarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182170"
---
# <a name="how-to-disable-tab-pages"></a>Gewusst wie: Deaktivieren von Registerkarten
In einigen Fällen möchten Sie den Zugriff auf Daten einschränken, die in Ihrer Windows Forms-Anwendung verfügbar sind. Ein Beispiel hierfür könnte sein, wenn Daten auf den Registerkarten eines Registerkartensteuerelements angezeigt werden. Administratoren können Informationen auf einer Registerkarte verwenden, die Sie von Gastbenutzern oder Benutzern auf niedrigerer Ebene einschränken möchten.  
  
### <a name="to-disable-tab-pages-programmatically"></a>So deaktivieren Sie Registerkarten programmgesteuert  
  
1. Schreiben Sie Code, um <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> das Ereignis des Registerkartensteuerelements zu behandeln. Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.  
  
2. Überprüfen Sie die Anmeldeinformationen. Abhängig von den dargestellten Informationen können Sie den Benutzernamen überprüfen, mit dem sich der Benutzer angemeldet hat, oder eine andere Form von Anmeldeinformationen, bevor Sie dem Benutzer erlauben, die Registerkarte anzuzeigen.  
  
3. Wenn der Benutzer über die entsprechenden Anmeldeinformationen verfügt, zeigen Sie die Registerkarte an, auf die geklickt wurde. Wenn der Benutzer nicht über die entsprechenden Anmeldeinformationen verfügt, zeigen Sie ein Meldungsfeld oder eine andere Benutzeroberfläche an, die angibt, dass er keinen Zugriff hat, und kehren Sie zur ursprünglichen Registerkarte zurück.  
  
    > [!NOTE]
    > Wenn Sie diese Funktionalität in Ihren Produktionsanwendungen implementieren, können Sie <xref:System.Windows.Forms.Form.Load> diese Anmeldeinformationsprüfung während des Formularereignisses durchführen. Auf diese Weise können Sie die Registerkarte ausblenden, bevor eine Benutzeroberfläche angezeigt wird, was ein viel saubererer Ansatz für die Programmierung ist. Die unten verwendete Methode (Überprüfen von Anmeldeinformationen <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> und Deaktivieren der Registerkarte während der Veranstaltung) dient zur Veranschaulichung.  
  
4. Wenn Sie mehr als zwei Registerkarten haben, zeigen Sie optional eine Andere Registerkarte als das Original an.  
  
     Im folgenden Beispiel <xref:System.Windows.Forms.CheckBox> wird anstelle der Überprüfung der Anmeldeinformationen ein Steuerelement verwendet, da die Kriterien für den Zugriff auf die Registerkarte je nach Anwendung variieren. Wenn <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> das Ereignis ausgelöst wird, wenn die Anmeldeinformationsprüfung wahr ist (d. h., das Kontrollkästchen aktiviert ist) und die ausgewählte Registerkarte `TabPage2` (die Registerkarte mit den vertraulichen Informationen in diesem Beispiel) angezeigt `TabPage2` wird. Andernfalls `TabPage3` wird ein Meldungsfeld angezeigt, das dem Benutzer angibt, dass er nicht über die entsprechenden Zugriffsberechtigungen verfügt. Der folgende Code setzt <xref:System.Windows.Forms.CheckBox> ein`CredentialCheck`Formular mit <xref:System.Windows.Forms.TabControl> einem Steuerelement ( ) und einem Steuerelement mit drei Registerkarten voraus.  
  
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
  
     (Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das TabControl-Steuerelement](tabcontrol-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](how-to-add-a-control-to-a-tab-page.md)
- [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
