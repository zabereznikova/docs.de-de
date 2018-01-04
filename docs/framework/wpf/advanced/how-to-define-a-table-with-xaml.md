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
ms.workload: dotnet
ms.openlocfilehash: b932c7df822edabc5626f20af2bfc1eb3a7f93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a>Gewusst wie: Definieren einer Tabelle mit XAML
Im folgende Beispiel wird veranschaulicht, wie definiert eine <xref:System.Windows.Documents.Table> mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Die Beispieltabelle enthält vier Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und mehrere Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> Elemente) enthält sowohl Daten als auch Titel-, Kopf- und Fußzeileninformationen.  Zeilen enthalten sein müssen, einem <xref:System.Windows.Documents.TableRowGroup> Element.  Jede Zeile in der Tabelle besteht aus einer oder mehrerer Zellen (dargestellt durch <xref:System.Windows.Documents.TableCell> Elemente).  Inhalt in eine Tabellenzelle muss enthalten sein, einem <xref:System.Windows.Documents.Block> Element; in diesem Fall <xref:System.Windows.Documents.Paragraph> Elemente verwendet werden.  Die Tabelle enthält außerdem einen Link (dargestellt durch die <xref:System.Windows.Documents.Hyperlink> Element) in der Fußzeile.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Die folgende Abbildung zeigt, wie die in diesem Beispiel definierte Tabelle gerendert wird.  
  
 ![Gerenderte Tabelle.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
