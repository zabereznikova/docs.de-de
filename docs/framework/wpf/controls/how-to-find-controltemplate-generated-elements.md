---
title: 'Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 232ee7d2859059591c9beff753f45781598a8127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460704"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie Sie nach Elementen suchen, die von einem <xref:System.Windows.Controls.ControlTemplate>generiert werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Stil, der eine einfache <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button>-Klasse erstellt:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Um nach dem Anwenden der Vorlage ein Element innerhalb der Vorlage zu finden, können Sie die <xref:System.Windows.FrameworkTemplate.FindName%2A>-Methode der <xref:System.Windows.Controls.Control.Template%2A>abrufen. Im folgenden Beispiel wird ein Meldungs Feld erstellt, in dem der tatsächliche Breitenwert des <xref:System.Windows.Controls.Grid> in der Steuerelement Vorlage angezeigt wird:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Siehe auch

- [Suchen von Elementen, die mit einer DataTemplate generiert wurden](../data/how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md)
- [Strukturen in WPF](../advanced/trees-in-wpf.md)
