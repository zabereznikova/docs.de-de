---
title: 'Gewusst wie: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 06d6cb7c5a5081d3b6c4979ab50e1caaa726acbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547000"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="647f6-102">Gewusst wie: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="647f6-102">How to: Add a Splash Screen to a WPF Application</span></span>
<span data-ttu-id="647f6-103">In diesem Thema wird gezeigt, wie ein Startfenster hinzufügen oder *Begrüßungsbildschirm*, um eine Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="647f6-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="647f6-104">So fügen Sie einem vorhandenen Image als Begrüßungsbildschirm hinzu</span><span class="sxs-lookup"><span data-stu-id="647f6-104">To add an existing image as a splash screen</span></span>  
  
1.  <span data-ttu-id="647f6-105">Erstellen Sie oder suchen Sie ein Bild, das Sie für den Begrüßungsbildschirm verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="647f6-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="647f6-106">Sie können jedes Bildformat verwenden, die von der Windows Imaging-Komponente (WIC) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="647f6-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="647f6-107">Sie können z. B. BMP, GIF, JPEG, PNG und TIFF-Format verwenden.</span><span class="sxs-lookup"><span data-stu-id="647f6-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>  
  
2.  <span data-ttu-id="647f6-108">Fügen Sie die Abbilddatei der WPF-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="647f6-108">Add the image file to the WPF Application project.</span></span> <span data-ttu-id="647f6-109">Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="647f6-109">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
3.  <span data-ttu-id="647f6-110">Wählen Sie im Projektmappen-Explorer das Abbild aus.</span><span class="sxs-lookup"><span data-stu-id="647f6-110">In Solution Explorer, select the image.</span></span>  
  
4.  <span data-ttu-id="647f6-111">Klicken Sie im Fenster Eigenschaften auf den Dropdownpfeil für die **Buildvorgang** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="647f6-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>  
  
5.  <span data-ttu-id="647f6-112">Wählen Sie **SplashScreen** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="647f6-112">Select **SplashScreen** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="647f6-113">Wenn Sie nicht sehen die **SplashScreen** aktivieren, sollten Sie unbedingt die Verwendung von [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="647f6-113">If you do not see the **SplashScreen** option, be sure to check that you are using [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 or later.</span></span>  
  
6.  <span data-ttu-id="647f6-114">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="647f6-114">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="647f6-115">Splash-Bildschirm wird in der Mitte des Bildschirms, und klicken Sie dann ausgeblendet wird, wenn das Hauptanwendungsfenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="647f6-115">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="647f6-116">So entfernen Sie den Begrüßungsbildschirm aus einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="647f6-116">To remove the splash screen from an application</span></span>  
  
1.  <span data-ttu-id="647f6-117">Wählen Sie im Projektmappen-Explorer die des Begrüßungsbildschirms.</span><span class="sxs-lookup"><span data-stu-id="647f6-117">In Solution Explorer, select the splash screen image.</span></span>  
  
2.  <span data-ttu-id="647f6-118">Legen Sie im Fenster Eigenschaften die **Buildvorgang** auf **keine**.</span><span class="sxs-lookup"><span data-stu-id="647f6-118">In the Properties window, set the **Build Action** to **None**.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="647f6-119">So entfernen Sie den Begrüßungsbildschirm aus einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="647f6-119">To remove the splash screen from an application</span></span>  
  
-   <span data-ttu-id="647f6-120">Löschen Sie im Projektmappen-Explorer die des Begrüßungsbildschirms.</span><span class="sxs-lookup"><span data-stu-id="647f6-120">In Solution Explorer, delete the splash screen image.</span></span>  
  
-   <span data-ttu-id="647f6-121">Schließen Sie das Bild des Begrüßungsbildschirms aus dem Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="647f6-121">Exclude the splash screen image from the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647f6-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="647f6-122">See Also</span></span>  
 <xref:System.Windows.SplashScreen>  
 [<span data-ttu-id="647f6-123">NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt</span><span class="sxs-lookup"><span data-stu-id="647f6-123">NIB:How to: Add Existing Items to a Project</span></span>](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
