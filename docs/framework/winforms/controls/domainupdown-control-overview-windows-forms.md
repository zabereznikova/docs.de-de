---
title: "Übersicht über das DomainUpDown-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0692677b8ef596bb31b1869480603573a9ec98d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="36431-102">Übersicht über das DomainUpDown-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="36431-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="36431-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> -Steuerelement ist im Wesentlichen eine Kombination aus einem Textfeld und einem Paar von Schaltflächen für das Durchsuchen einer Liste nach oben oder unten.</span><span class="sxs-lookup"><span data-stu-id="36431-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="36431-104">Das Steuerelement zeigt an, und legt eine Zeichenfolge aus einer Liste von Optionen.</span><span class="sxs-lookup"><span data-stu-id="36431-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="36431-105">Der Benutzer kann die Zeichenfolge auswählen, indem Sie auf nach oben oder unten Schaltflächen, um eine Liste durchlaufen, durch Drücken der nach-oben und nach unten-Taste oder durch Eingabe eine Zeichenfolge, die ein Element in der Liste entspricht.</span><span class="sxs-lookup"><span data-stu-id="36431-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="36431-106">Eine Verwendungsmöglichkeit für dieses Steuerelement ist für das Auswählen von Elementen aus einer alphabetisch sortierte Liste der Namen.</span><span class="sxs-lookup"><span data-stu-id="36431-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36431-107">Um die Liste zu sortieren, legen die <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="36431-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="36431-108">Die Funktion dieses Steuerelements wird im Listenfeld oder Kombinationsfeld sehr ähnlich, aber es nur sehr wenig Speicherplatz beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="36431-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="36431-109">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="36431-109">Key Properties</span></span>  
 <span data-ttu-id="36431-110">Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, und <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="36431-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="36431-111">Die <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft enthält die Liste der Objekte, deren Text im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="36431-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="36431-112">Wenn <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> festgelegt ist, um `false`, das Steuerelement automatisch abgeschlossen wird, Text, dass der Benutzer eingibt, und es mit einem Wert in der Liste vergleicht.</span><span class="sxs-lookup"><span data-stu-id="36431-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="36431-113">Wenn <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> festgelegt ist, um `true`, Durchführen eines Bildlaufs hinter dem letzten Element gelangen Sie auf das erste Element in der Liste und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="36431-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="36431-114">Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> und <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="36431-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="36431-115">Dieses Steuerelement zeigt nur Textzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="36431-115">This control displays only text strings.</span></span> <span data-ttu-id="36431-116">Wenn Sie ein Steuerelement möchten, in dem numerische Werte angezeigt, verwenden die <xref:System.Windows.Forms.NumericUpDown> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="36431-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="36431-117">Weitere Informationen finden Sie unter [Übersicht über das NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="36431-117">For more information, see [NumericUpDown Control Overview](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36431-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36431-118">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 [<span data-ttu-id="36431-119">DomainUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="36431-119">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
