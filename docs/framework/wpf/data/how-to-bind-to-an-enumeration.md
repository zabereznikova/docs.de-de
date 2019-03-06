---
title: 'Vorgehensweise: Binden an eine Enumeration'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: df26d2bd08e4691837f739a4e71d3bb1a25bdd00
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377793"
---
# <a name="how-to-bind-to-an-enumeration"></a>Vorgehensweise: Binden an eine Enumeration
Dieses Beispiel zeigt, wie an eine Enumeration, durch Bindung an eine Methode für die Enumeration des GetValues gebunden wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die <xref:System.Windows.Controls.ListBox> zeigt die Liste der <xref:System.Windows.HorizontalAlignment> Enumerationswerte mithilfe der Datenbindung. Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.Button> gebunden sind, sodass Sie ändern können, die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.Button> durch Auswählen eines Werts in der <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Siehe auch
- [Binden an eine Methode](how-to-bind-to-a-method.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
