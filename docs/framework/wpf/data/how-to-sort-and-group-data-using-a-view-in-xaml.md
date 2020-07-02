---
title: 'Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML'
description: Erfahren Sie, wie Sie eine Ansicht einer Datensammlung zum Gruppieren, Sortieren und Filtern im Windows Presentation Foundation (WPF) erstellen können.
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
ms.openlocfilehash: a4f8e2de9345dba8e4ea0d3a16a32d57a9adb55c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621677"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML
In diesem Beispiel wird gezeigt, wie eine Sicht einer Datensammlung in erstellt wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Sichten ermöglichen das Gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die statische Ressource mit dem Namen *Places* als eine Auflistung von *Place* -Objekten definiert, wobei jedes *Place* -Objekt aus einem Ortsnamen und dem-Zustand besteht. Das Präfix *src* wird dem Namespace zugeordnet, in dem die Datenquellen Speicher *Orte* definiert sind. Das Präfix *SCM* wird zugeordnet, `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` und *DAT* wird zugeordnet `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` .  
  
 Im folgenden Beispiel wird eine Ansicht der Datensammlung erstellt, die nach dem Namen der Stadt sortiert und nach dem-Status gruppiert ist.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Die Sicht kann dann eine Bindungs Quelle sein, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Für Bindungen an XML-Daten <xref:System.Windows.Data.XmlDataProvider> , die in einer Ressource definiert sind, muss dem XML-Namen ein @-Zeichen vorangestellt werden.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Data.CollectionViewSource>
- [Standardansicht einer Datensammlung erhalten](how-to-get-the-default-view-of-a-data-collection.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
