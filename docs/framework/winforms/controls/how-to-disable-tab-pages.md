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
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="cb3d0-102">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="cb3d0-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="cb3d0-103">In einigen Fällen möchten Sie den Zugriff auf Daten einschränken, die in Ihrer Windows Forms-Anwendung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="cb3d0-104">Ein Beispiel hierfür könnte sein, wenn Daten auf den Registerkarten eines Registerkartensteuerelements angezeigt werden. Administratoren können Informationen auf einer Registerkarte verwenden, die Sie von Gastbenutzern oder Benutzern auf niedrigerer Ebene einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="cb3d0-105">So deaktivieren Sie Registerkarten programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="cb3d0-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="cb3d0-106">Schreiben Sie Code, um <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> das Ereignis des Registerkartensteuerelements zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="cb3d0-107">Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="cb3d0-108">Überprüfen Sie die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-108">Check credentials.</span></span> <span data-ttu-id="cb3d0-109">Abhängig von den dargestellten Informationen können Sie den Benutzernamen überprüfen, mit dem sich der Benutzer angemeldet hat, oder eine andere Form von Anmeldeinformationen, bevor Sie dem Benutzer erlauben, die Registerkarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="cb3d0-110">Wenn der Benutzer über die entsprechenden Anmeldeinformationen verfügt, zeigen Sie die Registerkarte an, auf die geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="cb3d0-111">Wenn der Benutzer nicht über die entsprechenden Anmeldeinformationen verfügt, zeigen Sie ein Meldungsfeld oder eine andere Benutzeroberfläche an, die angibt, dass er keinen Zugriff hat, und kehren Sie zur ursprünglichen Registerkarte zurück.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cb3d0-112">Wenn Sie diese Funktionalität in Ihren Produktionsanwendungen implementieren, können Sie <xref:System.Windows.Forms.Form.Load> diese Anmeldeinformationsprüfung während des Formularereignisses durchführen.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="cb3d0-113">Auf diese Weise können Sie die Registerkarte ausblenden, bevor eine Benutzeroberfläche angezeigt wird, was ein viel saubererer Ansatz für die Programmierung ist.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="cb3d0-114">Die unten verwendete Methode (Überprüfen von Anmeldeinformationen <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> und Deaktivieren der Registerkarte während der Veranstaltung) dient zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="cb3d0-115">Wenn Sie mehr als zwei Registerkarten haben, zeigen Sie optional eine Andere Registerkarte als das Original an.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="cb3d0-116">Im folgenden Beispiel <xref:System.Windows.Forms.CheckBox> wird anstelle der Überprüfung der Anmeldeinformationen ein Steuerelement verwendet, da die Kriterien für den Zugriff auf die Registerkarte je nach Anwendung variieren.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="cb3d0-117">Wenn <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> das Ereignis ausgelöst wird, wenn die Anmeldeinformationsprüfung wahr ist (d. h., das Kontrollkästchen aktiviert ist) und die ausgewählte Registerkarte `TabPage2` (die Registerkarte mit den vertraulichen Informationen in diesem Beispiel) angezeigt `TabPage2` wird.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="cb3d0-118">Andernfalls `TabPage3` wird ein Meldungsfeld angezeigt, das dem Benutzer angibt, dass er nicht über die entsprechenden Zugriffsberechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="cb3d0-119">Der folgende Code setzt <xref:System.Windows.Forms.CheckBox> ein`CredentialCheck`Formular mit <xref:System.Windows.Forms.TabControl> einem Steuerelement ( ) und einem Steuerelement mit drei Registerkarten voraus.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="cb3d0-120">(Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="cb3d0-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cb3d0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb3d0-121">See also</span></span>

- [<span data-ttu-id="cb3d0-122">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cb3d0-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="cb3d0-123">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="cb3d0-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="cb3d0-124">Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb3d0-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="cb3d0-125">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb3d0-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
