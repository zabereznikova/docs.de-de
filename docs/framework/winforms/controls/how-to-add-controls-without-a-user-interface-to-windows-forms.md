---
title: 'Vorgehensweise: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330102"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="b7f1d-102">Vorgehensweise: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f1d-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="b7f1d-103">Ein nicht visuelles Steuerelement (oder Komponente) bietet Funktionen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="b7f1d-104">Im Gegensatz zu anderen Steuerelementen Komponenten bieten eine Benutzeroberfläche für dem Benutzer nicht und müssen somit auch nicht auf der Windows Forms-Designer-Oberfläche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="b7f1d-105">Wenn eine Komponente zu einem Formular hinzugefügt wird, zeigt der Windows Forms-Designer ein veränderbarer am unteren Rand der Form, in dem alle Komponenten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="b7f1d-106">Nach einem Steuerelement der Komponentenleiste hinzugefügt wurde, können Sie wählen die Komponente aus und legen Sie seine Eigenschaften fest, wie jedes andere Steuerelement im Formular.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7f1d-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b7f1d-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b7f1d-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b7f1d-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="b7f1d-110">Hinzufügen eine Komponente zu einem Windows-Formular</span><span class="sxs-lookup"><span data-stu-id="b7f1d-110">To add a component to a Windows Form</span></span>  
  
1. <span data-ttu-id="b7f1d-111">Öffnen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-111">Open the form.</span></span> <span data-ttu-id="b7f1d-112">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b7f1d-112">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="b7f1d-113">In der **Toolbox**, klicken Sie auf eine Komponente, und ziehen Sie es in Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="b7f1d-114">Die Komponente wird auf der Komponentenleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="b7f1d-115">Darüber hinaus können Komponenten zu einem Formular zur Laufzeit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="b7f1d-116">Dies ist ein häufiges Szenario, insbesondere deshalb, weil Komponenten keine visuellen Ausdruck im Gegensatz zu Steuerelementen haben, die eine Benutzeroberfläche verfügen.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="b7f1d-117">Im folgenden Beispiel wird eine <xref:System.Windows.Forms.Timer> Komponente wird zur Laufzeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="b7f1d-118">(Beachten Sie, dass Visual Studio eine Reihe von verschiedenen Zeitgeber enthält; in diesem Fall verwenden Sie ein Windows Forms <xref:System.Windows.Forms.Timer> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="b7f1d-119">Weitere Informationen zu den verschiedenen Zeitgeber in Visual Studio, finden Sie unter [Einführung in serverbasierte Timer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="b7f1d-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b7f1d-120">Komponenten haben häufig steuerelementspezifischen Eigenschaften, die für die Komponente effektive Funktionsweise festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="b7f1d-121">Im Fall von der <xref:System.Windows.Forms.Timer> folgenden Komponenten, Sie legen die `Interval` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="b7f1d-122">Achten Sie darauf, wenn Komponenten zu Ihrem Projekt hinzufügen, die die Eigenschaften für die jeweilige Komponente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="b7f1d-123">Programmgesteuertes Hinzufügen eine Komponente zu einem Windows-Formular</span><span class="sxs-lookup"><span data-stu-id="b7f1d-123">To add a component to a Windows Form programmatically</span></span>  
  
1. <span data-ttu-id="b7f1d-124">Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.Timer> Klasse im Code.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2. <span data-ttu-id="b7f1d-125">Legen Sie die `Interval` Eigenschaft, um die Zeit zwischen den Ticks des Zeitgebers zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3. <span data-ttu-id="b7f1d-126">Konfigurieren Sie alle anderen erforderlichen Eigenschaften für die Komponente an.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="b7f1d-127">Der folgende Code zeigt die Erstellung einer <xref:System.Windows.Forms.Timer> mit seiner `Interval` Eigenschaftensatz.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b7f1d-128">Sie können Ihrem lokalen Computer über das Netzwerk ein Sicherheitsrisiko durch Verweisen auf eine böswillige UserControl verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="b7f1d-129">Dies wäre nur ein Problem, wenn ein böswilliger Benutzer erstellt ein schädliches benutzerdefiniertes Steuerelement, indem Sie versehentlich zu Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f1d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7f1d-130">See also</span></span>

- [<span data-ttu-id="b7f1d-131">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b7f1d-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="b7f1d-132">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f1d-132">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="b7f1d-133">Vorgehensweise: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f1d-133">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="b7f1d-134">Vorgehensweise: Kopieren von Steuerelementen zwischen Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f1d-134">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="b7f1d-135">Einfügen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f1d-135">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="b7f1d-136">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="b7f1d-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="b7f1d-137">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f1d-137">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="b7f1d-138">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="b7f1d-138">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
