---
title: 'Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70a2c1e7735a6df31a44fce7eb9bb2371acc208b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs
Dieses Beispiel zeigt, wie Sie programmgesteuert einen Adorner an die untergeordneten Elemente eines angegebenen binden <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Beispiel  
 So binden Sie einen Adorner an die untergeordneten Elemente einer <xref:System.Windows.Controls.Panel>, gehen Sie folgendermaßen vor:  
  
1.  Deklarieren Sie ein neues <xref:System.Windows.Documents.AdornerLayer> Objekt, und rufen die `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode, um eine Adornerebene für das Element gesucht, deren untergeordnete Elemente sind, gestaltet werden.  
  
2.  Durchlaufen der untergeordneten Elemente des übergeordneten Elements, und rufen die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um einen Adorner an jedes untergeordnete Element binden.  
  
 Im folgenden Beispiel bindet ein SimpleCircleAdorner (siehe oben) auf die untergeordneten eine <xref:System.Windows.Controls.StackPanel> mit dem Namen *MyStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)
