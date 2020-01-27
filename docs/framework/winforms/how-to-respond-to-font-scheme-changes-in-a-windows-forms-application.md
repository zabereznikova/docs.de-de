---
title: Reagieren auf Änderungen an Schriftart Schemas in einer Windows Forms-App
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739224"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="7c249-102">Gewusst wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="7c249-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="7c249-103">In den Windows-Betriebssystemen kann ein Benutzer die systemweiten Schriftart Einstellungen ändern, damit die Standard Schriftart größer oder kleiner erscheint.</span><span class="sxs-lookup"><span data-stu-id="7c249-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="7c249-104">Das Ändern dieser Schriftart Einstellungen ist wichtig für Benutzer, die optisch beeinträchtigt sind und einen größeren Typ benötigen, um den Text auf den Bildschirmen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="7c249-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="7c249-105">Sie können Ihre Windows Forms Anwendung so anpassen, dass Sie auf diese Änderungen reagiert, indem Sie die Größe des Formulars und den gesamten enthaltenen Text erhöhen oder verringern, wenn sich das Schriftart Schema ändert.</span><span class="sxs-lookup"><span data-stu-id="7c249-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="7c249-106">Wenn Sie möchten, dass das Formular Änderungen an den Schriftgrößen dynamisch unternimmt, können Sie dem Formular Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c249-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="7c249-107">In der Regel ist die von Windows Forms verwendete Standard Schriftart die Schriftart, die vom <xref:Microsoft.Win32>-Namespace-Aufruf`GetStockObject(DEFAULT_GUI_FONT)`zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7c249-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="7c249-108">Die von diesem-Rückruf zurückgegebene Schriftart ändert sich nur, wenn sich die Bildschirmauflösung ändert.</span><span class="sxs-lookup"><span data-stu-id="7c249-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="7c249-109">Wie im folgenden Verfahren gezeigt, muss der Code die Standard Schriftart in <xref:System.Drawing.SystemFonts.IconTitleFont%2A> ändern, damit auf Änderungen des Schrift Grads geantwortet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c249-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="7c249-110">So verwenden Sie die Desktop Schriftart und reagieren auf Änderungen am Schriftart Schema</span><span class="sxs-lookup"><span data-stu-id="7c249-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="7c249-111">Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c249-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="7c249-112">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer Windows Forms Anwendung aus der Befehlszeile](how-to-create-a-windows-forms-application-from-the-command-line.md) und Steuer [Elemente, die auf Windows Forms verwendet werden sollen](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7c249-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="7c249-113">Fügen Sie dem Code einen Verweis auf den <xref:Microsoft.Win32>-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c249-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="7c249-114">Fügen Sie dem Konstruktor des Formulars den folgenden Code hinzu, um die erforderlichen Ereignishandler zu verbinden und die für das Formular verwendete Standard Schriftart zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7c249-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="7c249-115">Implementieren Sie einen Handler für das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> Ereignis, das bewirkt, dass das Formular automatisch skaliert wird, wenn die <xref:Microsoft.Win32.UserPreferenceCategory.Window> Kategorie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7c249-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="7c249-116">Implementieren Sie abschließend einen Handler für das <xref:System.Windows.Forms.Form.FormClosing> Ereignis, das den <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>-Ereignishandler trennt.</span><span class="sxs-lookup"><span data-stu-id="7c249-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="7c249-117">Wenn Sie diesen Code nicht einschließen, wird der Arbeitsspeicher von Ihrer Anwendung nicht mehr berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="7c249-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="7c249-118">Kompilieren Sie den Code, und führen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="7c249-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="7c249-119">So ändern Sie das Schriftart Schema in Windows XP manuell</span><span class="sxs-lookup"><span data-stu-id="7c249-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="7c249-120">Wenn die Windows Forms-Anwendung ausgeführt wird, klicken Sie mit der rechten Maustaste auf den Windows-Desktop, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7c249-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="7c249-121">Klicken Sie im Dialogfeld **Anzeigeeigenschaften** **auf die Register** Karte Darstellung.</span><span class="sxs-lookup"><span data-stu-id="7c249-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="7c249-122">Wählen Sie im Dropdown-Listenfeld **Schriftart Größe** einen neuen Schrift Grad aus.</span><span class="sxs-lookup"><span data-stu-id="7c249-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="7c249-123">Sie werden feststellen, dass das Formular nun auf Lauf Zeit Änderungen im Desktop Schriftart Schema reagiert.</span><span class="sxs-lookup"><span data-stu-id="7c249-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="7c249-124">Wenn sich der Benutzer zwischen **normalen**, **großen Schriftarten**und **besonders großen Schriftarten**ändert, ändert sich die Schriftart, und die Skalierung erfolgt ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="7c249-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c249-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c249-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="7c249-126">Der Konstruktor in diesem Codebeispiel enthält einen aufzurufenden `InitializeComponent`, der definiert wird, wenn Sie ein neues Windows Forms-Projekt in Visual Studio erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c249-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="7c249-127">Entfernen Sie diese Codezeile, wenn Sie die Anwendung in der Befehlszeile entwickeln.</span><span class="sxs-lookup"><span data-stu-id="7c249-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c249-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c249-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="7c249-129">Automatische Skalierung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c249-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
