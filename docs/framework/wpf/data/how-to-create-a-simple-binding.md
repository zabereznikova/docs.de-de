---
title: 'Gewusst wie: Erstellen einer einfachen Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 8910dd3ec6c9f72f9d8fb64cd33912f0d4318e5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-simple-binding"></a>Gewusst wie: Erstellen einer einfachen Bindung
Dieses Beispiel veranschaulicht das Erstellen eines einfachen <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel haben Sie eine `Person` Objekt mit der eine Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`. Die `Person` Objekt ist im Namespace namens definiert `SDKSample`.  
  
 Der markierten Zeile mit der `<src>` Element in das folgende Beispiel instanziiert die `Person` -Objekt mit einer `PersonName` Eigenschaftswert des `Joe`. Dies erfolgt in der `Resources` Abschnitt zugewiesen, und wählen Sie eine `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Die markierte Zeile, enthält die `<TextBlock>` Element dann bindet die <xref:System.Windows.Controls.TextBlock> die Steuerung an die `PersonName` Eigenschaft. Daher die <xref:System.Windows.Controls.TextBlock> wird mit dem Wert "Joe" angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
