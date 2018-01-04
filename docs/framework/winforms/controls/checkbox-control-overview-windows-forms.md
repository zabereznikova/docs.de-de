---
title: "Übersicht über das CheckBox-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39645a02cd66d37d61df72028ab129677edb757e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="7bef6-102">Übersicht über das CheckBox-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7bef6-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="7bef6-103">Das Windows Forms-Steuerelement <xref:System.Windows.Forms.CheckBox> zeigt an, ob eine bestimmte Bedingung aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7bef6-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="7bef6-104">Es wird häufig verwendet, um dem Benutzer eine Ja/Nein- oder Wahr/Falsch-Auswahl zu präsentieren.</span><span class="sxs-lookup"><span data-stu-id="7bef6-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="7bef6-105">Sie können Kontrollkästchen-Steuerelemente in Gruppen verwenden, um mehrere Optionen anzuzeigen, unter denen der Benutzer eine oder mehrere auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="7bef6-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="7bef6-106">Das Kontrollkästchensteuerelement ähnelt das Optionsfeld-Steuerelement jeder verwendet wird, eine Auswahl an, die vom Benutzer stammt.</span><span class="sxs-lookup"><span data-stu-id="7bef6-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="7bef6-107">Sie unterscheiden sich in, denen nur ein Optionsfeld in einer Gruppe zu einem Zeitpunkt ausgewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7bef6-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="7bef6-108">Mit dem Kontrollkästchen-Steuerelement kann jedoch eine beliebige Anzahl von Kontrollkästchen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="7bef6-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="7bef6-109">Ein Kontrollkästchen kann mit Elementen in einer Datenbank mit der einfachen Datenbindung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="7bef6-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="7bef6-110">Mehrere Kontrollkästchen können gruppiert werden, mithilfe der <xref:System.Windows.Forms.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7bef6-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="7bef6-111">Dies eignet sich für die visuelle Darstellung und auch für den Entwurf der Benutzeroberfläche, da im Formular-Designer zusammen gruppierte Steuerelemente verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="7bef6-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="7bef6-112">Weitere Informationen finden Sie unter [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md) und [GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7bef6-112">For more information, see [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) and [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="7bef6-113">Die <xref:System.Windows.Forms.CheckBox> Steuerelement verfügt über zwei wichtige Eigenschaften <xref:System.Windows.Forms.CheckBox.Checked%2A> und <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bef6-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="7bef6-114">Die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft gibt entweder `true` oder `false`.</span><span class="sxs-lookup"><span data-stu-id="7bef6-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="7bef6-115">Die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft gibt entweder <xref:System.Windows.Forms.CheckState.Checked> oder <xref:System.Windows.Forms.CheckState.Unchecked>; oder, wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> können zurückgeben <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="7bef6-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="7bef6-116">In den unbestimmten Zustand befindet wird das Dialogfeld angezeigt, abgeblendet, um anzugeben, dass die Option nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7bef6-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bef6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bef6-117">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="7bef6-118">Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bef6-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="7bef6-119">Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bef6-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="7bef6-120">CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7bef6-120">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
