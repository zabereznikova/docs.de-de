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
ms.openlocfilehash: 62b0f46e710180ef53fba086bdfed9e7cf45be9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610603"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Vorgehensweise: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML
In diesem Beispiel wird gezeigt, wie zum Erstellen einer Ansicht einer Datensammlung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Sichten können für die Funktionen von gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die statische Ressource namens *platziert* ist definiert als eine Auflistung von *Ort* -Objekte, in denen die einzelnen *Ort* Objekt ist Bestand, der Namen einer Stadt und die Status. Das Präfix *Src* zugeordnet ist, auf den Namespace, in dem die Datenquelle *stellen* definiert ist. Das Präfix *Scm* ordnet `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` und *Dat* ordnet `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 Das folgende Beispiel erstellt einen Überblick über die Datensammlung, die durch den Namen der Stadt sortiert und gruppiert nach den Status an.  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Die Ansicht kann dann eine Bindungsquelle, wie im folgenden Beispiel sein:  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Für Bindungen an XML-Daten, die definiert, die einer <xref:System.Windows.Data.XmlDataProvider> Ressource stellen vor den Namen der XML-ein @-Symbols.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Data.CollectionViewSource>
- [Abrufen der Standardansicht einer Datenauflistung](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)
- [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
