---
title: 'Vorgehensweise: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144520"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Vorgehensweise: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML
In diesem Beispiel wird gezeigt, wie zum Erstellen einer Ansicht einer Datensammlung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Sichten können für die Funktionen von gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die statische Ressource namens *platziert* ist definiert als eine Auflistung von *Ort* -Objekte, in denen die einzelnen *Ort* Objekt ist Bestand, der Namen einer Stadt und die Status. Das Präfix *Src* zugeordnet ist, auf den Namespace, in dem die Datenquelle *stellen* definiert ist. Das Präfix *Scm* ordnet `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` und *Dat* ordnet `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 Das folgende Beispiel erstellt einen Überblick über die Datensammlung, die durch den Namen der Stadt sortiert und gruppiert nach den Status an.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Die Ansicht kann dann eine Bindungsquelle, wie im folgenden Beispiel sein:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Für Bindungen an XML-Daten, die definiert, die einer <xref:System.Windows.Data.XmlDataProvider> Ressource stellen vor den Namen der XML-ein @-Symbols.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.CollectionViewSource>
- [Abrufen der Standardansicht einer Datenauflistung](how-to-get-the-default-view-of-a-data-collection.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
