---
title: 'Gewusst wie: Definieren einer Tabelle mit XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 350dff0b6ea9d92e919e45e4f46cf888f44f6212
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a>Gewusst wie: Definieren einer Tabelle mit XAML
Im folgende Beispiel wird veranschaulicht, wie definiert eine <xref:System.Windows.Documents.Table> mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Die Beispieltabelle enthält vier Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und mehrere Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> Elemente) enthält sowohl Daten als auch Titel-, Kopf- und Fußzeileninformationen.  Zeilen enthalten sein müssen, einem <xref:System.Windows.Documents.TableRowGroup> Element.  Jede Zeile in der Tabelle besteht aus einer oder mehrerer Zellen (dargestellt durch <xref:System.Windows.Documents.TableCell> Elemente).  Inhalt in eine Tabellenzelle muss enthalten sein, einem <xref:System.Windows.Documents.Block> Element; in diesem Fall <xref:System.Windows.Documents.Paragraph> Elemente verwendet werden.  Die Tabelle enthält außerdem einen Link (dargestellt durch die <xref:System.Windows.Documents.Hyperlink> Element) in der Fußzeile.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Die folgende Abbildung zeigt, wie die in diesem Beispiel definierte Tabelle gerendert wird.  
  
 ![Gerenderte Tabelle.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
