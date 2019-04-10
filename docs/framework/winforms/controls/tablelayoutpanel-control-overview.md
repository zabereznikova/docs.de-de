---
title: Übersicht über das TableLayoutPanel-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: 65daba0ce1a6f1c37fb257c1029396577821aad9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295366"
---
# <a name="tablelayoutpanel-control-overview"></a>Übersicht über das TableLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement ordnet seinen Inhalt in einem Raster an. Da das Layout sowohl zur Entwurfszeit als auch zur Laufzeit ausgeführt wird, kann es sich dynamisch ändern, wenn sich die Anwendungsumgebung ändert. Dadurch können sich die Steuerelemente im Bereich proportional in der Größe anpassen, sodass sie auf Änderungen wie die Größenanpassung des übergeordneten Steuerelements oder eine durch Lokalisierung veränderte Textlänge reagieren.  
  
 Jedes Windows Forms-Steuerelement kann ein untergeordnetes Element des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements sein, einschließlich anderer Instanzen von <xref:System.Windows.Forms.TableLayoutPanel>. Dadurch können Sie anspruchsvolle Layouts erstellen, die sich zur Laufzeit an Änderungen anpassen.  
  
 Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement kann je nach Wert der Eigenschaften <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> und <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> erweitert werden, sodass neue Steuerelemente hinzugefügt werden können. Indem Sie die <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>-Eigenschaft oder die <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>-Eigenschaft auf den Wert 0 festlegen, geben Sie an, dass der <xref:System.Windows.Forms.TableLayoutPanel> in der entsprechenden Richtung ungebunden ist.  
  
 Außerdem können Sie festlegen, in welche Richtung (horizontal oder vertikal) das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement erweitert wird, wenn es bereits mit untergeordneten Steuerelementen gefüllt ist. Standardmäßig wird das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement nach unten erweitert, indem Zeilen hinzufügt werden.  
  
 Wenn Sie Zeilen und Spalten ein anderes Verhalten als das Standardverhalten zuweisen möchten, können Sie deren Eigenschaften mithilfe der <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>-Eigenschaft und <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>-Eigenschaft steuern. Sie können die Eigenschaften von Zeilen oder Spalten individuell festlegen.  
  
 Das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fügt seinen untergeordneten Steuerelementen folgende Eigenschaften hinzu: `Cell`, `Column`, `Row`, `ColumnSpan` und `RowSpan`.  
  
 Sie können Zellen im <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement zusammenführen, indem Sie die `ColumnSpan`-Eigenschaft oder `RowSpan`-Eigenschaft für ein untergeordnetes Steuerelement festlegen.  
  
1. [Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [Vorgehensweise: Überspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutSettings>
- [Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Vorgehensweise: Erstellen von in der Größe veränderbaren Windows Forms für die Dateneingabe](how-to-create-a-resizable-windows-form-for-data-entry.md)
- [Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement](best-practices-for-the-tablelayoutpanel-control.md)
