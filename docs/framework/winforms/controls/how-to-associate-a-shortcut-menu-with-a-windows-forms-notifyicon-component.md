---
title: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 392c04f73feaec201033ad76f9419a0e070bec70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742048"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="9bc32-102">Gewusst wie: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9bc32-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="9bc32-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> die-<xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu>-Steuerelemente früherer Versionen ersetzen und Funktionen hinzufügen, werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9bc32-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="9bc32-104">Die <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein Symbol im Status Benachrichtigungsbereich der Taskleiste an.</span><span class="sxs-lookup"><span data-stu-id="9bc32-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="9bc32-105">Häufig können Sie mit der rechten Maustaste auf dieses Symbol klicken, um Befehle an die von ihm dargestellte Anwendung zu senden.</span><span class="sxs-lookup"><span data-stu-id="9bc32-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="9bc32-106">Indem Sie der <xref:System.Windows.Forms.NotifyIcon> Komponente eine <xref:System.Windows.Forms.ContextMenu> Komponente zuordnen, können Sie diese Funktionalität ihren Anwendungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc32-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bc32-107">Wenn Sie möchten, dass Ihre Anwendung beim Start minimiert wird, während eine Instanz der <xref:System.Windows.Forms.NotifyIcon> Komponente in der Taskleiste angezeigt wird, legen Sie die <xref:System.Windows.Forms.Form.WindowState%2A>-Eigenschaft des Haupt Formulars auf <xref:System.Windows.Forms.FormWindowState.Minimized> fest, und stellen Sie sicher, dass die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>-Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente auf `true`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9bc32-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="9bc32-108">So ordnen Sie der NotifyIcon-Komponente zur Entwurfszeit ein Kontextmenü zu</span><span class="sxs-lookup"><span data-stu-id="9bc32-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="9bc32-109">Fügen Sie dem Formular eine <xref:System.Windows.Forms.NotifyIcon> Komponente hinzu, und legen Sie die wichtigen Eigenschaften fest, wie z. b. die Eigenschaften <xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bc32-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="9bc32-110">Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der Windows Forms NotifyIcon-Komponente](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="9bc32-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="9bc32-111">Fügen Sie Ihrem Windows Form eine <xref:System.Windows.Forms.ContextMenu> Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="9bc32-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="9bc32-112">Fügen Sie dem Kontextmenü Menü Elemente hinzu, die die Befehle darstellen, die zur Laufzeit verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9bc32-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="9bc32-113">Dies ist auch ein guter Zeitpunkt, diesen Menü Elementen, z. b. Zugriffstasten, Menü Erweiterungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc32-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="9bc32-114">Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>-Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente auf das Kontextmenü fest, das Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="9bc32-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="9bc32-115">Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn auf das Symbol auf der Taskleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="9bc32-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="9bc32-116">So ordnen Sie der NotifyIcon-Komponente Programm gesteuert ein Kontextmenü zu</span><span class="sxs-lookup"><span data-stu-id="9bc32-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="9bc32-117">Erstellen Sie eine Instanz der <xref:System.Windows.Forms.NotifyIcon>-Klasse und eine <xref:System.Windows.Forms.ContextMenu> Klasse mit den für die Anwendung erforderlichen Eigenschafts Einstellungen (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften für die <xref:System.Windows.Forms.NotifyIcon> Komponente, Menü Elemente für die <xref:System.Windows.Forms.ContextMenu> Komponente).</span><span class="sxs-lookup"><span data-stu-id="9bc32-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="9bc32-118">Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>-Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente auf das Kontextmenü fest, das Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="9bc32-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="9bc32-119">Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn auf das Symbol auf der Taskleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="9bc32-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9bc32-120">Im folgenden Codebeispiel wird eine einfache Menüstruktur erstellt.</span><span class="sxs-lookup"><span data-stu-id="9bc32-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="9bc32-121">Sie müssen die Menü Optionen für die Anwendung anpassen, die Sie entwickeln.</span><span class="sxs-lookup"><span data-stu-id="9bc32-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="9bc32-122">Außerdem sollten Sie Code schreiben, um die <xref:System.Windows.Forms.MenuItem.Click> Ereignisse für diese Menü Elemente zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="9bc32-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> <span data-ttu-id="9bc32-123">Sie müssen `notifyIcon1` initialisieren und `contextMenu1,` können, indem Sie die folgenden Anweisungen in den Konstruktor Ihres Formulars einschließen:</span><span class="sxs-lookup"><span data-stu-id="9bc32-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bc32-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bc32-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="9bc32-125">Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9bc32-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="9bc32-126">NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="9bc32-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="9bc32-127">Übersicht über die NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="9bc32-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
