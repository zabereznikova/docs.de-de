---
title: 'Vorgehensweise: Verzieren der untergeordneten Elemente eines Bereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923525"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Vorgehensweise: Verzieren der untergeordneten Elemente eines Bereichs
In diesem Beispiel wird gezeigt, wie ein Funktions Indikator Programm gesteuert an die untergeordneten Elemente <xref:System.Windows.Controls.Panel>eines angegebenen gebunden wird.  
  
## <a name="example"></a>Beispiel  
 Führen Sie die folgenden Schritte aus <xref:System.Windows.Controls.Panel>, um einen Funktions Indikator an die untergeordneten Elemente eines zu binden:  
  
1. Deklarieren Sie <xref:System.Windows.Documents.AdornerLayer> ein neues-Objekt `static` , und rufen Sie die <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> -Methode auf, um eine Adornerebene für das Element zu finden, dessen untergeordnete Elemente geschmückt werden  
  
2. Listet die untergeordneten Elemente des übergeordneten Elements auf und ruft <xref:System.Windows.Documents.AdornerLayer.Add%2A> die-Methode auf, um einen Funktions Indikator an jedes untergeordnete Element zu binden.  
  
 Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente <xref:System.Windows.Controls.StackPanel> eines namens *myStackPanel*gebunden.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Adorner](adorners-overview.md)
