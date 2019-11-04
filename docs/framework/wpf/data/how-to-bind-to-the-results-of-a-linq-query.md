---
title: 'Gewusst wie: Binden an die Ergebnisse einer LINQ-Abfrage'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d21ac5f366e001ea76d6eda64ed62583248796f6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454417"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Gewusst wie: Binden an die Ergebnisse einer LINQ-Abfrage

In diesem Beispiel wird veranschaulicht, wie eine LINQ-Abfrage ausgeführt und anschließend an die Ergebnisse gebunden wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Listenfelder erstellt. Das erste Listenfeld enthält drei Listenelemente.

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

Wenn Sie ein Element aus dem ersten Listenfeld auswählen, wird der folgende Ereignishandler aufgerufen. In diesem Beispiel ist `Tasks` eine Auflistung von `Task`-Objekten. Die `Task`-Klasse verfügt über eine Eigenschaft mit dem Namen `Priority`. Dieser Ereignishandler führt eine LINQ-Abfrage aus, die die Auflistung von `Task` Objekten zurückgibt, die über den ausgewählten Prioritätswert verfügen, und legt diesen dann als <xref:System.Windows.FrameworkElement.DataContext%2A>fest:

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

Das zweite Listenfeld wird an diese Auflistung gebunden, da der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Wert auf `{Binding}`festgelegt ist. Daraufhin wird die zurückgegebene Auflistung (basierend auf der `myTaskTemplate` <xref:System.Windows.DataTemplate>) angezeigt.

## <a name="see-also"></a>Siehe auch

- [Bereitstellen von Daten für die Bindung in XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Neues in WPF Version 4.5](../getting-started/whats-new.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
