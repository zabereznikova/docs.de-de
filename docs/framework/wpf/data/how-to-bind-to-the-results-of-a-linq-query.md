---
title: 'Vorgehensweise: Binden an die Ergebnisse einer LINQ-Abfrage'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644412"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Vorgehensweise: Binden an die Ergebnisse einer LINQ-Abfrage
Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage ausführen und dann Binden an die Ergebnisse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Listenfelder. Das erste Listenfeld enthält drei Listenelemente.  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 Das erste Listenfeld ein Element auswählen, wird der folgende Ereignishandler aufgerufen. In diesem Beispiel `Tasks` ist eine Sammlung von `Task` Objekte. Die `Task` -Klasse verfügt über eine Eigenschaft namens `Priority`. Dieser Ereignishandler ausgeführt wird, eine LINQ-Abfrage, die die Auflistung der zurückgibt `Task` Objekte, die den ausgewählten Priority-Wert und legt dann fest, dass die <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 Das zweite Listenfeld wird eine Bindung an die Sammlung erstellt, da die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Wert wird festgelegt, um `{Binding}`. Daher wird die zurückgegebene Auflistung (basierend auf den `myTaskTemplate` <xref:System.Windows.DataTemplate>).  
  
## <a name="see-also"></a>Siehe auch

- [Bereitstellen von Daten für die Bindung in XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Neues in WPF Version 4.5](../getting-started/whats-new.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
