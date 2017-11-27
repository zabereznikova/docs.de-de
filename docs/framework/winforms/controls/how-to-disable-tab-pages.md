---
title: 'Gewusst wie: Deaktivieren von Registerkarten'
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
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20674a93459f42a793ddf5f7ee5dffb1fa122d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-tab-pages"></a>Gewusst wie: Deaktivieren von Registerkarten
Unter Umständen möchten Sie den Zugriff auf Daten beschränken, die innerhalb der Windows Forms-Anwendung verfügbar ist. Dazu zählt beispielsweise der möglicherweise auf, wenn Sie in den Registerkarten des Registerkarten-Steuerelement angezeigte Daten haben; Administratoren möglicherweise Informationen über eine Registerkarte, die Sie vom Gastbetriebssystem oder technisch anspruchsvolle Benutzer einschränken möchten, würden.  
  
### <a name="to-disable-tab-pages-programmatically"></a>So deaktivieren Sie Registerkarten programmgesteuert  
  
1.  Schreiben von Code zum Behandeln des Registersteuerelements <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis. Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.  
  
2.  Überprüfen Sie die Anmeldeinformationen. Abhängig von den angezeigten Informationen, sollten Sie den Benutzernamen an, dem der Benutzer angemeldet hat, oder eine andere Art von Anmeldeinformationen überprüfen, bevor der Benutzer auf die Registerkarte "anzeigen.  
  
3.  Wenn der Benutzer die entsprechende Anmeldeinformationen verfügt, zeigen Sie die Registerkarte, auf die geklickt wurde. Wenn der Benutzer nicht über die entsprechende Anmeldeinformationen verfügt, ein Meldungsfeld anzeigen oder eine andere Benutzeroberfläche zeigt an, dass sie keine Zugriffsrechte, und auf der ersten Registerkarte zurück.  
  
    > [!NOTE]
    >  Wenn Sie diese Funktionalität in Ihre Produktionsanwendungen zu implementieren, können Sie diese Überprüfung von Anmeldeinformationen ausführen, während des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis. Dadurch können Sie auf die Registerkarte "ausblenden, bevor der Benutzeroberfläche angezeigt wird, ist eine äußerst saubere Programmierung. Die Methodik unten (Überprüfen von Anmeldeinformationen und Deaktivieren der Registerkarte während der <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis) Dient zur Veranschaulichung.  
  
4.  Optional, wenn Sie über mehr als zwei Registerkarten verfügen, eine Registerkarte, die sich von der ursprünglichen angezeigt.  
  
     Im folgenden Beispiel wird eine <xref:System.Windows.Forms.CheckBox> -Steuerelement wird anstelle der Überprüfung von Anmeldeinformationen für das Konto als Kriterium für den Zugriff auf die Registerkarte je nach Anwendung variieren. Wenn die <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis wird ausgelöst, wenn die Überprüfung der Anmeldeinformationen auf "true" festgelegt ist (d. h. Sie dieses Kontrollkästchen aktiviert ist) und die ausgewählte Registerkarte `TabPage2` (die Registerkarte mit den vertraulichen Informationen in diesem Beispiel), klicken Sie dann `TabPage2` wird angezeigt. Andernfalls `TabPage3` wird angezeigt, und ein Meldungsfeld wird angezeigt, für den Benutzer, der angibt, sie verfügte nicht über ausreichende Zugriffsrechte. Im folgenden Code wird ein Formular mit einem <xref:System.Windows.Forms.CheckBox> Steuerelement (`CredentialCheck`) und ein <xref:System.Windows.Forms.TabControl> -Steuerelement mit drei Registerkarten.  
  
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
  
     (Visual c#, Visual C++) Fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
