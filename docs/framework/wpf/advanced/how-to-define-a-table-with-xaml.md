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
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="47dee-102">Vorgehensweise: Definieren einer Tabelle mit XAML</span><span class="sxs-lookup"><span data-stu-id="47dee-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="47dee-103">Im folgende Beispiel wird veranschaulicht, wie zum Definieren einer <xref:System.Windows.Documents.Table> mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47dee-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="47dee-104">Die Beispieltabelle enthält vier Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und mehrere Zeilen (durch dargestellt <xref:System.Windows.Documents.TableRow> Elemente) enthält sowohl Daten als auch Titel, Header und Footerinformationen.</span><span class="sxs-lookup"><span data-stu-id="47dee-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="47dee-105">Zeilen müssen enthalten sein, einem <xref:System.Windows.Documents.TableRowGroup> Element.</span><span class="sxs-lookup"><span data-stu-id="47dee-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="47dee-106">Jede Zeile in der Tabelle besteht aus einer oder mehrerer Zellen (dargestellt durch <xref:System.Windows.Documents.TableCell> Elemente).</span><span class="sxs-lookup"><span data-stu-id="47dee-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="47dee-107">Inhalte in einer Tabellenzelle muss enthalten sein, einem <xref:System.Windows.Documents.Block> Element; in diesem Fall <xref:System.Windows.Documents.Paragraph> Elemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47dee-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="47dee-108">Die Tabelle enthält außerdem einen Link (dargestellt durch die <xref:System.Windows.Documents.Hyperlink> Element) in der Fußzeile.</span><span class="sxs-lookup"><span data-stu-id="47dee-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47dee-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47dee-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="47dee-110">Die folgende Abbildung zeigt, wie die in diesem Beispiel definierte Tabelle gerendert:</span><span class="sxs-lookup"><span data-stu-id="47dee-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![Bildschirmabbildung von einer Tabelle mit XAML definiert.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
