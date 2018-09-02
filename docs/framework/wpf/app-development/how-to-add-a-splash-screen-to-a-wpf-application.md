---
title: 'Gewusst wie: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 46efa041736870c5c0f08baa321ef0dc53cacc0d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402925"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="64b1b-102">Gewusst wie: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="64b1b-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="64b1b-103">In diesem Thema wird gezeigt, wie einem Startfenster hinzufügen oder *Begrüßungsbildschirm*, an eine Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="64b1b-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="64b1b-104">So fügen Sie ein vorhandenes Image als eines Begrüßungsbildschirms hinzu</span><span class="sxs-lookup"><span data-stu-id="64b1b-104">To add an existing image as a splash screen</span></span>

1.  <span data-ttu-id="64b1b-105">Erstellen Sie oder suchen Sie ein Bild, das Sie für den Begrüßungsbildschirm verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="64b1b-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="64b1b-106">Sie können jedes Bildformat verwenden, die von der Windows Imaging Component (WIC) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="64b1b-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="64b1b-107">Beispielsweise können Sie die BMP, GIF, JPEG, PNG und TIFF-Format verwenden.</span><span class="sxs-lookup"><span data-stu-id="64b1b-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2.  <span data-ttu-id="64b1b-108">Fügen Sie die Imagedatei dem Projekt WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="64b1b-108">Add the image file to the WPF Application project.</span></span>

3.  <span data-ttu-id="64b1b-109">In **Projektmappen-Explorer**, wählen Sie das Image.</span><span class="sxs-lookup"><span data-stu-id="64b1b-109">In **Solution Explorer**, select the image.</span></span>

4.  <span data-ttu-id="64b1b-110">Klicken Sie im Eigenschaftenfenster auf die Dropdown-Pfeil für die **Buildvorgang** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="64b1b-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5.  <span data-ttu-id="64b1b-111">Wählen Sie **SplashScreen** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="64b1b-111">Select **SplashScreen** from the drop-down list.</span></span>

6.  <span data-ttu-id="64b1b-112">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="64b1b-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="64b1b-113">Das Image des Begrüßungsbildschirms wird in der Mitte des Bildschirms, und klicken Sie dann ausgeblendet wird, wenn das Hauptanwendungsfenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="64b1b-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="64b1b-114">Den Begrüßungsbildschirm aus Build ausschließen</span><span class="sxs-lookup"><span data-stu-id="64b1b-114">To exclude the splash screen from build</span></span>

1.  <span data-ttu-id="64b1b-115">In **Projektmappen-Explorer**, wählen Sie das Image des Begrüßungsbildschirms.</span><span class="sxs-lookup"><span data-stu-id="64b1b-115">In **Solution Explorer**, select the splash screen image.</span></span>

2.  <span data-ttu-id="64b1b-116">In der **Eigenschaften** legen die **Buildvorgang** zu **keine**.</span><span class="sxs-lookup"><span data-stu-id="64b1b-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="64b1b-117">So entfernen Sie den Begrüßungsbildschirm von einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="64b1b-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="64b1b-118">In **Projektmappen-Explorer**, löschen Sie das Image des Begrüßungsbildschirms.</span><span class="sxs-lookup"><span data-stu-id="64b1b-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="64b1b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64b1b-119">See Also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="64b1b-120">[Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64b1b-120">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
