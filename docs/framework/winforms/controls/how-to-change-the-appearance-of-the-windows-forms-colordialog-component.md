---
title: Darstellung der Color Dialog-Komponente ändern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746633"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="6d7c5-102">Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d7c5-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="6d7c5-103">Sie können die Darstellung der Windows Forms <xref:System.Windows.Forms.ColorDialog> Komponente mit einer Reihe von Eigenschaften konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="6d7c5-104">Das Dialogfeld enthält zwei Abschnitte – eine, in der die Grundfarben angezeigt werden, und eine, mit der Benutzer benutzerdefinierte Farben definieren können.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="6d7c5-105">Die meisten Eigenschaften schränken die Farben ein, die der Benutzer im Dialogfeld auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="6d7c5-106">Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>-Eigenschaft auf `true`festgelegt ist, darf der Benutzer benutzerdefinierte Farben definieren.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="6d7c5-107">Die <xref:System.Windows.Forms.ColorDialog.FullOpen%2A>-Eigenschaft ist `true`, wenn das Dialogfeld erweitert wird, um benutzerdefinierte Farben zu definieren. Andernfalls muss der Benutzer auf die Schaltfläche "benutzerdefinierte Farben definieren" klicken.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="6d7c5-108">Wenn die <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>-Eigenschaft auf `true`festgelegt ist, werden im Dialogfeld alle verfügbaren Farben im Satz der Grundfarben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="6d7c5-109">Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>-Eigenschaft auf `true`festgelegt ist, kann der Benutzer keine Dithering-Farben auswählen. Es können nur voll Tonfarben ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="6d7c5-110">Wenn die <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>-Eigenschaft auf `true`festgelegt ist, wird im Dialogfeld eine Schaltfläche "Hilfe" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="6d7c5-111">Wenn der Benutzer auf die Schaltfläche "Hilfe" klickt, wird das <xref:System.Windows.Forms.CommonDialog.HelpRequest> Ereignis der <xref:System.Windows.Forms.ColorDialog> Komponente ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="6d7c5-112">So konfigurieren Sie die Darstellung des Dialog Felds "Farbe"</span><span class="sxs-lookup"><span data-stu-id="6d7c5-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="6d7c5-113">Legen Sie die Eigenschaften <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>und <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> auf die gewünschten Werte fest.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6d7c5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d7c5-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="6d7c5-115">ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="6d7c5-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="6d7c5-116">Übersicht über die ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="6d7c5-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
