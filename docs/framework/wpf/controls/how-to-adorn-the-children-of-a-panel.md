---
title: 'Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550218"
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
