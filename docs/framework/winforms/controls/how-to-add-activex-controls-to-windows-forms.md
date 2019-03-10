---
title: 'Vorgehensweise: Hinzufügen von ActiveX-Steuerelemente zu Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 68e25cb2cd7e1f1c63954b20d24f028a49431553
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707988"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="d3e8f-102">Vorgehensweise: Hinzufügen von ActiveX-Steuerelemente zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3e8f-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="d3e8f-103">Während der Windows Forms-Designer zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie auch die ActiveX-Steuerelementen in Windows Forms einfügen.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d3e8f-104">Es gibt leistungseinschränkungen für Windows Forms, wenn ActiveX-Steuerelemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="d3e8f-105">Bevor Sie das ActiveX-Steuerelementen zum Formular hinzufügen, müssen Sie sie zur Toolbox hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="d3e8f-106">Weitere Informationen finden Sie unter [COM-Komponenten, Dialogfeld "Toolbox" anpassen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d3e8f-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3e8f-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d3e8f-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d3e8f-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="d3e8f-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="d3e8f-110">Das Windows-Formular ein ActiveX-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="d3e8f-110">To add an ActiveX control to your Windows Form</span></span>  
  
-   <span data-ttu-id="d3e8f-111">Doppelklicken Sie auf das Steuerelement in der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-111">Double-click the control on the Toolbox.</span></span>  
  
     <span data-ttu-id="d3e8f-112">Alle Verweise auf das Steuerelement wird von Visual Studio in Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-112">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="d3e8f-113">Weitere Informationen zu Dinge zu bedenken, wenn ActiveX-Steuerelementen in Windows Forms verwenden, finden Sie unter [Aspekte beim Hosten eines ActiveX-Steuerelements in einem Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="d3e8f-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3e8f-114">Windows Forms ActiveX Control Importer (AxImp.exe) erstellt die Ereignisargumente, die von einem anderen Typ als beim Import von ActiveX-dynamic Link Librarys erwartet.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="d3e8f-115">Die Argumente, die von AxImp.exe erstellt sind ähnlich dem folgenden: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`Wenn `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` wird erwartet.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="d3e8f-116">Denken Sie daran, dass diese Unregelmäßigkeit nicht Code verhindert, Normal zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d3e8f-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="d3e8f-117">Weitere Informationen finden Sie unter [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="d3e8f-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e8f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3e8f-118">See also</span></span>
- [<span data-ttu-id="d3e8f-119">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d3e8f-119">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="d3e8f-120">[In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d3e8f-120">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="d3e8f-121">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3e8f-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="d3e8f-122">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3e8f-122">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="d3e8f-123">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e8f-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="d3e8f-124">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d3e8f-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="d3e8f-125">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="d3e8f-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
