---
title: 'Vorgehensweise: Suchen von Elementen einer ControlTemplate generiert wurden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 9a6609d70a6b863f16533aac81ffce4daf171bcf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364501"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Vorgehensweise: Suchen von Elementen einer ControlTemplate generiert wurden
In diesem Beispiel zeigt, wie Sie Elemente, die vom generierten eine <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Format, das eine einfache erstellt <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button> Klasse:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Zum Suchen nach einem Element in der Vorlage aus, nachdem die Vorlage angewendet wurde, rufen Sie die <xref:System.Windows.FrameworkTemplate.FindName%2A> Methode der <xref:System.Windows.Controls.Control.Template%2A>. Das folgende Beispiel erstellt ein Meldungsfeld an, die die tatsächliche Breite-Wert, der angezeigt wird der <xref:System.Windows.Controls.Grid> innerhalb der Steuerelementvorlage:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Siehe auch
- [Suchen von Elementen, die mit einer DataTemplate generiert wurden](../data/how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md)
- [Strukturen in WPF](../advanced/trees-in-wpf.md)
