---
title: 'Gewusst wie: Festlegen des Eingabeformats'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 6f554c239e3444db5f6ac84f7994108ac70df0a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="27b7d-102">Gewusst wie: Festlegen des Eingabeformats</span><span class="sxs-lookup"><span data-stu-id="27b7d-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="27b7d-103">Das maskierte Textfeld-Steuerelement ist eine verbesserte Textfeld-Steuerelement, die eine deklarative Syntax zum Akzeptieren oder ablehnen von Benutzereingaben unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27b7d-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="27b7d-104">Durch Festlegen der Mask-Eigenschaft, können Sie die zulässigen Benutzereingaben angeben, ohne dass eine benutzerdefinierte Validierungslogik in der Anwendung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b7d-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="27b7d-105">Weitere Informationen finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox> Klasse.</span><span class="sxs-lookup"><span data-stu-id="27b7d-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="27b7d-106">Manuelles Festlegen der Mask-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="27b7d-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="27b7d-107">Wenn Sie mit den Zeichen vertraut, die die Mask-Eigenschaft unterstützt sind, können Sie es manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="27b7d-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="27b7d-108">Eine Zusammenfassung der Zeichen, die die Mask-Eigenschaft unterstützt, finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="27b7d-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="27b7d-109">Die Mask-Eigenschaft manuell festlegen.</span><span class="sxs-lookup"><span data-stu-id="27b7d-109">To set the Mask property manually</span></span>  
  
1.  <span data-ttu-id="27b7d-110">In **Entwurf** wählen eine <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="27b7d-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2.  <span data-ttu-id="27b7d-111">In der **Eigenschaften** Fenster, suchen Sie die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="27b7d-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3.  <span data-ttu-id="27b7d-112">Geben Sie die Maske, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="27b7d-112">Type the mask that you want.</span></span> <span data-ttu-id="27b7d-113">Geben Sie z. B. `###`.</span><span class="sxs-lookup"><span data-stu-id="27b7d-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="27b7d-114">Mithilfe des Dialogfelds Eingabeformat</span><span class="sxs-lookup"><span data-stu-id="27b7d-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="27b7d-115">Die Input Mask-Dialogfeld stellt einige vordefinierte Eingabeformate bereit.</span><span class="sxs-lookup"><span data-stu-id="27b7d-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="27b7d-116">Sie können auch vordefinierten Masken ändern oder eigene Maske manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="27b7d-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="27b7d-117">So öffnen das Dialogfeld Eingabeformat</span><span class="sxs-lookup"><span data-stu-id="27b7d-117">To open the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="27b7d-118">In **Entwurf** wählen eine <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="27b7d-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="27b7d-119">Klicken Sie auf das Smarttag, öffnen Sie die **MaskedTextBox-Aufgaben** Bereich.</span><span class="sxs-lookup"><span data-stu-id="27b7d-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="27b7d-120">Klicken Sie auf **Maske festlegen**.</span><span class="sxs-lookup"><span data-stu-id="27b7d-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="27b7d-121">\- oder –</span><span class="sxs-lookup"><span data-stu-id="27b7d-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="27b7d-122">In der **Eigenschaften** wählen die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="27b7d-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="27b7d-123">Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, in der Eigenschaft-Wert-Spalte.</span><span class="sxs-lookup"><span data-stu-id="27b7d-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="27b7d-124">Die **Eingabeformat** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27b7d-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="27b7d-125">Zum Verwenden der Input Mask-Dialogfelds</span><span class="sxs-lookup"><span data-stu-id="27b7d-125">To use the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="27b7d-126">(Optional) Klicken Sie auf eine der vordefinierten Masken in der Liste.</span><span class="sxs-lookup"><span data-stu-id="27b7d-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2.  <span data-ttu-id="27b7d-127">(Optional) Bearbeiten Sie die vordefinierte Maske in die **Maske** Feld.</span><span class="sxs-lookup"><span data-stu-id="27b7d-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3.  <span data-ttu-id="27b7d-128">(Optional) Geben Sie eine neue Maske in die **Maske** Feld.</span><span class="sxs-lookup"><span data-stu-id="27b7d-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="27b7d-129">Sie haben also nicht eine der vordefinierten Masken verwenden.</span><span class="sxs-lookup"><span data-stu-id="27b7d-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27b7d-130">Das Feld Vorschau zeigt die Zeichen, die dem Benutzer angezeigt, in wird der <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="27b7d-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="27b7d-131">Diese Zeichen sind eine Anleitung für die Benutzer die Daten ordnungsgemäß eingeben helfen.</span><span class="sxs-lookup"><span data-stu-id="27b7d-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4.  <span data-ttu-id="27b7d-132">Aktivieren oder Deaktivieren der **verwenden ValidatingType** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="27b7d-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="27b7d-133">Die **verwenden ValidatingType** Kontrollkästchen gibt an, ob ein Datentyp verwendet wird, um zu überprüfen, ob die Dateneingabe vom Benutzer.</span><span class="sxs-lookup"><span data-stu-id="27b7d-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="27b7d-134">Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="27b7d-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5.  <span data-ttu-id="27b7d-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="27b7d-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="27b7d-136">Die Maske eingegeben wird, der **Maske** Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="27b7d-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b7d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27b7d-137">See Also</span></span>  
 [<span data-ttu-id="27b7d-138">Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="27b7d-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
