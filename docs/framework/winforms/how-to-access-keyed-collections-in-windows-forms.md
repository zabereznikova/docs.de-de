---
title: 'Vorgehensweise: Zugreifen auf verschlüsselte Auflistungen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: fdd3a56ab9a267990bb0e832c0d4cc2af9334034
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801828"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="67bce-102">Vorgehensweise: Zugreifen auf verschlüsselte Auflistungen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67bce-102">How to: Access Keyed Collections in Windows Forms</span></span>
- <span data-ttu-id="67bce-103">Sie können auf einzelne Auflistungselemente mit Schlüssel zugreifen.</span><span class="sxs-lookup"><span data-stu-id="67bce-103">You can access individual collection items by key.</span></span> <span data-ttu-id="67bce-104">Diese Funktion verfügt über viele Auflistungsklassen hinzugefügt, die in der Regel von Windows Forms-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67bce-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="67bce-105">Die folgende Liste enthält einige der Auflistungsklassen, die zugänglich schlüsselgebundene Auflistungen haben:</span><span class="sxs-lookup"><span data-stu-id="67bce-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="67bce-106">Ein Element in einer Sammlung zugeordnete Schlüssel wird in der Regel der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="67bce-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="67bce-107">Die folgenden Verfahren zeigen, wie Auflistungsklassen zu verwenden, um allgemeine Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67bce-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="67bce-108">Suchen, und geben Sie ein geschachteltes Steuerelement in einer steuerelementauflistung den Fokus</span><span class="sxs-lookup"><span data-stu-id="67bce-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="67bce-109">Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> und <xref:System.Windows.Forms.Control.Focus%2A> Methoden geben Sie den Namen des Steuerelements zu finden, und geben Sie den Fokus auf.</span><span class="sxs-lookup"><span data-stu-id="67bce-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="67bce-110">Auf ein Bild in einer imagesammlung</span><span class="sxs-lookup"><span data-stu-id="67bce-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="67bce-111">Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> -Eigenschaft den Namen des Bilds an die Sie zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="67bce-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="67bce-112">Festlegen eine Registerkarte als ausgewählte Registerkarte</span><span class="sxs-lookup"><span data-stu-id="67bce-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="67bce-113">Verwenden der <xref:System.Windows.Forms.TabControl.SelectedTab%2A> Eigenschaft zusammen mit den <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> Eigenschaft, um den Namen der Registerkarte für die festzulegende als ausgewählte Registerkarte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="67bce-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="67bce-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67bce-114">See also</span></span>

- [<span data-ttu-id="67bce-115">Erste Schritte mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67bce-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="67bce-116">Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67bce-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
