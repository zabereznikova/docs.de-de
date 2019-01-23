---
title: 'Vorgehensweise: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms'
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
ms.openlocfilehash: b516a88b4830c5ed1bccfc5ecb76ebc97c6e3b56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530288"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="36179-102">Vorgehensweise: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36179-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="36179-103">Sie können konfigurieren, das Erscheinungsbild der Windows-Formulare <xref:System.Windows.Forms.ColorDialog> Komponente mit dem eine Reihe von dessen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="36179-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="36179-104">Das Dialogfeld verfügt über zwei Abschnitte: einen, der anzeigt, Grundfarben und eine, die dem Benutzer ermöglicht, benutzerdefinierte Farben definieren.</span><span class="sxs-lookup"><span data-stu-id="36179-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="36179-105">Die meisten Eigenschaften einschränken, welche Farben im Dialogfeld der Benutzer auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="36179-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="36179-106">Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `true`, können Benutzer benutzerdefinierte Farben definieren.</span><span class="sxs-lookup"><span data-stu-id="36179-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="36179-107">Die <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> Eigenschaft `true` Wenn das Dialogfeld wird erweitert, damit benutzerdefinierte Farben definiert werden andernfalls der Benutzer muss klicken Sie auf eine Schaltfläche "Benutzerdefinierte Farben".</span><span class="sxs-lookup"><span data-stu-id="36179-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="36179-108">Wenn die <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> -Eigenschaftensatz auf `true`, im Dialogfeld werden alle verfügbare Farben angezeigt, in der Menge der Grundfarben.</span><span class="sxs-lookup"><span data-stu-id="36179-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="36179-109">Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht mit Dithering Farben auswählen, stehen nur Volltonfarben auswählen.</span><span class="sxs-lookup"><span data-stu-id="36179-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="36179-110">Wenn die <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> -Eigenschaftensatz auf `true`, eine Schaltfläche "Hilfe", die im Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36179-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="36179-111">Wenn der Benutzer die Schaltfläche "Hilfe" klickt der <xref:System.Windows.Forms.ColorDialog> Komponente <xref:System.Windows.Forms.CommonDialog.HelpRequest> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="36179-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="36179-112">So konfigurieren Sie die Darstellung im Dialogfeld "Farbe"</span><span class="sxs-lookup"><span data-stu-id="36179-112">To configure the appearance of the color dialog box</span></span>  
  
1.  <span data-ttu-id="36179-113">Legen Sie die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, und <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> Eigenschaften auf die gewünschten Werte.</span><span class="sxs-lookup"><span data-stu-id="36179-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="36179-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36179-114">See also</span></span>
- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="36179-115">ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="36179-115">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
- [<span data-ttu-id="36179-116">Übersicht über die ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="36179-116">ColorDialog Component Overview</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
