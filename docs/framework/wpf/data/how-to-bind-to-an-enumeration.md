---
title: 'Gewusst wie: Binden an eine Enumeration'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72439cdc1c1017378a5b6b3f6b4bf41a9eee2537
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="dc47a-102">Gewusst wie: Binden an eine Enumeration</span><span class="sxs-lookup"><span data-stu-id="dc47a-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="dc47a-103">Dieses Beispiel zeigt, wie auf eine Enumeration von Bindung zum GetValues-Enumerationsmethode gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="dc47a-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc47a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc47a-104">Example</span></span>  
 <span data-ttu-id="dc47a-105">Im folgenden Beispiel die <xref:System.Windows.Controls.ListBox> zeigt die Liste der <xref:System.Windows.HorizontalAlignment> Enumerationswerte durch Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="dc47a-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="dc47a-106">Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.Button> gebunden sind, sodass Sie ändern können die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.Button> durch Auswählen eines Werts in der <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="dc47a-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="dc47a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc47a-107">See Also</span></span>  
 [<span data-ttu-id="dc47a-108">Binden an eine Methode</span><span class="sxs-lookup"><span data-stu-id="dc47a-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="dc47a-109">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="dc47a-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="dc47a-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="dc47a-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
