---
title: 'Vorgehensweise: Festlegen des Eingabeformats'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949145"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="1e202-102">Vorgehensweise: Festlegen des Eingabeformats</span><span class="sxs-lookup"><span data-stu-id="1e202-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="1e202-103">Das maskierte Textfeld-Steuerelement ist ein erweitertes Textfeld-Steuerelement, das eine deklarative Syntax zum akzeptieren oder ablehnen von Benutzereingaben unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e202-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="1e202-104">Indem Sie die Mask-Eigenschaft festlegen, können Sie die zulässige Benutzereingabe angeben, ohne benutzerdefinierte Validierungs Logik in Ihre Anwendung schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1e202-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="1e202-105">Weitere Informationen finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="1e202-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="1e202-106">Manuelles Festlegen der Mask-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e202-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="1e202-107">Wenn Sie mit den Zeichen vertraut sind, die von der Mask-Eigenschaft unterstützt werden, können Sie Sie manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="1e202-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="1e202-108">Eine Zusammenfassung der Zeichen, die von der Mask-Eigenschaft unterstützt werden, finden Sie <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> im Abschnitt "Hinweise" der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1e202-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="1e202-109">So legen Sie die Mask-Eigenschaft manuell fest</span><span class="sxs-lookup"><span data-stu-id="1e202-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="1e202-110">Wählen Sie in der **Entwurfs** Ansicht <xref:System.Windows.Forms.MaskedTextBox>einen aus.</span><span class="sxs-lookup"><span data-stu-id="1e202-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="1e202-111">Suchen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1e202-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="1e202-112">Geben Sie die gewünschte Maske ein.</span><span class="sxs-lookup"><span data-stu-id="1e202-112">Type the mask that you want.</span></span> <span data-ttu-id="1e202-113">Geben Sie beispielsweise Folgendes ein: `###`.</span><span class="sxs-lookup"><span data-stu-id="1e202-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="1e202-114">Verwenden des Dialog Felds Eingabemaske</span><span class="sxs-lookup"><span data-stu-id="1e202-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="1e202-115">Das Dialogfeld Eingabemaske bietet einige vordefinierte Eingabemasken.</span><span class="sxs-lookup"><span data-stu-id="1e202-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="1e202-116">Sie können auch die vordefinierten Masken ändern oder eine eigene Maske manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="1e202-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="1e202-117">So öffnen Sie das Dialogfeld "Eingabemaske"</span><span class="sxs-lookup"><span data-stu-id="1e202-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="1e202-118">Wählen Sie in der **Entwurfs** Ansicht <xref:System.Windows.Forms.MaskedTextBox>einen aus.</span><span class="sxs-lookup"><span data-stu-id="1e202-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="1e202-119">Klicken Sie auf das Smarttag, um das **Aufgaben Panel MaskedTextBox** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1e202-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="1e202-120">Klicken Sie auf **Maske festlegen**.</span><span class="sxs-lookup"><span data-stu-id="1e202-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="1e202-121">\- oder –</span><span class="sxs-lookup"><span data-stu-id="1e202-121">\- or -</span></span>  
  
    1. <span data-ttu-id="1e202-122">Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> -Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="1e202-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="1e202-123">Klicken Sie in der Spalte Eigenschaften Wert auf die Schaltfläche mit den Auslassungs Zeichen</span><span class="sxs-lookup"><span data-stu-id="1e202-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="1e202-124">Das Dialogfeld **Eingabemaske** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e202-124">The **Input Mask** dialog box appears.</span></span>  
  
### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="1e202-125">So verwenden Sie das Dialogfeld "Eingabemaske"</span><span class="sxs-lookup"><span data-stu-id="1e202-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="1e202-126">Optionale Klicken Sie in der Liste auf eine der vordefinierten Masken.</span><span class="sxs-lookup"><span data-stu-id="1e202-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="1e202-127">Optionale Bearbeiten Sie die vordefinierte Maske im Feld **Maske** .</span><span class="sxs-lookup"><span data-stu-id="1e202-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="1e202-128">Optionale Geben Sie eine neue Maske in das Feld **Maske** ein.</span><span class="sxs-lookup"><span data-stu-id="1e202-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="1e202-129">Das heißt, dass Sie nicht eine der vordefinierten Masken verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="1e202-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1e202-130">Im Feld Vorschau werden die Zeichen angezeigt, die dem Benutzer in <xref:System.Windows.Forms.MaskedTextBox>der angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1e202-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="1e202-131">Diese Zeichen sind eine Anleitung, mit deren Hilfe der Benutzer die Daten ordnungsgemäß eingeben können.</span><span class="sxs-lookup"><span data-stu-id="1e202-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="1e202-132">Aktivieren oder deaktivieren Sie das Kontrollkästchen **ValidatingType verwenden** .</span><span class="sxs-lookup"><span data-stu-id="1e202-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="1e202-133">Das Kontrollkästchen **use ValidatingType** gibt an, ob ein Datentyp verwendet wird, um die Dateneingabe durch den Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1e202-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="1e202-134">Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1e202-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="1e202-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e202-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="1e202-136">Die Maske wird in der **Mask** -Eigenschaft im **Eigenschaften** Fenster eingegeben.</span><span class="sxs-lookup"><span data-stu-id="1e202-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e202-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e202-137">See also</span></span>

- [<span data-ttu-id="1e202-138">Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1e202-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
