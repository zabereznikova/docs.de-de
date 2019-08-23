---
title: Datenformatierung im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 5966f16238999655d6072c1127e5bf16aefde5e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969188"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Datenformatierung im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView> -Steuerelement ermöglicht die automatische Konvertierung zwischen Zellwerten und den Datentypen, die in den übergeordneten Spalten angezeigt werden. Text Feld Spalten zeigen z. b. Zeichen folgen Darstellungen von Datums-, Uhrzeit-, Zahlen-und Enumerationswerten an und Konvertieren vom Benutzer eingegebene Zeichen folgen Werte in die vom Datenspeicher benötigten Typen.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formatieren mit der DataGridViewCellStyle-Klasse  
 Das <xref:System.Windows.Forms.DataGridView> -Steuerelement stellt grundlegende Datenformatierung von Zellwerten über die <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse bereit. Sie können die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> -Eigenschaft verwenden, um Datums-, Uhrzeit-, Zahlen-und Enumerationswerte für die aktuelle Standard Kultur mithilfe der in [Formatierungs Typen](../../../standard/base-types/formatting-types.md)beschriebenen Formatspezifizierer zu formatieren. Sie können diese Werte auch für bestimmte Kulturen formatieren, <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> indem Sie die-Eigenschaft verwenden. Das angegebene Format wird sowohl zum Anzeigen von Daten als auch zum Analysieren von Daten verwendet, die vom Benutzer im angegebenen Format eingegeben werden.  
  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse stellt zusätzliche Formatierungs Eigenschaften für WordWrap, Textausrichtung und die benutzerdefinierte Anzeige von NULL-Daten bankwerten bereit. Weitere Informationen finden Sie unter [Vorgehensweise: Formatieren Sie die Daten im Windows Forms DataGridView-Steuer](how-to-format-data-in-the-windows-forms-datagridview-control.md)Element.  
  
## <a name="formatting-with-the-cellformatting-event"></a>Formatieren mit dem cellformatierung-Ereignis  
 Wenn die grundlegende Formatierung nicht Ihren Anforderungen entspricht, können Sie eine benutzerdefinierte Datenformatierung in einem Handler für <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> das-Ereignis bereitstellen. Das <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> an den Handler über gegebene verfügt <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> über eine-Eigenschaft, die anfänglich den Zellwert enthält. Normalerweise wird dieser Wert automatisch in den Anzeigetyp konvertiert. Wenn Sie den Wert selbst konvertieren möchten, <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> legen Sie die-Eigenschaft auf einen Wert des Anzeige Typs fest.  
  
> [!NOTE]
> Wenn für die Zelle eine Format Zeichenfolge aktiviert ist, überschreibt Sie die Änderung des <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Eigenschafts Werts, es sei <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> denn, `true`Sie legen die-Eigenschaft auf fest.  
  
 Das <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis ist auch nützlich, wenn Sie Eigenschaften für <xref:System.Windows.Forms.DataGridViewCellStyle> einzelne Zellen basierend auf ihren Werten festlegen möchten. Weitere Informationen finden Sie unter [Vorgehensweise: Passen Sie die Datenformatierung im Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)-Steuerelement an.  
  
 Wenn die standardmäßige Verarbeitung von benutzerdefinierten Werten nicht Ihren Anforderungen entspricht, können Sie das <xref:System.Windows.Forms.DataGridView.CellParsing> -Ereignis <xref:System.Windows.Forms.DataGridView> des-Steuer Elements behandeln, um eine benutzerdefinierte-Verarbeitung bereitzustellen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Formatieren von Daten im Windows Forms DataGridView-Steuerelement](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuerelement](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
