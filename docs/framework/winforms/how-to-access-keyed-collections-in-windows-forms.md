---
title: "Gewusst wie: Zugreifen auf verschlüsselte Auflistungen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2bca9b56f37c815bfa9f1520467ae0ae864c14ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="c0898-102">Gewusst wie: Zugreifen auf verschlüsselte Auflistungen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0898-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="c0898-103">Sie können einzelne Auflistungselemente durch Schlüssel zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c0898-103">You can access individual collection items by key.</span></span> <span data-ttu-id="c0898-104">Diese Funktionalität wurde um viele Auflistungsklassen hinzugefügt, die in der Regel von Windows Forms-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0898-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="c0898-105">Die folgende Liste enthält einige der Auflistungsklassen, die zugänglich schlüsselgebundene Auflistungen haben:</span><span class="sxs-lookup"><span data-stu-id="c0898-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="c0898-106">Der zugeordneten Schlüssel für ein Element in einer Auflistung ist in der Regel der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="c0898-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="c0898-107">Nachfolgend wird erläutert, wie Auflistungsklassen zu verwenden, um allgemeine Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c0898-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="c0898-108">Zum Suchen, und geben Sie ein geschachteltes Steuerelement in einer steuerelementauflistung den Fokus</span><span class="sxs-lookup"><span data-stu-id="c0898-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="c0898-109">Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> und <xref:System.Windows.Forms.Control.Focus%2A> Methoden, um den Namen des Steuerelements zu suchen, und setzen Sie den Fokus zu geben.</span><span class="sxs-lookup"><span data-stu-id="c0898-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="c0898-110">Auf ein Bild in einer Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c0898-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="c0898-111">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> -Eigenschaft den Namen des Bilds an die Sie zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0898-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="c0898-112">Festlegen eine Registerkarte als ausgewählte Registerkarte</span><span class="sxs-lookup"><span data-stu-id="c0898-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="c0898-113">Verwenden der <xref:System.Windows.Forms.TabControl.SelectedTab%2A> Eigenschaft zusammen mit der <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> Eigenschaft, um den Namen der Registerkartenseite festzulegende als der ausgewählten Registerkarte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c0898-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c0898-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0898-114">See Also</span></span>  
 [<span data-ttu-id="c0898-115">Erste Schritte mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0898-115">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="c0898-116">Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0898-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
