---
title: "Gewusst wie: Erstellen eines schreibgeschützten TextBox-Steuerelements"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d3acf1e5065633f9f4c75f24780230525b01ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="e60ac-102">Gewusst wie: Erstellen eines schreibgeschützten TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="e60ac-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="e60ac-103">In diesem Beispiel wird gezeigt, wie so konfigurieren Sie eine <xref:System.Windows.Controls.TextBox> Steuerelement, damit keine Benutzereingaben oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="e60ac-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e60ac-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e60ac-104">Example</span></span>  
 <span data-ttu-id="e60ac-105">Um zu verhindern, dass Benutzer ändern des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, legen Sie die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> -Attribut auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="e60ac-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="e60ac-106">Die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Attribut wirkt sich nur die Benutzereingabe; er hat keinen Einfluss auf Text festgelegt, der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beschreibung eine <xref:System.Windows.Controls.TextBox> Steuerelement oder Text programmgesteuert durch Festlegen der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e60ac-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="e60ac-107">Der Standardwert von <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> ist **"false"**.</span><span class="sxs-lookup"><span data-stu-id="e60ac-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60ac-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e60ac-108">See Also</span></span>  
 [<span data-ttu-id="e60ac-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="e60ac-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="e60ac-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e60ac-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
