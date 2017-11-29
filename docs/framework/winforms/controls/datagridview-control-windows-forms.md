---
title: DataGridView-Steuerelement (Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08a0cc15cff39bb936a78db95c73568aa643d0b6
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="datagridview-control-windows-forms"></a>DataGridView-Steuerelement (Windows Forms)
Das `DataGridView`-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form. Sie können das `DataGridView`-Steuerelement verwenden, um schreibgeschützte Ansichten mit kleinen Datenmengen anzuzeigen, oder Sie können es skalieren, um bearbeitbare Ansichten von sehr umfangreichen Datasets anzuzeigen.  
  
 Es gibt mehrere Möglichkeiten zum Erweitern des `DataGridView`-Steuerelements, um Ihre Anwendungen mit benutzerdefinierten Verhaltensweisen auszustatten. So können Sie beispielsweise programmgesteuert Ihre eigenen Sortieralgorithmen angeben und eigene Zelltypen erstellen. Die Darstellung des `DataGridView`-Steuerelements kann mithilfe mehrerer Eigenschaften ganz einfach angepasst werden. Als Datenquelle können viele Arten von Datenspeichern verwendet werden, oder das `DataGridView`-Steuerelement kann ohne eine hieran gebundene Datenquelle ausgeführt werden.  
  
 In den Themen in diesem Abschnitt werden die Konzepte und Techniken beschrieben, die Sie verwenden können, um `DataGridView`-Features in Ihre Anwendungen einzubinden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 Enthält Themen, in denen die Architektur und die Kernkonzepte des `DataGridView`-Steuerelements in Windows Forms beschrieben werden.  
  
 [Standardfunktionalität des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 Beschreibt die Standarddarstellung und das Standardverhalten des `DataGridView`-Steuerelements von Windows Forms, wenn es an eine Datenquelle gebunden ist.  
  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Beschreibt die Spaltentypen im `DataGridView`-Steuerelement in Windows Forms, die verwendet werden, um Daten anzuzeigen und es dem Benutzer ermöglichen, Daten zu ändern oder hinzuzufügen.  
  
 [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Enthält Themen, in denen häufig verwendete Zellen-, Zeilen- und Spalteneigenschaften beschrieben werden.  
  
 [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.  
  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen beschrieben wird, wie das Steuerelement entweder manuell oder mit Daten aus einer externen Datenquelle gefüllt wird.  
  
 [Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen erläutert wird, wie die Größe von Zeilen und Spalten automatisch angepasst werden kann, um dem Zellinhalt oder der verfügbaren Breite des Steuerelements zu entsprechen.  
  
 [Sortieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 Unter diesen Themen werden die Sortierfunktionen des Steuerelements beschrieben.  
  
 [Dateneingabe im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen beschrieben wird, wie die Art und Weise geändert wird, in der Benutzer Daten im Steuerelement hinzufügen und diese ändern.  
  
 [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen die Auswahlfunktionen für Zellen, Zeilen und Spalten im Steuerelement beschrieben werden.  
  
 [Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 Enthält Themen, in denen die Programmierung mit Zellen-, Zeilen- und Spaltenobjekten beschrieben wird.  
  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen das benutzerdefinierte Zeichnen von `DataGridView`-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.  
  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in den erläutert wird, wie das Steuerelement effizient eingesetzt wird, um bei der Arbeit mit großen Datenmengen Leistungsprobleme zu vermeiden.  
  
 [Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie Benutzer per Tastatur und Maus mit dem `DataGridView`-Steuerelement interagieren können.  
  
 [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 Beschreibt, in welcher Weise das `DataGridView`-Steuerelement verbessert wurde, das das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt.  
  
 Siehe auch [mithilfe des Designers mit dem DataGridView-Steuerelement von Windows Forms](http://msdn.microsoft.com/library/ms171593\(v=vs.110\)).  
  
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente. Das <xref:System.Windows.Forms.DataGridView>-Steuerelement und die <xref:System.Windows.Forms.BindingSource>-Komponente sind auf eine enge Zusammenarbeit ausgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
