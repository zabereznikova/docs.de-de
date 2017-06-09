---
title: "&#220;bersicht &#252;ber das TableLayoutPanel-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TableLayoutPanel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Größenänderung"
  - "Layout [Windows Forms], TableLayoutPanel-Steuerelement"
  - "Größenveränderbare Steuerelemente"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Informationen über das TableLayoutPanel-Steuerelement"
  - "Windows Forms-Steuerelemente, Proportionale Größenänderung"
  - "Windows Forms, Proportionale Größenänderung von Steuerelementen"
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das TableLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ordnet seinen Inhalt in einem Raster an.  Da das Layout sowohl zur Entwurfszeit als auch zur Laufzeit ausgeführt wird, kann es sich dynamisch ändern, wenn sich die Anwendungsumgebung ändert.  Dadurch können sich die Steuerelemente im Bereich proportional in der Größe anpassen, sodass sie auf Änderungen wie die Größenanpassung des übergeordneten Steuerelements oder eine durch Lokalisierung veränderte Textlänge reagieren.  
  
 Jedes Windows Forms\-Steuerelement kann ein untergeordnetes Element des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements sein, einschließlich anderer Instanzen von <xref:System.Windows.Forms.TableLayoutPanel>.  Dadurch können Sie anspruchsvolle Layouts erstellen, die sich zur Laufzeit an Änderungen anpassen.  
  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement kann je nach Wert der Eigenschaften <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> und <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> erweitert werden, sodass neue Steuerelemente hinzugefügt werden können.  Indem Sie die <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>\-Eigenschaft oder die <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>\-Eigenschaft auf den Wert 0 festlegen, geben Sie an, dass der <xref:System.Windows.Forms.TableLayoutPanel> in der entsprechenden Richtung ungebunden ist.  
  
 Außerdem können Sie festlegen, in welche Richtung \(horizontal oder vertikal\) das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement erweitert wird, wenn es bereits mit untergeordneten Steuerelementen gefüllt ist.  Standardmäßig wird das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement nach unten erweitert, indem Zeilen hinzufügt werden.  
  
 Wenn Sie Zeilen und Spalten ein anderes Verhalten als das Standardverhalten zuweisen möchten, können Sie deren Eigenschaften mithilfe der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>\-Eigenschaft und <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>\-Eigenschaft steuern.  Sie können die Eigenschaften von Zeilen oder Spalten individuell festlegen.  
  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement fügt seinen untergeordneten Steuerelementen folgende Eigenschaften hinzu: `Cell`, `Column`, `Row`, `ColumnSpan` und `RowSpan`.  
  
 Sie können Zellen im <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement zusammenführen, indem Sie die `ColumnSpan`\-Eigenschaft oder `RowSpan`\-Eigenschaft für ein untergeordnetes Steuerelement festlegen.  
  
1.  [Gewusst wie: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel\-Steuerelement](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [Gewusst wie: Überspannen von Zeilen und Spalten in einem TableLayoutPanel\-Steuerelement](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
3.  [Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel\-Steuerelement](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
4.  [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
## Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutSettings>   
 [Gewusst wie: Entwerfen eines Windows Forms\-Layouts, das zur Lokalisierung gut geeignet ist](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)   
 [Gewusst wie: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)   
 [Empfohlene Vorgehensweisen für das TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)