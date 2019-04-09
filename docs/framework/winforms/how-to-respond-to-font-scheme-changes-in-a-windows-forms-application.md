---
title: 'Vorgehensweise: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 85770687ecfad690a251eafec9051c4c20f45dd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182103"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="51b12-102">Vorgehensweise: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="51b12-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="51b12-103">In der Windows-Betriebssystemen kann ein Benutzer die systemweite schriftarteinstellungen, um die Standardschriftart angezeigt werden, vergrößert oder verkleinert werden ändern.</span><span class="sxs-lookup"><span data-stu-id="51b12-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="51b12-104">Ändern der schriftarteinstellungen ist wichtig für Benutzer, die sehbehinderte und größeren Typ zum Lesen des Texts auf ihren Bildschirmen erfordern.</span><span class="sxs-lookup"><span data-stu-id="51b12-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="51b12-105">Sie können Ihre Windows Forms-Anwendung, um diese Änderungen zu reagieren durch erhöhen oder verringern die Größe des Formulars und alle darin enthaltenen Text ein, wenn des Schriftartenschemas Änderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="51b12-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="51b12-106">Wenn Sie das Formular aus, um Änderungen in Schriftgrade Ihren Bedürfnissen entsprechend dynamisch zu berücksichtigen möchten, können Sie Code zum Formular hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="51b12-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="51b12-107">In der Regel ist die Standardschriftart, die von Windows Forms verwendet die Schriftart, die zurückgegeben werden, indem die <xref:Microsoft.Win32> Namespace beim Aufrufen von `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="51b12-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="51b12-108">Die Schriftart, die durch diesen Aufruf zurückgegeben wird nur geändert, wenn die Bildschirmauflösung ändert.</span><span class="sxs-lookup"><span data-stu-id="51b12-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="51b12-109">Wie im folgenden Verfahren dargestellt wird, muss den Code der Standardschriftart ändern <xref:System.Drawing.SystemFonts.IconTitleFont%2A> Reaktion auf Änderungen in der Schriftgrad.</span><span class="sxs-lookup"><span data-stu-id="51b12-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="51b12-110">Verwenden Sie die desktop-Schriftart und reagieren auf Änderungen des Schriftartenschemas</span><span class="sxs-lookup"><span data-stu-id="51b12-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="51b12-111">Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="51b12-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="51b12-112">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eine Windows Forms-Anwendung über die Befehlszeile](how-to-create-a-windows-forms-application-from-the-command-line.md) und [in Windows Forms-Steuerelemente](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="51b12-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="51b12-113">Hinzufügen eines Verweises auf die <xref:Microsoft.Win32> Namespace in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="51b12-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="51b12-114">Fügen Sie den folgenden Code, an den Konstruktor des Formulars, um die erforderlichen Ereignishandler einzubinden und so ändern Sie die Standardschriftart für das Formular verwendet.</span><span class="sxs-lookup"><span data-stu-id="51b12-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="51b12-115">Implementieren Sie einen Handler für die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignis, das bewirkt, das Formular dass für die automatische Skalierung bei der <xref:Microsoft.Win32.UserPreferenceCategory.Window> Kategorie Änderungen.</span><span class="sxs-lookup"><span data-stu-id="51b12-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="51b12-116">Abschließend implementieren Sie einen Handler für die <xref:System.Windows.Forms.Form.FormClosing> -Ereignis, das trennt die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="51b12-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="51b12-117">Wird dieser Code eingefügt wird Ihre Anwendung für die Speicherverluste verursachen.</span><span class="sxs-lookup"><span data-stu-id="51b12-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  <span data-ttu-id="51b12-118">Kompilieren Sie den Code, und führen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="51b12-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="51b12-119">So ändern Sie manuell das Schriftartschema in Windows XP</span><span class="sxs-lookup"><span data-stu-id="51b12-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="51b12-120">Während die Windows Forms-Anwendung ausgeführt wird, mit der rechten Maustaste in des Windows-Desktops, und wählen Sie **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="51b12-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="51b12-121">In der **Anzeigeeigenschaften** Dialogfeld klicken Sie auf die **Darstellung** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="51b12-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="51b12-122">Von der **Schriftgrad** Dropdown-Liste wählen eine andere Schriftgröße.</span><span class="sxs-lookup"><span data-stu-id="51b12-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="51b12-123">Sie werden feststellen, dass das Formular jetzt auf Laufzeit-Änderungen in der desktop Schriftartenschemas reagiert.</span><span class="sxs-lookup"><span data-stu-id="51b12-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="51b12-124">Wenn der Benutzer ändert zwischen **Normal**, **großen Schriftarten**, und **Extragroß**, das Formular die Schriftart und ordnungsgemäß skaliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="51b12-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51b12-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51b12-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="51b12-126">Der Konstruktor in diesem Codebeispiel enthält einen Aufruf von `InitializeComponent`, die definiert, wenn Sie ein neues Windows Forms-Projekt in Visual Studio erstellen.</span><span class="sxs-lookup"><span data-stu-id="51b12-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="51b12-127">Entfernen Sie diese Codezeile aus, wenn Sie Ihre Anwendung in der Befehlszeile erstellen.</span><span class="sxs-lookup"><span data-stu-id="51b12-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b12-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51b12-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="51b12-129">Automatische Skalierung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51b12-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
