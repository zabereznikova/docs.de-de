---
title: 'Gewusst wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 455609ea602f450803718f5be34618b087560d21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539451"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="81fc3-102">Gewusst wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="81fc3-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="81fc3-103">In den Windows-Betriebssystemen kann ein Benutzer die systemweite schriftarteinstellungen, um die Standardschriftart angezeigt vergrößern oder verkleinern möchten ändern.</span><span class="sxs-lookup"><span data-stu-id="81fc3-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="81fc3-104">Das Ändern dieser schriftarteinstellungen ist wichtig für Benutzer, die Sehbehinderte sind, und größeren Typ zum Lesen des Texts auf ihre Bildschirme benötigen.</span><span class="sxs-lookup"><span data-stu-id="81fc3-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="81fc3-105">Sie können anpassen, dass Ihre Windows Forms-Anwendung, um diese Änderungen, die durch erhöhen oder verringern die Größe des Formulars und alle enthaltenen Text bei jeder Änderung des Schriftartenschemas zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="81fc3-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="81fc3-106">Wenn das Formular, um dynamisch Änderungen in Schriftgrade Ihren Bedürfnissen gerecht zu werden soll, können Sie Code zum Formular hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="81fc3-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="81fc3-107">In der Regel ist die Standardschriftart von Windows Forms verwendet die zurückgegebene Schriftart der <xref:Microsoft.Win32> Namespace beim Aufrufen von `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="81fc3-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="81fc3-108">Die Schriftart, die durch diesen Aufruf zurückgegeben wird nur geändert, wenn sich die Bildschirmauflösung ändert.</span><span class="sxs-lookup"><span data-stu-id="81fc3-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="81fc3-109">Wie in der folgenden Prozedur dargestellt, muss den Code ändern Standardschriftart <xref:System.Drawing.SystemFonts.IconTitleFont%2A> Reaktion auf Änderungen an der Größe der Schriftart.</span><span class="sxs-lookup"><span data-stu-id="81fc3-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="81fc3-110">Verwenden Sie die Remotedesktop-Schriftart und reagieren auf Änderungen des Schriftartenschemas</span><span class="sxs-lookup"><span data-stu-id="81fc3-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="81fc3-111">Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="81fc3-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="81fc3-112">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer Windows Forms-Anwendung über die Befehlszeile](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) und [Steuerelemente für Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="81fc3-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="81fc3-113">Hinzufügen eines Verweises auf die <xref:Microsoft.Win32> Namespace in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="81fc3-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="81fc3-114">Fügen Sie den folgenden Code an den Konstruktor des Formulars erforderlichen Ereignishandler verknüpft und die Standardschriftart verwendet für das Formular zu ändern.</span><span class="sxs-lookup"><span data-stu-id="81fc3-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="81fc3-115">Implementieren Sie einen Handler für die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> Ereignis, das bewirkt, das Formular dass, um automatisch skalieren, wenn die <xref:Microsoft.Win32.UserPreferenceCategory.Window> Kategorie Änderungen.</span><span class="sxs-lookup"><span data-stu-id="81fc3-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="81fc3-116">Implementieren Sie schließlich einen Handler für die <xref:System.Windows.Forms.Form.FormClosing> Ereignis, das trennt die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="81fc3-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81fc3-117">Dieser Code wird die Anwendung zu Speicherverlust führen.</span><span class="sxs-lookup"><span data-stu-id="81fc3-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  <span data-ttu-id="81fc3-118">Kompilieren Sie den Code, und führen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="81fc3-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="81fc3-119">So ändern manuell die Schriftartenschemas in Windows XP</span><span class="sxs-lookup"><span data-stu-id="81fc3-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="81fc3-120">Während die Windows Forms-Anwendung ausgeführt wird, mit der rechten Maustaste in des Windows-Desktops, und wählen Sie **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="81fc3-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="81fc3-121">In der **Anzeigeeigenschaften** (Dialogfeld), klicken Sie auf die **Darstellung** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="81fc3-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="81fc3-122">Aus der **Schriftgrad** Dropdown-Liste wählen eine andere Schriftgröße.</span><span class="sxs-lookup"><span data-stu-id="81fc3-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="81fc3-123">Beachten Sie, dass das Formular jetzt reagiert auf zeitänderungen in der desktop Schriftartenschemas ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="81fc3-123">You will notice that the form now reacts to run time changes in the desktop font scheme.</span></span> <span data-ttu-id="81fc3-124">Wenn der Benutzer zwischen ändert **Normal**, **große Schriftarten**, und **Extragroß**, dem Formular die Schriftart und ordnungsgemäß skaliert.</span><span class="sxs-lookup"><span data-stu-id="81fc3-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81fc3-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81fc3-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="81fc3-126">Der Konstruktor in diesem Codebeispiel enthält einen Aufruf von `InitializeComponent`, also definiert, wenn Sie ein neues Windows Forms-Projekt in Visual Studio erstellen.</span><span class="sxs-lookup"><span data-stu-id="81fc3-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="81fc3-127">Entfernen Sie diese Codezeile aus, wenn Sie Ihre Anwendung in der Befehlszeile erstellen.</span><span class="sxs-lookup"><span data-stu-id="81fc3-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fc3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81fc3-128">See Also</span></span>  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [<span data-ttu-id="81fc3-129">Automatische Skalierung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="81fc3-129">Automatic Scaling in Windows Forms</span></span>](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
