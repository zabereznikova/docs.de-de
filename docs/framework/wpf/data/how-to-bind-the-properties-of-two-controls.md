---
title: 'Vorgehensweise: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809534"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Vorgehensweise: Binden der Eigenschaften von zwei Steuerelementen
Dieses Beispiel zeigt, wie Sie die Eigenschaft eines instanziierten Steuerelements an, die von einem anderen mit binden die <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie binden die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Canvas> auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> -Eigenschaft einer <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Bei Rendern dieses Beispiels sieht es folgendermaßen aus:  
  
![Screenshot, der ein Kombinationsfeld anzeigt, das mit dem Wert, der grüne aktiviert und ein grünes Quadrat.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> Die Bindungsziel-Eigenschaft (in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft) muss eine Abhängigkeitseigenschaft sein. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](data-binding-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
