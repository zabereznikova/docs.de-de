---
title: 'Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: c7658a3a1c72c3fed4033e644d0dd776b06ee1a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525412"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="71f46-102">Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71f46-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="71f46-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein einzelnes Symbol im Statusbereich der Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="71f46-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="71f46-104">Um mehrere Symbole im Statusbereich anzuzeigen, benötigen Sie mehrere <xref:System.Windows.Forms.NotifyIcon> Komponenten auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="71f46-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="71f46-105">Um das Symbol angezeigt, die für ein Steuerelement festzulegen, verwenden die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="71f46-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="71f46-106">Sie können auch Code schreiben, der <xref:System.Windows.Forms.NotifyIcon.DoubleClick> -Ereignishandler so, dass etwas passiert, wenn der Benutzer auf das Symbol doppelklickt.</span><span class="sxs-lookup"><span data-stu-id="71f46-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="71f46-107">Beispielsweise können Sie ein Dialogfeld für den Benutzer so konfigurieren Sie die im Hintergrund ausgeführten Prozess, dargestellt durch das Symbol angezeigt vornehmen.</span><span class="sxs-lookup"><span data-stu-id="71f46-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71f46-108">Die <xref:System.Windows.Forms.NotifyIcon> Komponente nur aus Gründen der Benachrichtigung verwendet wird, um Benutzer darauf aufmerksam, die eine Aktion oder ein Ereignis aufgetreten ist oder eine Änderung des Status von irgendeine stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="71f46-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="71f46-109">Sie sollten Menüs, Symbolleisten und andere Elemente der Benutzeroberfläche für die standard-Interaktion mit Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="71f46-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="71f46-110">Das Symbol "festlegen</span><span class="sxs-lookup"><span data-stu-id="71f46-110">To set the icon</span></span>  
  
1.  <span data-ttu-id="71f46-111">Weisen Sie einen Wert an die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="71f46-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="71f46-112">Der Wert muss vom Typ `System.Drawing.Icon` und kann aus einer ICO‑Datei geladen werden.</span><span class="sxs-lookup"><span data-stu-id="71f46-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="71f46-113">Sie können die Symboldatei angeben, im Code oder durch Klicken auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben der <xref:System.Windows.Forms.NotifyIcon.Icon%2A> Eigenschaft in der  **Eigenschaften** Fenster, und wählen Sie dann die Datei in die **öffnen** im daraufhin geöffneten Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="71f46-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2.  <span data-ttu-id="71f46-114">Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="71f46-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="71f46-115">Legen Sie die <xref:System.Windows.Forms.NotifyIcon.Text%2A> Eigenschaft, um eine entsprechende QuickInfo-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="71f46-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="71f46-116">Im folgenden Codebeispiel legen der Pfad für der Speicherort des Symbols wird die **eigene** Ordner.</span><span class="sxs-lookup"><span data-stu-id="71f46-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="71f46-117">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner die meisten Computer das Windows-Betriebssystem ausgeführt wird enthält.</span><span class="sxs-lookup"><span data-stu-id="71f46-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="71f46-118">Dieser Speicherort kann auch Benutzer mit minimalen sicher auf die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71f46-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="71f46-119">Das folgende Beispiel erfordert ein Formular mit einem <xref:System.Windows.Forms.NotifyIcon> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="71f46-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="71f46-120">Darüber hinaus müssen eine Symboldatei mit dem Namen `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="71f46-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="71f46-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71f46-121">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="71f46-122">Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71f46-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [<span data-ttu-id="71f46-123">NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="71f46-123">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="71f46-124">Übersicht über die NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="71f46-124">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
