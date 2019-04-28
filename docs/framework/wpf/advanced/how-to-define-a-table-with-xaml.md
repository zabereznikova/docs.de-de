---
title: 'Vorgehensweise: Definieren einer Tabelle mit XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 011f612527f0c9e89ec05643edbb95b2d908488c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776584"
---
# <a name="how-to-define-a-table-with-xaml"></a>Vorgehensweise: Definieren einer Tabelle mit XAML
Im folgende Beispiel wird veranschaulicht, wie zum Definieren einer <xref:System.Windows.Documents.Table> mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Die Beispieltabelle enthält vier Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und mehrere Zeilen (durch dargestellt <xref:System.Windows.Documents.TableRow> Elemente) enthält sowohl Daten als auch Titel, Header und Footerinformationen.  Zeilen müssen enthalten sein, einem <xref:System.Windows.Documents.TableRowGroup> Element.  Jede Zeile in der Tabelle besteht aus einer oder mehrerer Zellen (dargestellt durch <xref:System.Windows.Documents.TableCell> Elemente).  Inhalte in einer Tabellenzelle muss enthalten sein, einem <xref:System.Windows.Documents.Block> Element; in diesem Fall <xref:System.Windows.Documents.Paragraph> Elemente verwendet werden.  Die Tabelle enthält außerdem einen Link (dargestellt durch die <xref:System.Windows.Documents.Hyperlink> Element) in der Fußzeile.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Die folgende Abbildung zeigt, wie die in diesem Beispiel definierte Tabelle gerendert:  
  
 ![Bildschirmabbildung von einer Tabelle mit XAML definiert.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
