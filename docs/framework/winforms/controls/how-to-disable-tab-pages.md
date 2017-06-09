---
title: "Gewusst wie: Deaktivieren von Registerkarten | Microsoft Docs"
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
  - "Registerkarten, Ausblenden in Formularen"
  - "TabControl-Steuerelement [Windows Forms], Deaktivieren von Seiten"
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Deaktivieren von Registerkarten
Unter Umständen möchten Sie den Zugriff auf Daten beschränken, die innerhalb der Windows Forms\-Anwendung verfügbar sind.  Wenn beispielsweise Daten in den Registerkarten von einem Registersteuerelement angezeigt werden, können Sie Administratoren den Zugriff auf Informationen einer Registerkarte ermöglichen, während Gäste oder Benutzer mit eingeschränkten Rechten keinen Zugriff darauf haben.  
  
### So deaktivieren Sie Registerkarten programmgesteuert  
  
1.  Schreiben Sie Code, um das <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>\-Ereignis des Tab\-Steuerelements zu behandeln.  Dieses Ereignis wird ausgelöst, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.  
  
2.  Überprüfen Sie die Anmeldeinformationen.  Entsprechend den angegebenen Informationen können Sie den Benutzernamen, unter dem sich der Benutzer angemeldet hat, bzw. andere Anmeldeinformationen überprüfen, bevor Sie dem Benutzer das Anzeigen der Registerkarte gestatten.  
  
3.  Wenn der Benutzer über die entsprechenden Anmeldeinformationen verfügt, zeigen Sie die Registerkarte an, auf die geklickt wurde.  Wenn der Benutzer nicht über die erforderlichen Anmeldeinformationen verfügt, zeigen Sie ein Meldungsfeld oder eine andere Benutzeroberfläche an, um darauf hinzuweisen, dass die erforderlichen Zugriffsrechte nicht vorhanden sind. Kehren Sie anschließend zur ersten Registerkarte zurück.  
  
    > [!NOTE]
    >  Wenn Sie diese Funktionalität in Produktionsanwendungen implementieren, können Sie die Überprüfung der Anmeldeinformationen während des <xref:System.Windows.Forms.Form.Load>\-Ereignisses des Formulars durchführen.  Dies ermöglicht es Ihnen, die Registerkarte vor dem Anzeigen einer beliebigen Benutzeroberfläche auszublenden und damit eine äußerst saubere Programmierung durchzuführen.  Die im Folgenden verwendete Methodik \(Überprüfen von Anmeldeinformationen und Deaktivieren der Registerkarte während des <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>\-Ereignisses\) dient zur Veranschaulichung.  
  
4.  Wenn es sich um mehr als zwei Registerkarten handelt, zeigen Sie optional eine von der ursprünglichen Registerkarte abweichende Registerkarte an.  
  
     Im folgenden Beispiel wird anstelle der Überprüfung der Anmeldeinformationen ein <xref:System.Windows.Forms.CheckBox>\-Steuerelement verwendet, da die Kriterien für den Zugriff auf die Registerkarte je nach Anwendung variieren.  Wenn die Überprüfung der Anmeldeinformationen bei Auslösung des <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>\-Ereignisses true zurückgibt \(d. h., das Kontrollkästchen aktiviert ist\) und die ausgewählte Registerkarte `TabPage2` ist \(in diesem Beispiel die Registerkarte mit den vertraulichen Informationen\), wird `TabPage2` angezeigt.  Andernfalls wird `TabPage3` angezeigt. Die Benutzer sehen ein Meldungsfeld, das darauf hinweist, dass sie nicht über die erforderlichen Zugriffsrechte verfügen.  Im folgenden Code wird ein Formular mit einem <xref:System.Windows.Forms.CheckBox>\-Steuerelement \(`CredentialCheck`\) und einem <xref:System.Windows.Forms.TabControl>\-Steuerelement mit drei Registerkarten vorausgesetzt.  
  
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
  
     \(Visual C\#, Visual C\+\+\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## Siehe auch  
 [Übersicht über das TabControl\-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)   
 [Gewusst wie: Ändern der Darstellung der TabControl\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)