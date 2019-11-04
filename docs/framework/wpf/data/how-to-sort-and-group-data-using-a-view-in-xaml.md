---
title: 'Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML'
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
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460125"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML
Dieses Beispiel zeigt, wie eine Ansicht einer Datensammlung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]erstellt wird. Sichten ermöglichen das Gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die statische Ressource mit dem Namen *Places* als eine Auflistung von *Place* -Objekten definiert, wobei jedes *Place* -Objekt aus einem Ortsnamen und dem-Zustand besteht. Das Präfix *src* wird dem Namespace zugeordnet, in dem die Datenquellen Speicher *Orte* definiert sind. Das Präfix *SCM* wird `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` zugeordnet, und *DAT* wird `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`zugeordnet.  
  
 Im folgenden Beispiel wird eine Ansicht der Datensammlung erstellt, die nach dem Namen der Stadt sortiert und nach dem-Status gruppiert ist.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Die Sicht kann dann eine Bindungs Quelle sein, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Für Bindungen an XML-Daten, die in einer <xref:System.Windows.Data.XmlDataProvider> Ressource definiert sind, muss dem XML-Namen ein @-Symbol vorangestellt sein.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.CollectionViewSource>
- [Abrufen der Standardansicht einer Datenauflistung](how-to-get-the-default-view-of-a-data-collection.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
