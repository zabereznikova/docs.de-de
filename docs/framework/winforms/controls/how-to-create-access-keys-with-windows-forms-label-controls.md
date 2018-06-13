---
title: 'Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen'
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
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530802"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="28c02-102">Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="28c02-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="28c02-103">Windows Forms <xref:System.Windows.Forms.Label> Steuerelemente können zum Definieren von Zugriffstasten für andere Steuerelemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="28c02-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="28c02-104">Wenn Sie eine Zugriffstaste in ein Label-Steuerelement definieren, kann der Benutzer drücken Sie die ALT-Taste plus das Zeichen, die für die Sicherung um an das Steuerelement den Fokus zu verschieben, die sie in der Aktivierreihenfolge folgt.</span><span class="sxs-lookup"><span data-stu-id="28c02-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="28c02-105">Da Bezeichnungen den Fokus erhalten können, wird den Fokus automatisch auf das nächste Steuerelement in der Aktivierreihenfolge verschoben.</span><span class="sxs-lookup"><span data-stu-id="28c02-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="28c02-106">Verwenden Sie dieses Verfahren, Textfelder, Kombinationsfelder, Listenfelder und Datenblätter Zugriffstasten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="28c02-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="28c02-107">Zuweisen eine Zugriffstaste zu einem Steuerelement mit einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="28c02-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="28c02-108">Zeichnen Sie zuerst die Bezeichnung, und zeichnen Sie dann die Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="28c02-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="28c02-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="28c02-109">-or-</span></span>  
  
     <span data-ttu-id="28c02-110">Zeichnen Sie die Steuerelemente in beliebiger Reihenfolge, und legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft des Bezeichnungsfelds bis eins weniger als die anderen Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="28c02-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="28c02-111">Legen Sie die Bezeichnung <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="28c02-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="28c02-112">Verwenden Sie ein kaufmännisches und-Zeichen (&) in der Bezeichnung <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft, um den Zugriffsschlüssel für die Bezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="28c02-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="28c02-113">Weitere Informationen finden Sie unter [Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="28c02-113">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28c02-114">Möglicherweise möchten und-Zeichen in ein Label-Steuerelement, statt Sie zu verwenden, um das Erstellen von Zugriffstasten.</span><span class="sxs-lookup"><span data-stu-id="28c02-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="28c02-115">Dies kann auftreten, wenn Sie ein Bezeichnungsfeld-Steuerelement an ein Feld in einem Recordset binden, in denen Daten für das kaufmännische und-Zeichen umfassen.</span><span class="sxs-lookup"><span data-stu-id="28c02-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="28c02-116">Wenn kaufmännische und-Zeichen in ein Label-Steuerelement anzeigen möchten, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="28c02-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="28c02-117">Wenn Sie und-Zeichen und außerdem eine Zugriffstaste möchten, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `true` und geben Sie den Zugriffsschlüssel ein kaufmännisches und-Zeichen (&) und das kaufmännische und-Zeichen, das mit zwei kaufmännische und-Zeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28c02-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28c02-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28c02-118">See Also</span></span>  
 [<span data-ttu-id="28c02-119">Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt</span><span class="sxs-lookup"><span data-stu-id="28c02-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="28c02-120">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="28c02-120">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="28c02-121">Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="28c02-121">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
