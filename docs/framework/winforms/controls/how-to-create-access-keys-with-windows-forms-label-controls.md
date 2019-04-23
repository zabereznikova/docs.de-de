---
title: 'Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen'
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
ms.openlocfilehash: ffe4bf6fb29e82b04938e2ba9a2d9d21e5eabcde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314307"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="54838-102">Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="54838-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="54838-103">Windows Forms <xref:System.Windows.Forms.Label> Steuerelemente können verwendet werden, um die Zugriffstasten für andere Steuerelemente definieren.</span><span class="sxs-lookup"><span data-stu-id="54838-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="54838-104">Wenn Sie einen Zugriffsschlüssel in ein Label-Steuerelement definieren, kann Benutzer drücken, die ALT-Taste plus das Zeichen, das Sie festlegen, um den Fokus auf das Steuerelement zu verschieben, die sie in der Aktivierreihenfolge folgt.</span><span class="sxs-lookup"><span data-stu-id="54838-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="54838-105">Da Bezeichnungen keinen Fokus erhalten können, verschiebt den Fokus automatisch auf das nächste Steuerelement in der Aktivierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="54838-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="54838-106">Verwenden Sie dieses Verfahren, um Textfelder, Kombinationsfelder, Listenfelder und Datenraster Zugriffsschlüssel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="54838-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="54838-107">Zuweisen eine Zugriffstaste auf ein Steuerelement mit einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="54838-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="54838-108">Zeichnen Sie zuerst die Bezeichnung, und klicken Sie dann zeichnen Sie das andere Steuerelement zu.</span><span class="sxs-lookup"><span data-stu-id="54838-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="54838-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="54838-109">-or-</span></span>  
  
     <span data-ttu-id="54838-110">Zeichnen Sie die Steuerelemente in beliebiger Reihenfolge aus, und legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft der Bezeichnung bis eins weniger als das andere Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="54838-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="54838-111">Legen Sie die Bezeichnung des <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="54838-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="54838-112">Verwenden Sie ein kaufmännisches und-Zeichen (&), in der Bezeichnung <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft, um den Zugriffsschlüssel für die Bezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="54838-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="54838-113">Weitere Informationen finden Sie unter [Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="54838-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54838-114">Sie sollten kaufmännische und-Zeichen in ein Label-Steuerelement anzeigen, anstatt Sie zu verwenden, um Zugriffstasten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54838-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="54838-115">Dies kann auftreten, wenn Sie ein Label-Steuerelement an ein Feld in einem Recordset binden, in denen die Daten kaufmännische und-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="54838-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="54838-116">Um das kaufmännische und-Zeichen in ein Label-Steuerelement anzuzeigen, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="54838-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="54838-117">Wenn Sie das kaufmännische und-Zeichen anzuzeigen und außerdem einen Zugriffsschlüssel möchten, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `true` und geben Sie den Zugriffsschlüssel ein kaufmännisches und-Zeichen (&) und dem kaufmännischen und-Zeichen, das mit zwei kaufmännische und-Zeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54838-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54838-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54838-118">See also</span></span>

- [<span data-ttu-id="54838-119">Vorgehensweise: Größe der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="54838-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="54838-120">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="54838-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="54838-121">Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="54838-121">Label Control</span></span>](label-control-windows-forms.md)
