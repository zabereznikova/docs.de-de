---
title: Hinzufügen von Steuerelementen ohne Benutzeroberfläche
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
ms.openlocfilehash: 43f13b4f009fcd6e5d82fa2c00113a77d48877b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744752"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="dfd6d-102">Gewusst wie: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfd6d-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="dfd6d-103">Ein nicht visuelles Steuerelement (oder eine Komponente) stellt Funktionen für Ihre Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="dfd6d-104">Im Gegensatz zu anderen Steuerelementen bieten Komponenten keine Benutzeroberfläche für den Benutzer und müssen daher nicht auf der Windows Forms-Designer Oberfläche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="dfd6d-105">Wenn eine Komponente zu einem Formular hinzugefügt wird, zeigt der Windows Forms-Designer am unteren Rand des Formulars, in dem alle Komponenten angezeigt werden, eine Größe an, die geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="dfd6d-106">Nachdem ein Steuerelement der Komponenten Leiste hinzugefügt wurde, können Sie die Komponente auswählen und deren Eigenschaften wie jedes andere Steuerelement im Formular festlegen.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="dfd6d-107">Hinzufügen einer Komponente zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="dfd6d-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="dfd6d-108">Öffnen Sie das Formular in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="dfd6d-109">Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="dfd6d-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="dfd6d-110">Klicken Sie in der **Toolbox**auf eine Komponente, und ziehen Sie Sie in das Formular.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="dfd6d-111">Die Komponente wird in der Komponenten Leiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="dfd6d-112">Darüber hinaus können Komponenten zur Laufzeit einem Formular hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="dfd6d-113">Dies ist ein häufiges Szenario, insbesondere, da Komponenten keinen visuellen Ausdruck aufweisen, anders als Steuerelemente mit einer Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="dfd6d-114">Im folgenden Beispiel wird eine <xref:System.Windows.Forms.Timer> Komponente zur Laufzeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="dfd6d-115">(Beachten Sie, dass Visual Studio eine Reihe von unterschiedlichen Timern enthält. verwenden Sie in diesem Fall eine Windows Forms <xref:System.Windows.Forms.Timer> Komponente.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="dfd6d-116">Weitere Informationen zu den verschiedenen Timern in Visual Studio finden [Sie unter Einführung in Server basierte Timer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="dfd6d-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="dfd6d-117">Komponenten verfügen häufig über Steuerungs spezifische Eigenschaften, die für eine effektive Funktionsweise der Komponente festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="dfd6d-118">Im Fall der folgenden <xref:System.Windows.Forms.Timer> Komponente legen Sie die `Interval`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="dfd6d-119">Stellen Sie sicher, dass Sie beim Hinzufügen von Komponenten zu Ihrem Projekt die Eigenschaften festlegen, die für diese Komponente erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="dfd6d-120">Programm gesteuertes Hinzufügen einer Komponente zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="dfd6d-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="dfd6d-121">Erstellen Sie im Code eine Instanz der <xref:System.Windows.Forms.Timer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="dfd6d-122">Legen Sie die `Interval`-Eigenschaft fest, um die Zeit zwischen Ticks des Timers zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="dfd6d-123">Konfigurieren Sie alle anderen erforderlichen Eigenschaften für die Komponente.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="dfd6d-124">Der folgende Code zeigt die Erstellung einer <xref:System.Windows.Forms.Timer>, deren `Interval`-Eigenschaft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

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
    > <span data-ttu-id="dfd6d-125">Sie können den lokalen Computer mit einem Sicherheitsrisiko über das Netzwerk verfügbar machen, indem Sie auf ein schädliches UserControl-Steuerelement verweisen.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="dfd6d-126">Dies wäre nur ein Problem, wenn eine böswillige Person ein schädliches benutzerdefiniertes Steuerelement erstellt, gefolgt von dem, das Sie versehentlich dem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dfd6d-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfd6d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfd6d-127">See also</span></span>

- [<span data-ttu-id="dfd6d-128">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="dfd6d-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="dfd6d-129">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfd6d-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="dfd6d-130">Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfd6d-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="dfd6d-131">Einfügen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfd6d-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="dfd6d-132">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="dfd6d-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="dfd6d-133">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfd6d-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="dfd6d-134">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="dfd6d-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
