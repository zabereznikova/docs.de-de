---
title: 'Vorgehensweise: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms'
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
ms.openlocfilehash: f2a086cc25eb6996b2643742a887bccf481916d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337057"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="a077f-102">Vorgehensweise: Zuordnen eines Kontextmenüs zu einer NotifyIcon-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a077f-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="a077f-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="a077f-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a077f-104">Die <xref:System.Windows.Forms.NotifyIcon> Komponente zeigt ein Symbol im Statusbereich der Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="a077f-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="a077f-105">In der Regel können Anwendungen mit der rechten Maustaste dieses Symbol, um Befehle an die Anwendung zu senden, den es darstellt.</span><span class="sxs-lookup"><span data-stu-id="a077f-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="a077f-106">Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenu> Komponente mit dem die <xref:System.Windows.Forms.NotifyIcon> Komponente ist, können Sie diese Funktionalität zu Ihren Anwendungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a077f-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a077f-107">Wenn Sie Ihre Anwendung beim Start minimiert werden, beim Anzeigen einer Instanz von möchten der <xref:System.Windows.Forms.NotifyIcon> Komponentensatz in der Taskleiste des Hauptformulars <xref:System.Windows.Forms.Form.WindowState%2A> Eigenschaft, um <xref:System.Windows.Forms.FormWindowState.Minimized> und achten Sie darauf die <xref:System.Windows.Forms.NotifyIcon> Komponente <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaft nastaven NA hodnotu `true`.</span><span class="sxs-lookup"><span data-stu-id="a077f-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="a077f-108">Zum Zuordnen eines Kontextmenüs mit der NotifyIcon-Komponente zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="a077f-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="a077f-109">Hinzufügen einer <xref:System.Windows.Forms.NotifyIcon> -Komponente zum Formular, und legen Sie die wichtigen Eigenschaften, z. B. die <xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a077f-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="a077f-110">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der Windows Forms NotifyIcon-Komponente](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="a077f-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="a077f-111">Hinzufügen einer <xref:System.Windows.Forms.ContextMenu> Ihrem Windows-Formular.</span><span class="sxs-lookup"><span data-stu-id="a077f-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="a077f-112">Hinzufügen von Menüelementen, die im Kontextmenü die Befehle, die zur Laufzeit zur Verfügung stellen möchten darstellt.</span><span class="sxs-lookup"><span data-stu-id="a077f-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="a077f-113">Dies ist auch ein guter Zeitpunkt, zu diesen Menüelementen wie den Zugriffsschlüssel im Menü-Erweiterungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a077f-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="a077f-114">Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente dem Kontextmenü aus, die Sie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a077f-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="a077f-115">Diese Eigenschaft festgelegt ist wird das Kontextmenü angezeigt, wenn das Symbol auf der Taskleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="a077f-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="a077f-116">Um programmgesteuert Zuordnen eines Kontextmenüs mit der NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="a077f-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="a077f-117">Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.NotifyIcon> Klasse und ein <xref:System.Windows.Forms.ContextMenu> Klasse, dabei werden alle eigenschafteneinstellungen für die Anwendung erforderlich sind (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A> Eigenschaften für die <xref:System.Windows.Forms.NotifyIcon> -Komponente, die Menüelemente für die <xref:System.Windows.Forms.ContextMenu> die Komponente).</span><span class="sxs-lookup"><span data-stu-id="a077f-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="a077f-118">Legen Sie die <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> Eigenschaft der <xref:System.Windows.Forms.NotifyIcon> Komponente dem Kontextmenü aus, die Sie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a077f-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="a077f-119">Diese Eigenschaft festgelegt ist wird das Kontextmenü angezeigt, wenn das Symbol auf der Taskleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="a077f-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a077f-120">Im folgenden Codebeispiel wird eine grundlegende Menüstruktur erstellt.</span><span class="sxs-lookup"><span data-stu-id="a077f-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="a077f-121">Sie müssen an die Menüoptionen, mit denen die Anwendung anpassen, die Sie entwickeln.</span><span class="sxs-lookup"><span data-stu-id="a077f-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="a077f-122">Darüber hinaus sollten Sie zum Schreiben von Code zum Behandeln von der <xref:System.Windows.Forms.MenuItem.Click> Ereignisse für diese Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="a077f-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
>  <span data-ttu-id="a077f-123">Sie müssen initialisieren `notifyIcon1` und `contextMenu1,` Dies können Sie dazu die folgenden Anweisungen im Konstruktor des Formulars:</span><span class="sxs-lookup"><span data-stu-id="a077f-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a077f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a077f-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="a077f-125">Vorgehensweise: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a077f-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="a077f-126">NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="a077f-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="a077f-127">Übersicht über die NotifyIcon-Komponente</span><span class="sxs-lookup"><span data-stu-id="a077f-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
