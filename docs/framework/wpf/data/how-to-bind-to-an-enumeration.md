---
title: 'Gewusst wie: Binden an eine Enumeration'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454439"
---
# <a name="how-to-bind-to-an-enumeration"></a>Gewusst wie: Binden an eine Enumeration
Dieses Beispiel zeigt, wie Sie eine Bindung an eine Enumeration durch Binden an die GetValues-Methode der-Enumeration herstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel zeigt der <xref:System.Windows.Controls.ListBox> die Liste der <xref:System.Windows.HorizontalAlignment> Enumerationswerte durch Datenbindung an. Die <xref:System.Windows.Controls.ListBox> und die <xref:System.Windows.Controls.Button> sind so gebunden, dass Sie den <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>-Eigenschafts Wert der <xref:System.Windows.Controls.Button> ändern können, indem Sie im <xref:System.Windows.Controls.ListBox>einen Wert auswählen.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Siehe auch

- [Binden an eine Methode](how-to-bind-to-a-method.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
