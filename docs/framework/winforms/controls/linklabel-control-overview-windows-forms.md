---
title: "Übersicht über das LinkLabel-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0cb01c0fc5503a5bf16e1f191d87ae90907ec816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="8feb2-102">Übersicht über das LinkLabel-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8feb2-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="8feb2-103">Windows Forms <xref:System.Windows.Forms.LinkLabel> Steuerelement ermöglicht es Ihnen, Windows Forms-Anwendungen Weblinks hinzu.</span><span class="sxs-lookup"><span data-stu-id="8feb2-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="8feb2-104">Können Sie die <xref:System.Windows.Forms.LinkLabel> Control für alle Elemente, die Sie verwenden können, die <xref:System.Windows.Forms.Label> für steuern; Sie können auch Teile des Texts als Link in einer Datei, einem Ordner oder einer Webseite festlegen.</span><span class="sxs-lookup"><span data-stu-id="8feb2-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you also can set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="8feb2-105">Was können Sie mit dem LinkLabel-Steuerelement tun.</span><span class="sxs-lookup"><span data-stu-id="8feb2-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="8feb2-106">Zusätzlich zu allen Eigenschaften, Methoden und Ereignisse der <xref:System.Windows.Forms.Label> -Steuerelement, das <xref:System.Windows.Forms.LinkLabel> Steuerelement verfügt über Eigenschaften für Links und Linkfarben.</span><span class="sxs-lookup"><span data-stu-id="8feb2-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="8feb2-107">Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft legt den Bereich des Texts, der die Verknüpfung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8feb2-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="8feb2-108">Die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, und <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> Eigenschaften legen die Farben des Links.</span><span class="sxs-lookup"><span data-stu-id="8feb2-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="8feb2-109">Die <xref:System.Windows.Forms.LinkLabel.LinkClicked> Ereignis bestimmt, was geschieht, wenn der Text des Links ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8feb2-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="8feb2-110">Der einfachsten Verwendung von der <xref:System.Windows.Forms.LinkLabel> Steuerelement wird zum Anzeigen einer einzelnen Link mit der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Eigenschaft, aber Sie können auch mehrere Links mit Anzeigen der <xref:System.Windows.Forms.LinkLabel.Links%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8feb2-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="8feb2-111">Die <xref:System.Windows.Forms.LinkLabel.Links%2A> Eigenschaft ermöglicht Ihnen, eine Sammlung von Links zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8feb2-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="8feb2-112">Sie können auch angeben, Daten in die <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> -Eigenschaft jedes einzelnen <xref:System.Windows.Forms.LinkLabel.Link> Objekt.</span><span class="sxs-lookup"><span data-stu-id="8feb2-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="8feb2-113">Der Wert, der die <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> Eigenschaft kann verwendet werden, um den Speicherort einer Datei mit Anzeige oder die Adresse einer Website zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8feb2-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8feb2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8feb2-114">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="8feb2-115">Übersicht über das Label-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8feb2-115">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="8feb2-116">Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8feb2-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="8feb2-117">Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8feb2-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
