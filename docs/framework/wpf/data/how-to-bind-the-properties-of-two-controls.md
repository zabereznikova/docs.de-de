---
title: 'Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459180"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen
In diesem Beispiel wird gezeigt, wie die-Eigenschaft eines instanziierten Steuer Elements mithilfe der <xref:System.Windows.Data.Binding.ElementName%2A>-Eigenschaft an die andere gebunden wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft einer <xref:System.Windows.Controls.Canvas> an die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>gebunden wird.<xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eines <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Bei Rendern dieses Beispiels sieht es folgendermaßen aus:  
  
![Screenshot, der ein Kombinations Feld mit ausgewähltem grünen Wert und einem grünen Quadrat anzeigt](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> Die Bindungs Ziel Eigenschaft (in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft) muss eine Abhängigkeits Eigenschaft sein. Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
