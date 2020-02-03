---
title: Erstellen von Zugriffs Schlüsseln mit Label-Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731051"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="e9f2e-102">Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e9f2e-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="e9f2e-103">Windows Forms <xref:System.Windows.Forms.Label>-Steuerelemente können verwendet werden, um Zugriffsschlüssel für andere Steuerelemente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="e9f2e-104">Wenn Sie in einem Label-Steuerelement eine Zugriffstaste definieren, kann der Benutzer die Alt-Taste sowie das von Ihnen festgelegten Zeichen drücken, um den Fokus in der Aktivier Reihenfolge auf das Steuerelement zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="e9f2e-105">Da Bezeichnungen keinen Fokus erhalten können, wechselt der Fokus automatisch zum nächsten Steuerelement in der Aktivier Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="e9f2e-106">Verwenden Sie dieses Verfahren, um Textfeldern, Kombinations Feldern, Listenfeldern und Daten Rastern Zugriffstasten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="e9f2e-107">So weisen Sie einem Steuerelement mit einer Bezeichnung einen Zugriffsschlüssel zu</span><span class="sxs-lookup"><span data-stu-id="e9f2e-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="e9f2e-108">Zeichnen Sie zuerst die Bezeichnung, und zeichnen Sie dann das andere Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="e9f2e-109">Oder</span><span class="sxs-lookup"><span data-stu-id="e9f2e-109">-or-</span></span>  
  
     <span data-ttu-id="e9f2e-110">Zeichnen Sie die Steuerelemente in beliebiger Reihenfolge, und legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A>-Eigenschaft der Bezeichnung auf ein kleiner als das andere Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="e9f2e-111">Legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A>-Eigenschaft der Bezeichnung auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="e9f2e-112">Verwenden Sie ein kaufmännisches und-Zeichen (&) in der <xref:System.Windows.Forms.Label.Text%2A>-Eigenschaft der Bezeichnung, um den Zugriffsschlüssel für die Bezeichnung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="e9f2e-113">Weitere Informationen finden Sie unter [Erstellen von Zugriffs Schlüsseln für Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e9f2e-114">Möglicherweise möchten Sie kaufmännische und-Zeichen in einem Label-Steuerelement anzeigen, anstatt Sie zum Erstellen von Zugriffs Schlüsseln zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="e9f2e-115">Dies kann vorkommen, wenn Sie ein Label-Steuerelement an ein Feld in einem Recordset binden, in dem die Daten kaufmännische Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="e9f2e-116">Legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A>-Eigenschaft auf `false`fest, um kaufmännische Zeichen in einem Label-Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="e9f2e-117">Wenn Sie kaufmännische und auch Zugriffsschlüssel anzeigen möchten, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A>-Eigenschaft auf `true` fest, und geben Sie den Zugriffsschlüssel mit einem kaufmännischen und-Zeichen (&) und dem kaufmännischen und-Zeichen an, um zwei kaufmännische und-Zeichen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9f2e-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e9f2e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9f2e-118">See also</span></span>

- [<span data-ttu-id="e9f2e-119">Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="e9f2e-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="e9f2e-120">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e9f2e-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="e9f2e-121">Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e9f2e-121">Label Control</span></span>](label-control-windows-forms.md)
