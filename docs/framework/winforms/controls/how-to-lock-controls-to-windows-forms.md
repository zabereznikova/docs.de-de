---
title: Sperren von Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 16eb151dc435614e1edc82bf9f0acf3974f36690
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736234"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="072fe-102">Gewusst wie: Sperren von Steuerelementen auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="072fe-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="072fe-103">Wenn Sie die Benutzeroberfläche der Windows-Anwendung entwerfen, können Sie die Steuerelemente nach der ordnungsgemäßen Positionierung sperren, damit Sie Sie nicht versehentlich verschieben oder ändern, wenn Sie andere Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="072fe-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="072fe-104">Darüber hinaus können Sie alle Steuerelemente im Formular auf einmal Sperren und entsperren, was für Formulare mit vielen Steuerelementen hilfreich ist, oder Sie können einzelne Steuerelemente entsperren.</span><span class="sxs-lookup"><span data-stu-id="072fe-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="072fe-105">Nachdem Sie alle Steuerelemente auf dem Formular abgelegt haben, Sperren Sie Sie alle an Ort und Stelle, um eine fehlerhafte Bewegung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="072fe-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="072fe-106">So sperren Sie ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="072fe-106">To lock a control</span></span>

<span data-ttu-id="072fe-107">Wählen Sie im **Eigenschaften** Fenster von Visual Studio die Eigenschaft **gesperrt** aus, und wählen Sie dann **true**aus.</span><span class="sxs-lookup"><span data-stu-id="072fe-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="072fe-108">(Doppelklicken Sie auf den Namen, um die Eigenschafts Einstellung zu wechseln.)</span><span class="sxs-lookup"><span data-stu-id="072fe-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="072fe-109">Klicken Sie alternativ mit der rechten Maustaste auf das Steuerelement, und wählen Sie Steuer **Elemente sperren**</span><span class="sxs-lookup"><span data-stu-id="072fe-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="072fe-110">Sperr Steuerelemente verhindern, dass Sie auf der Entwurfs Oberfläche an eine neue Größe oder Position gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="072fe-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="072fe-111">Sie können jedoch weiterhin die Größe oder Position von Steuerelementen mithilfe des **Eigenschaften** Fensters oder im Code ändern.</span><span class="sxs-lookup"><span data-stu-id="072fe-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="072fe-112">So sperren Sie alle Steuerelemente auf einem Formular</span><span class="sxs-lookup"><span data-stu-id="072fe-112">To lock all the controls on a form</span></span>

<span data-ttu-id="072fe-113">Wählen Sie im Menü **Format** die Option Steuer **Elemente sperren**aus.</span><span class="sxs-lookup"><span data-stu-id="072fe-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="072fe-114">Dieser Befehl sperrt auch die Größe des Formulars, da ein Formular ein Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="072fe-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="072fe-115">So entsperren Sie alle gesperrten Steuerelemente auf einem Formular</span><span class="sxs-lookup"><span data-stu-id="072fe-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="072fe-116">Wählen Sie im Menü **Format** die Option Steuer **Elemente sperren**aus.</span><span class="sxs-lookup"><span data-stu-id="072fe-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="072fe-117">Alle zuvor gesperrten Steuerelemente auf dem Formular sind nun entsperrt.</span><span class="sxs-lookup"><span data-stu-id="072fe-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="072fe-118">So entsperren Sie gesperrte Steuerelemente einzeln</span><span class="sxs-lookup"><span data-stu-id="072fe-118">To unlock locked controls individually</span></span>

<span data-ttu-id="072fe-119">Wählen Sie im Fenster **Eigenschaften** die Eigenschaft **gesperrt** aus, und wählen Sie dann **false**aus.</span><span class="sxs-lookup"><span data-stu-id="072fe-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="072fe-120">(Doppelklicken Sie auf den Namen, um die Eigenschafts Einstellung zu wechseln.)</span><span class="sxs-lookup"><span data-stu-id="072fe-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="072fe-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="072fe-121">See also</span></span>

- [<span data-ttu-id="072fe-122">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="072fe-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="072fe-123">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="072fe-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="072fe-124">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="072fe-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="072fe-125">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="072fe-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
