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
ms.openlocfilehash: 21592fdd74c43d40310e0fcbc96af6565a42e08b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336069"
---
# <a name="how-to-disable-tab-pages"></a>Vorgehensweise: Deaktivieren von Registerkartenseiten
In einigen Fällen möchten Sie den Zugriff auf Daten zu beschränken, die in der Windows Forms-Anwendung verfügbar ist. Ein Beispiel hierfür kann sein, wenn Sie auf den Registerkartenseiten des ein Registerkarten-Steuerelement angezeigte Daten verfügen; Administratoren können Informationen zu einer Registerkarte haben, die Sie aus dem Gast oder Low-Level-Benutzer zu beschränken möchten.  
  
### <a name="to-disable-tab-pages-programmatically"></a>So deaktivieren Sie die Registerkarten programmgesteuert  
  
1. Schreiben von Code zum Behandeln des Registerkarten-Steuerelements <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis. Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.  
  
2. Überprüfen Sie die Anmeldeinformationen. Abhängig von den angezeigten Informationen, sollten Sie den Benutzernamen ein, die, dem der Benutzer angemeldet hat, oder eine andere Art von Anmeldeinformationen überprüfen, bevor der Benutzer auf die Registerkarte anzuzeigen.  
  
3. Wenn der Benutzer die entsprechende Anmeldeinformationen verfügt, zeigen Sie die Registerkarte, auf die geklickt wurde. Wenn der Benutzer nicht über die entsprechende Anmeldeinformationen verfügt, ein Meldungsfenster anzeigt, oder eine andere Benutzeroberfläche zeigt an, dass sie nicht zugreifen, und die erste Registerkarte.  
  
    > [!NOTE]
    >  Wenn Sie diese Funktionalität in Ihre Produktionsanwendungen implementieren, können Sie diese Überprüfung von Anmeldeinformationen ausführen, während des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis. Dadurch können Sie auf die Registerkarte ausgeblendet werden soll, bevor eine Benutzeroberfläche angezeigt wird, ist eine äußerst saubere Programmierung. Die Methodik unten (Überprüfen von Anmeldeinformationen, und deaktivieren die Registerkarte ", während die <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis) Dient zur Veranschaulichung.  
  
4. Optional, wenn Sie mehr als zwei Registerkarten verfügen, eine Registerkarte, die sich von der ursprünglichen angezeigt.  
  
     Im folgenden Beispiel wird eine <xref:System.Windows.Forms.CheckBox> Steuerelement wird verwendet, anstelle der Überprüfung von Anmeldeinformationen für das Konto als Kriterium für den Zugriff auf die Registerkarte nach Anwendung variieren. Wenn die <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> -Ereignis wird ausgelöst, wenn die Überprüfung der Anmeldeinformationen auf "true" festgelegt ist (d. h. Sie dieses Kontrollkästchen ist aktiviert) und die ausgewählte Registerkarte `TabPage2` (die Registerkarte mit den vertraulichen Informationen in diesem Beispiel), klicken Sie dann `TabPage2` wird angezeigt. Andernfalls `TabPage3` wird angezeigt, und ein Meldungsfeld wird angezeigt, für den Benutzer, der angibt, es keine entsprechenden Zugriffsberechtigungen. Im folgenden Code wird ein Formular mit einem <xref:System.Windows.Forms.CheckBox> Control (`CredentialCheck`) und ein <xref:System.Windows.Forms.TabControl> Steuerelement mit drei Registerkarten.  
  
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
  
     (Visual C#, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
- [Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte](how-to-add-a-control-to-a-tab-page.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Vorgehensweise: Ändern der Darstellung der TabControl-Komponente in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
