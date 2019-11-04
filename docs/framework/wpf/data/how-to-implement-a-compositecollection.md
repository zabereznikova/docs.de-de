---
title: 'Gewusst wie: Implementieren von CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454026"
---
# <a name="how-to-implement-a-compositecollection"></a>Gewusst wie: Implementieren von CompositeCollection
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mehrere Auflistungen und Elemente mithilfe der <xref:System.Windows.Data.CompositeCollection>-Klasse als eine Liste angezeigt werden. In diesem Beispiel ist `GreekGods` ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `GreekGod` benutzerdefinierten Objekten. Datenvorlagen werden so definiert, dass `GreekGod` Objekte und `GreekHero` Objekte jeweils mit einer Gold-und einer Zyan-Vordergrundfarbe angezeigt werden.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
