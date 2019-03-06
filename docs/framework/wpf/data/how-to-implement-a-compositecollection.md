---
title: 'Vorgehensweise: Implementieren einer CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 71d55a23711b116a91386a537d5572e8506d4c6b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372671"
---
# <a name="how-to-implement-a-compositecollection"></a>Vorgehensweise: Implementieren einer CompositeCollection
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mehrere Auflistungen und Elemente anzeigen, wie eine Liste mit den <xref:System.Windows.Data.CompositeCollection> Klasse. In diesem Beispiel `GreekGods` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `GreekGod` benutzerdefinierter Objekte. Datenvorlagen werden definiert, damit `GreekGod` Objekte und `GreekHero` Objekte werden mit einem "Gold" und eine Zyan Vordergrundfarbe.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
