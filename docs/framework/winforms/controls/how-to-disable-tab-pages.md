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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013451"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="b4225-102">Vorgehensweise: Deaktivieren von Registerkartenseiten</span><span class="sxs-lookup"><span data-stu-id="b4225-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="b4225-103">In einigen Fällen möchten Sie den Zugriff auf Daten zu beschränken, die in der Windows Forms-Anwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b4225-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="b4225-104">Ein Beispiel hierfür kann sein, wenn Sie auf den Registerkartenseiten des ein Registerkarten-Steuerelement angezeigte Daten verfügen; Administratoren können Informationen zu einer Registerkarte haben, die Sie aus dem Gast oder Low-Level-Benutzer zu beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="b4225-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="b4225-105">So deaktivieren Sie die Registerkarten programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b4225-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="b4225-106">Schreiben von Code zum Behandeln des Registerkarten-Steuerelements <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b4225-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="b4225-107">Dies ist das Ereignis, das ausgelöst wird, wenn der Benutzer von einer Registerkarte zur nächsten wechselt.</span><span class="sxs-lookup"><span data-stu-id="b4225-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="b4225-108">Überprüfen Sie die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="b4225-108">Check credentials.</span></span> <span data-ttu-id="b4225-109">Abhängig von den angezeigten Informationen, sollten Sie den Benutzernamen ein, die, dem der Benutzer angemeldet hat, oder eine andere Art von Anmeldeinformationen überprüfen, bevor der Benutzer auf die Registerkarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4225-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="b4225-110">Wenn der Benutzer die entsprechende Anmeldeinformationen verfügt, zeigen Sie die Registerkarte, auf die geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="b4225-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="b4225-111">Wenn der Benutzer nicht über die entsprechende Anmeldeinformationen verfügt, ein Meldungsfenster anzeigt, oder eine andere Benutzeroberfläche zeigt an, dass sie nicht zugreifen, und die erste Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="b4225-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4225-112">Wenn Sie diese Funktionalität in Ihre Produktionsanwendungen implementieren, können Sie diese Überprüfung von Anmeldeinformationen ausführen, während des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b4225-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="b4225-113">Dadurch können Sie auf die Registerkarte ausgeblendet werden soll, bevor eine Benutzeroberfläche angezeigt wird, ist eine äußerst saubere Programmierung.</span><span class="sxs-lookup"><span data-stu-id="b4225-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="b4225-114">Die Methodik unten (Überprüfen von Anmeldeinformationen, und deaktivieren die Registerkarte ", während die <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> Ereignis) Dient zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="b4225-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="b4225-115">Optional, wenn Sie mehr als zwei Registerkarten verfügen, eine Registerkarte, die sich von der ursprünglichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4225-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="b4225-116">Im folgenden Beispiel wird eine <xref:System.Windows.Forms.CheckBox> Steuerelement wird verwendet, anstelle der Überprüfung von Anmeldeinformationen für das Konto als Kriterium für den Zugriff auf die Registerkarte nach Anwendung variieren.</span><span class="sxs-lookup"><span data-stu-id="b4225-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="b4225-117">Wenn die <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> -Ereignis wird ausgelöst, wenn die Überprüfung der Anmeldeinformationen auf "true" festgelegt ist (d. h. Sie dieses Kontrollkästchen ist aktiviert) und die ausgewählte Registerkarte `TabPage2` (die Registerkarte mit den vertraulichen Informationen in diesem Beispiel), klicken Sie dann `TabPage2` wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4225-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="b4225-118">Andernfalls `TabPage3` wird angezeigt, und ein Meldungsfeld wird angezeigt, für den Benutzer, der angibt, es keine entsprechenden Zugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b4225-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="b4225-119">Im folgenden Code wird ein Formular mit einem <xref:System.Windows.Forms.CheckBox> Control (`CredentialCheck`) und ein <xref:System.Windows.Forms.TabControl> Steuerelement mit drei Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="b4225-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="b4225-120">(Visual C#, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b4225-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b4225-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4225-121">See also</span></span>

- [<span data-ttu-id="b4225-122">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b4225-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="b4225-123">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="b4225-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="b4225-124">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4225-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="b4225-125">Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4225-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
