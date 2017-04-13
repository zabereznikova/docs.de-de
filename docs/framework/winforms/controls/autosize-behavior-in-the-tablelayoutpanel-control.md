---
title: "Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Automatische Größenanpassung"
  - "AutoSize-Eigenschaft, TableLayoutPanel-Steuerelement"
  - "AutoSizeMode-Eigenschaft"
  - "Steuerelemente [Windows Forms], Größe anpassen"
  - "Layout [Windows Forms], AutoSize"
  - "Lokalisieren von Formularen"
  - "Größe anpassen, Automatisch"
  - "TableLayoutPanel-Steuerelement [Windows Forms], AutoSize-Verhalten"
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement
## Verschiedene AutoSize\-Verhalten  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement unterstützt das automatische Größenanpassungsverhalten auf die folgenden Weisen:  
  
-   Durch die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft;  
  
-   Durch die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>\-Eigenschaft für die Spalten\- und Zeilenstile des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  
  
### Die AutoSize\-Eigenschaft mit Zeilen\- und Spaltenstilen  
 In der folgenden Tabelle wird die Interaktion zwischen der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft und den Spalten\- und Zeilenstilen des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements beschrieben.  
  
|AutoSize\-Einstellung|Stilinteraktion|  
|---------------------------|---------------------|  
|`false`|Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement geht von links nach rechts vor und ordnet in folgender Reihenfolge Platz für die Spalte oder Zeile zu.<br /><br /> 1.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>\-Eigenschaft auf <xref:System.Windows.Forms.SizeType> festgelegt ist, wird die durch <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> angegebene Anzahl an Pixel zugeordnet.<br />2.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>\-Eigenschaft auf <xref:System.Windows.Forms.SizeType> festgelegt ist, wird die von der <xref:System.Windows.Forms.Control.GetPreferredSize%2A>\-Methode des untergeordneten Steuerelements zurückgegebene Anzahl an Pixel zugeordnet.<br />3.  Nachdem allen <xref:System.Windows.Forms.SizeType>\- und <xref:System.Windows.Forms.SizeType>\-Spalten und \-Zeilen Platz zugeordnet wurde, werden alle Spalten oder Zeilen, deren <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> auf <xref:System.Windows.Forms.SizeType> festgelegt ist, verwendet, um den verbleibenden freien Platz proportional zu verteilen.|  
|`true`|Vergleichbar mit der vorherigen Interaktion, abgesehen davon, dass <xref:System.Windows.Forms.SizeType>\-Spalten und \-Zeilen automatisch in der Größe angepasst werden.<br /><br /> Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement erweitert die Spalte oder Zeile, um so viel freien Platz zu schaffen, dass keine Inhalte von Spalten oder Zeilen mit dem Stil <xref:System.Windows.Forms.SizeType> abgeschnitten werden.  Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ordnet den neuen Platz proportional anhand der <xref:System.Windows.Forms.ColumnStyle.Width%2A>\-Eigenschaft oder <xref:System.Windows.Forms.RowStyle.Height%2A>\-Eigenschaft zu.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Übersicht über das TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)