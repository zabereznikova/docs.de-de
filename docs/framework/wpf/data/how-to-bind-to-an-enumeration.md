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
# <a name="how-to-bind-to-an-enumeration"></a>Gewusst wie: Binden an eine Enumeration
Dieses Beispiel zeigt, wie auf eine Enumeration von Bindung zum GetValues-Enumerationsmethode gebunden wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die <xref:System.Windows.Controls.ListBox> zeigt die Liste der <xref:System.Windows.HorizontalAlignment> Enumerationswerte durch Datenbindung. Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.Button> gebunden sind, sodass Sie ändern können die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.Button> durch Auswählen eines Werts in der <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Siehe auch  
 [Binden an eine Methode](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
