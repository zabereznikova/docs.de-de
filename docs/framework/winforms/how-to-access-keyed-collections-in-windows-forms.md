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
ms.openlocfilehash: a88e4766a1e774582bcd0356c9b6e77bc31f1960
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928528"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="aedad-102">Vorgehensweise: Zugreifen auf verschlüsselte Auflistungen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aedad-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="aedad-103">Sie können auf einzelne Sammel Elemente nach Schlüssel zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aedad-103">You can access individual collection items by key.</span></span> <span data-ttu-id="aedad-104">Diese Funktionalität wurde vielen Sammlungs Klassen hinzugefügt, die in der Regel von Windows Forms Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aedad-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="aedad-105">In der folgenden Liste sind einige der Auflistungs Klassen aufgeführt, für die barrierefreie Sammlungen zugänglich sind:</span><span class="sxs-lookup"><span data-stu-id="aedad-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="aedad-106">Der Schlüssel, der einem Element in einer Auflistung zugeordnet ist, ist in der Regel der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="aedad-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="aedad-107">In den folgenden Verfahren wird gezeigt, wie Sie mithilfe von Auflistungs Klassen häufige Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="aedad-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="aedad-108">So suchen und setzen Sie den Fokus auf ein in einer Steuerelement Sammlung eingefügter Steuerelement</span><span class="sxs-lookup"><span data-stu-id="aedad-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="aedad-109">Verwenden Sie <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> die <xref:System.Windows.Forms.Control.Focus%2A> -Methode und die-Methode, um den Namen des Steuer Elements anzugeben, das gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="aedad-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="aedad-110">So greifen Sie auf ein Bild in einer Bild Auflistung zu</span><span class="sxs-lookup"><span data-stu-id="aedad-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="aedad-111">Verwenden Sie <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> die-Eigenschaft, um den Namen des Abbilds anzugeben, auf das Sie zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="aedad-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="aedad-112">So legen Sie eine Registerkarte als ausgewählte Registerkarte fest</span><span class="sxs-lookup"><span data-stu-id="aedad-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="aedad-113">Verwenden Sie <xref:System.Windows.Forms.TabControl.SelectedTab%2A> die-Eigenschaft in <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> Verbindung mit der-Eigenschaft, um den Namen der Registerkarte anzugeben, die als ausgewählte Registerkarte festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="aedad-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="aedad-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aedad-114">See also</span></span>

- [<span data-ttu-id="aedad-115">Erste Schritte mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aedad-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="aedad-116">Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="aedad-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
