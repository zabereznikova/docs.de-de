---
title: 'Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974818"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen

In diesem Beispiel wird gezeigt, wie die-Eigenschaft eines instanziierten Steuer Elements mithilfe der <xref:System.Windows.Data.Binding.ElementName%2A>-Eigenschaft an die andere gebunden wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft einer <xref:System.Windows.Controls.Canvas> an die [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) -Eigenschaft eines <xref:System.Windows.Controls.ComboBox>gebunden wird:

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

Bei Rendern dieses Beispiels sieht es folgendermaßen aus:

![Screenshot, der ein Kombinations Feld mit ausgewähltem grünen Wert und einem grünen Quadrat anzeigt](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> Die Bindungs Ziel Eigenschaft (in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft) muss eine Abhängigkeits Eigenschaft sein. Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

## <a name="see-also"></a>Siehe auch

- [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
