---
title: Datenformatierung im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 0016b87add6f20223bdeda72f10ac94b74ec9fcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737857"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Datenformatierung im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement ermöglicht die automatische Konvertierung zwischen Zellen und die Datentypen, die die übergeordneten Spalten angezeigt. Text-Feld-Spalten, z. B. zeichenfolgenentsprechungen von Datums-, Uhrzeit, Zahl und Enumerationswerte anzuzeigen, und Konvertieren der freien Eingabe Zeichenfolgenwerte in der Typen, die vom Datenspeicher erforderlich.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formatieren mit der DataGridViewCellStyle-Klasse  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet grundlegende Daten zur Formatierung der Zellenwerte über die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse. Können Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Eigenschaft zur Formatierung Date, Time, Anzahl und Enumeration von Werten für die aktuelle Standardkultur, die über die in beschriebenen Formatbezeichner [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md). Sie können auch formatieren, diese Werte für bestimmte Kulturen mithilfe der <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> Eigenschaft. Das angegebene Format wird verwendet, Daten anzeigen und Analysieren von Daten, die der Benutzer, im angegebenen Format eingibt.  
  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse bietet zusätzliche Formatierungseigenschaften für die Wordwrap textausrichtung und die benutzerdefinierte Anzeige von Datenbank-Nullwerte. Weitere Informationen finden Sie unter [Vorgehensweise: Formatieren von Daten in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Formatieren mit dem CellFormatting-Ereignis  
 Bei der einfache Formatierung nicht Ihre Anforderungen erfüllt, können Sie angeben, dass benutzerdefinierte Formatieren von Daten in einen Handler für die <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis. Die <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> an den Handler übergebenen verfügt über eine <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Eigenschaft, die zunächst der Wert der Zelle enthält. Normalerweise ist dieser Wert automatisch auf den Anzeigetyp konvertiert. Um den Wert selbst zu konvertieren, legen Sie die <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Eigenschaft mit einem Wert des Anzeigetyps.  
  
> [!NOTE]
>  Wenn eine Formatzeichenfolge für die Zelle gilt, überschreibt es die Änderung des der <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Eigenschaftswert, es sei denn, Sie legen die <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> Eigenschaft, um `true`.  
  
 Die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis ist auch nützlich, wenn Sie festlegen möchten <xref:System.Windows.Forms.DataGridViewCellStyle> Eigenschaften für einzelne Zellen basierend auf ihren Werten. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Wenn die Standard-Analyse von Benutzer angegebene Werte nicht Ihre Anforderungen erfüllt, können Sie behandeln die <xref:System.Windows.Forms.DataGridView.CellParsing> Ereignis die <xref:System.Windows.Forms.DataGridView> Steuerelement zum Analysieren von benutzerdefinierten zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Formatieren von Daten in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
