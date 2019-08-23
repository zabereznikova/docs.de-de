---
title: 'Vorgehensweise: Binden eines Adorners an ein Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: e8c7eb929042bfe1455bfc9bf459fc466de5c397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923496"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Vorgehensweise: Binden eines Adorners an ein Element
In diesem Beispiel wird gezeigt, wie ein Funktions Indikator Programm gesteuert an eine <xref:System.Windows.UIElement>angegebene gebunden wird.  
  
## <a name="example"></a>Beispiel  
 Führen Sie die folgenden Schritte aus, um <xref:System.Windows.UIElement>einen Funktions Indikator an einen bestimmten zu binden:  
  
1. Ruft die `static` - <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode auf, <xref:System.Windows.Documents.AdornerLayer> um ein- <xref:System.Windows.UIElement> Objekt zu erhalten, das zu schmücken ist. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>durchläuft die visuelle Struktur, beginnend beim angegebenen **UIElement**, und gibt die erste gefundene Adornerebene zurück. (Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)  
  
2. Ruft die <xref:System.Windows.Documents.AdornerLayer.Add%2A> -Methode auf, um den Funktions Indikator an das **UIElement**-Ziel zu binden.  
  
 Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an ein <xref:System.Windows.Controls.TextBox> benanntes *MyTextBox*-Element gebunden.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Adorner](adorners-overview.md)
