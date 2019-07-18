---
title: 'Vorgehensweise: Implementieren einer CompositeCollection-Klasse'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931675"
---
# <a name="how-to-implement-a-compositecollection"></a>Vorgehensweise: Implementieren einer CompositeCollection-Klasse
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
