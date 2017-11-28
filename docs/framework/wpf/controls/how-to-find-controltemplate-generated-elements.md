---
title: 'Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden'
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
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f81069873930af57e1f6ab2f3e0408b4d53f38b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie nach Elementen suchen, die generiert werden, indem Sie eine <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Format, das eine einfache erstellt <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button> Klasse:  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Zum Suchen nach einem Element in der Vorlage aus, nachdem die Vorlage angewendet wurde, rufen Sie die <xref:System.Windows.FrameworkTemplate.FindName%2A> Methode der <xref:System.Windows.Controls.Control.Template%2A>. Das folgende Beispiel erstellt ein Meldungsfeld mit der tatsächlichen Breitenwert, der an die <xref:System.Windows.Controls.Grid> innerhalb der Steuerelementvorlage:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen von Elementen, die mit einer DataTemplate generiert wurden](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [WPF-XAML-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
