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
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="7ff7e-102">Vorgehensweise: Deaktivieren von Registerkartenseiten</span><span class="sxs-lookup"><span data-stu-id="7ff7e-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="7ff7e-103">In manchen Fällen möchten Sie den Zugriff auf Daten einschränken, die in Ihrer Windows Forms Anwendung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="7ff7e-104">Ein Beispiel hierfür ist, wenn auf den Registerkarten Seiten eines Registerkarten-Steuer Elements Daten angezeigt werden. Administratoren könnten Informationen auf einer Registerkarte haben, die Sie von Gast-oder unterebenendbenutzern einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="7ff7e-105">So deaktivieren Sie Registerkarten Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="7ff7e-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="7ff7e-106">Schreiben Sie Code zur Behandlung des-Ereignisses <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> des Registerkarten-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="7ff7e-107">Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="7ff7e-108">Anmelde Informationen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-108">Check credentials.</span></span> <span data-ttu-id="7ff7e-109">Abhängig von den dargestellten Informationen können Sie den Benutzernamen, mit dem sich der Benutzer angemeldet hat, oder eine andere Form von Anmelde Informationen überprüfen, bevor Sie dem Benutzer gestatten, die Registerkarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="7ff7e-110">Wenn der Benutzer über die entsprechenden Anmelde Informationen verfügt, zeigen Sie die Registerkarte an</span><span class="sxs-lookup"><span data-stu-id="7ff7e-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="7ff7e-111">Wenn der Benutzer nicht über die entsprechenden Anmelde Informationen verfügt, zeigen Sie ein Meldungs Feld oder eine andere Benutzeroberfläche an, die darauf hinweist, dass Sie keinen Zugriff haben, und kehren Sie zur ursprünglichen Registerkarte zurück.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7ff7e-112">Wenn Sie diese Funktionalität in ihren Produktionsanwendungen implementieren, können Sie diese Überprüfung der Anmelde Informationen während des <xref:System.Windows.Forms.Form.Load> Ereignisses des Formulars durchführen.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="7ff7e-113">Auf diese Weise können Sie die Registerkarte ausblenden, bevor eine Benutzeroberfläche angezeigt wird. Dies ist ein viel saubererer Ansatz für die Programmierung.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="7ff7e-114">Die unten verwendete Methodik (Überprüfen der Anmelde Informationen und Deaktivieren der Register <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Karte während des Ereignisses) dient zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="7ff7e-115">Wenn Sie über mehr als zwei Registerkarten verfügen, können Sie optional eine Registerkarte anzeigen, die sich von der ursprünglichen Seite unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="7ff7e-116">Im folgenden Beispiel wird ein <xref:System.Windows.Forms.CheckBox> -Steuerelement anstelle der Überprüfung der Anmelde Informationen verwendet, da die Kriterien für den Zugriff auf die Registerkarte je nach Anwendung variieren.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="7ff7e-117">Wenn das- `TabPage2` `TabPage2` Ereignis ausgelöst wird, wenn die Überprüfung der Anmelde Informationen true ist (das heißt, das Kontrollkästchen ist aktiviert), und die ausgewählte Registerkarte (in diesem Beispiel die Registerkarte mit den vertraulichen Informationen) angezeigt wird, wird angezeigt. <xref:System.Windows.Forms.TabControl.SelectedIndexChanged></span><span class="sxs-lookup"><span data-stu-id="7ff7e-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="7ff7e-118">`TabPage3` Andernfalls wird angezeigt, und dem Benutzer wird ein Meldungs Feld angezeigt, das angibt, dass Sie nicht über die entsprechenden Zugriffsberechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="7ff7e-119">Der folgende Code nimmt ein Formular mit einem <xref:System.Windows.Forms.CheckBox> -Steuer`CredentialCheck`Element () <xref:System.Windows.Forms.TabControl> und einem-Steuerelement mit drei Registerkarten Seiten an.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="7ff7e-120">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7ff7e-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ff7e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ff7e-121">See also</span></span>

- [<span data-ttu-id="7ff7e-122">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7ff7e-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="7ff7e-123">Vorgehensweise: Hinzufügen eines Steuer Elements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="7ff7e-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="7ff7e-124">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ff7e-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="7ff7e-125">Vorgehensweise: Ändern des Erscheinungs Bilds der Windows Forms TabControl</span><span class="sxs-lookup"><span data-stu-id="7ff7e-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
