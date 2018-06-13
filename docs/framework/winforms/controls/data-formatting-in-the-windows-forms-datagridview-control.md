---
title: Datenformatierung im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: ae1947cf7c3825553837fa5f1ee288114988d28f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527773"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Datenformatierung im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ermöglicht die automatische Konvertierung zwischen Zellenwerten und die Datentypen, die den übergeordneten Spalten angezeigt. Feld Textspalten, z. B. zeichenfolgenentsprechungen von Date, Time, Anzahl und Enumerationswerte anzuzeigen, und konvertieren Benutzereingaben Zeichenfolgenwerte in der Typen, die erforderlich sind, durch den Datenspeicher.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formatierung mit der DataGridViewCellStyle-Klasse  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement stellt grundlegende datenformatierung von Zellenwerten durch die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse. Sie können die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Eigenschaft zur Formatierung von Datum, Uhrzeit, Zahl und Enumeration Werten für die aktuelle Standardkultur mithilfe von Formatbezeichnern, die in beschriebenen [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md). Sie können ebenso formatieren, diese Werte für bestimmte Kulturen mithilfe der <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> Eigenschaft. Das angegebene Format wird verwendet, zum Anzeigen von Daten und Daten zu analysieren, die der Benutzer, im angegebenen Format eingibt.  
  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse bietet zusätzliche Formatierungseigenschaften für Wordwrap, Ausrichtung und die benutzerdefinierte Anzeige der null-Datenbankwerte. Weitere Informationen finden Sie unter [Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Mit dem Ereignis CellFormatting Formatierung  
 Bei der einfache Formatierung nicht Ihren Anforderungen entspricht, können Sie angeben, dass benutzerdefinierte Formatieren von Daten in einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis. Die <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> an den Ereignishandler übergeben hat eine <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> -Eigenschaft, die zunächst der Wert der Zelle enthält. Normalerweise ist dieser Wert automatisch in den Anzeigetyp konvertiert. Um den Wert selbst zu konvertieren, legen Sie die <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Eigenschaft auf einen Wert des Anzeigetyps.  
  
> [!NOTE]
>  Wenn eine Formatzeichenfolge für die Zelle gültig ist, überschreibt er die Änderung von der <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Eigenschaftswert, es sei denn, Sie legen die <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> Eigenschaft `true`.  
  
 Die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis ist auch nützlich, wenn Sie festlegen möchten <xref:System.Windows.Forms.DataGridViewCellStyle> Eigenschaften für einzelne Zellen basierend auf ihren Werten. Weitere Informationen finden Sie unter [wie: Anpassen der Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Wenn die Standard-Analyse von Benutzer angegebene Werte nicht Ihren Anforderungen entspricht, können Sie behandeln die <xref:System.Windows.Forms.DataGridView.CellParsing> -Ereignis für die <xref:System.Windows.Forms.DataGridView> Steuerelement zum Analysieren von benutzerdefinierten zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
