---
title: "Datenformatierung im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Daten [Windows Forms], Formatieren in Datenblättern"
  - "Datenblätter, Formatieren von Daten"
  - "DataGridView-Steuerelement [Windows Forms], Formatieren von Daten"
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Datenformatierung im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ermöglicht die automatische Konvertierung zwischen Zellenwerten und den Datentypen, die in den übergeordneten Spalten angezeigt werden.  In den Textfeldspalten werden beispielsweise Zeichenfolgenentsprechungen von Datums\-, Uhrzeit\-, Zahlen\- und Enumerationswerten angezeigt und vom Benutzer eingegebene Zeichenfolgenwerte in die für den Datastore erforderlichen Typen konvertiert.  
  
## Formatieren mit der DataGridViewCellStyle\-Klasse  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt grundlegende Datenformatierungen von Zellenwerten durch die <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse bereit.  Mit der <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>\-Eigenschaft können Sie Datums\-, Uhrzeit\-, Zahlen\- und Enumerationswerte für die aktuelle Standardkultur mithilfe der unter [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md) beschriebenen Formatspezifizierer formatieren.  Sie können diese Werte auch für bestimmte Kulturen mithilfe der <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>\-Eigenschaft formatieren.  Das angegebene Format wird sowohl zur Anzeige von Daten als auch zur Analyse von Daten verwendet, die der Benutzer im angegebenen Format eingibt.  
  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse stellt zusätzliche Formatierungseigenschaften für den Zeilenumbruch, die Textausrichtung und die benutzerdefinierte Anzeige von NULL\-Datenbankwerten bereit.  Weitere Informationen finden Sie unter [Gewusst wie: Formatieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## Formatieren mit dem CellFormatting\-Ereignis  
 Wenn die grundlegende Formatierung nicht Ihren Vorstellungen entspricht, können Sie in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>\-Ereignis benutzerdefinierte Datenformatierungen bereitstellen.  Das an den Handler übergebene <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> verfügt über eine <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>\-Eigenschaft, die anfangs den Zellenwert enthält.  Normalerweise wird dieser Wert automatisch in den Anzeigetyp konvertiert.  Um den Wert selbst zu konvertieren, legen Sie die <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>\-Eigenschaft auf einen Wert des Anzeigetyps fest.  
  
> [!NOTE]
>  Wenn für die Zelle eine Formatzeichenfolge ausgewählt ist, wird der geänderte <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>\-Eigenschaftswert damit überschrieben, sofern Sie die <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A>\-Eigenschaft nicht auf `true` festlegen.  
  
 Das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis ist außerdem hilfreich, wenn Sie <xref:System.Windows.Forms.DataGridViewCellStyle>\-Eigenschaften für einzelne Zellen anhand ihrer Werte festlegen möchten.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Wenn die herkömmliche Analyse der vom Benutzer angegebenen Werte nicht Ihren Vorstellungen entspricht, können Sie das <xref:System.Windows.Forms.DataGridView.CellParsing>\-Ereignis des <xref:System.Windows.Forms.DataGridView>\-Steuerelements behandeln, um eine benutzerdefinierte Analyse bereitzustellen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Formatieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)