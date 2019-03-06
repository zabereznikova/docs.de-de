---
title: 'Vorgehensweise: Definieren einer Tabelle mit XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 7398af6fddae56238e1af3ee4e726420c01ab7ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376922"
---
# <a name="how-to-define-a-table-with-xaml"></a>Vorgehensweise: Definieren einer Tabelle mit XAML
Im folgende Beispiel wird veranschaulicht, wie zum Definieren einer <xref:System.Windows.Documents.Table> mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Die Beispieltabelle enthält vier Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und mehrere Zeilen (durch dargestellt <xref:System.Windows.Documents.TableRow> Elemente) enthält sowohl Daten als auch Titel, Header und Footerinformationen.  Zeilen müssen enthalten sein, einem <xref:System.Windows.Documents.TableRowGroup> Element.  Jede Zeile in der Tabelle besteht aus einer oder mehrerer Zellen (dargestellt durch <xref:System.Windows.Documents.TableCell> Elemente).  Inhalte in einer Tabellenzelle muss enthalten sein, einem <xref:System.Windows.Documents.Block> Element; in diesem Fall <xref:System.Windows.Documents.Paragraph> Elemente verwendet werden.  Die Tabelle enthält außerdem einen Link (dargestellt durch die <xref:System.Windows.Documents.Hyperlink> Element) in der Fußzeile.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Die folgende Abbildung zeigt, wie die in diesem Beispiel definierte Tabelle gerendert wird.  
  
 ![Gerenderte Tabelle.](./media/tableeg.png "TableEG")
