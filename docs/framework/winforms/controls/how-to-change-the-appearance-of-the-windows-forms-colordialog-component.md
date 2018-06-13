---
title: 'Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms'
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
ms.openlocfilehash: 816850fa61de97b5f4c251571a74da7e0a70cba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530246"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="434e0-102">Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="434e0-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="434e0-103">Sie können die Darstellung von Windows Forms konfigurieren <xref:System.Windows.Forms.ColorDialog> Komponente mit dem eine Reihe von seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="434e0-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="434e0-104">Das Dialogfeld enthält zwei Abschnitte – eines, das anzeigt, Grundfarben und eine, die dem Benutzer ermöglicht, benutzerdefinierte Farben definieren.</span><span class="sxs-lookup"><span data-stu-id="434e0-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="434e0-105">Die meisten Eigenschaften einschränken, welche Farben im Dialogfeld die Benutzer auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="434e0-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="434e0-106">Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `true`, den der Benutzer benutzerdefinierte Farben definieren.</span><span class="sxs-lookup"><span data-stu-id="434e0-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="434e0-107">Die <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> Eigenschaft `true` verwenden, wenn das Dialogfeld, zum Definieren benutzerdefinierter Farben erweitert wird; andernfalls der Benutzer muss klicken Sie auf eine Schaltfläche "Benutzerdefinierte Farben definieren".</span><span class="sxs-lookup"><span data-stu-id="434e0-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="434e0-108">Wenn die <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> -Eigenschaftensatz auf `true`, das Dialogfeld zeigt alle verfügbare Farben in der Menge der Grundfarben.</span><span class="sxs-lookup"><span data-stu-id="434e0-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="434e0-109">Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht Dithering Farben auswählen; nur Volltonfarben stehen zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="434e0-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="434e0-110">Wenn die <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> -Eigenschaftensatz auf `true`, eine Schaltfläche "Hilfe" im Dialogfeld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="434e0-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="434e0-111">Wenn der Benutzer die Schaltfläche "Hilfe" klickt der <xref:System.Windows.Forms.ColorDialog> Komponente <xref:System.Windows.Forms.CommonDialog.HelpRequest> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="434e0-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="434e0-112">So konfigurieren Sie die Darstellung im Dialogfeld "Farbe"</span><span class="sxs-lookup"><span data-stu-id="434e0-112">To configure the appearance of the color dialog box</span></span>  
  
1.  <span data-ttu-id="434e0-113">Legen Sie die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, und <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> Eigenschaften auf die gewünschten Werte.</span><span class="sxs-lookup"><span data-stu-id="434e0-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="434e0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="434e0-114">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="434e0-115">ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="434e0-115">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [<span data-ttu-id="434e0-116">Übersicht über die ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="434e0-116">ColorDialog Component Overview</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
