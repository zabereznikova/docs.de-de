---
title: Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: 466edeee5f45ec72ef265ef4855049c7852641b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954348"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement
## <a name="distinct-autosize-behaviors"></a>Verschiedene AutoSize-Verhalten  
 Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement das automatische Größenanpassungsverhalten unterstützt, es gibt folgende Möglichkeiten:  
  
- Durch die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft  
  
- Über die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft für die <xref:System.Windows.Forms.TableLayoutPanel> Zeilen- und Spaltenstile des Steuerelements.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>Der AutoSize-Eigenschaft mit Zeilen- und Spaltenstile  
 Die folgende Tabelle beschreibt die Interaktion zwischen der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft und die <xref:System.Windows.Forms.TableLayoutPanel> Zeilen- und Spaltenstile des Steuerelements.  
  
|AutoSize-Einstellung|-Interaktion|  
|----------------------|-----------------------|  
|`false`|Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement geht von links nach rechts, und ordnet Platz für die Spalte oder Zeile in der folgenden Reihenfolge.<br /><br /> 1.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.SizeType.Absolute>, die Anzahl der Pixel, die anhand des <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> zugeordnet ist.<br />2.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.SizeType.AutoSize>, die Anzahl der Pixel des untergeordneten Steuerelements zurückgegebenes <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methode zugeordnet ist.<br />3.  Nach der Speicherplatz für alle <xref:System.Windows.Forms.SizeType.Absolute> und <xref:System.Windows.Forms.SizeType.AutoSize> Spalten oder Zeilen zugewiesen, alle Spalten oder Zeilen mit <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> festgelegt <xref:System.Windows.Forms.SizeType.Percent> werden verwendet, um den verbleibenden freien Platz proportional zu verteilen.|  
|`true`|Ähnelt der vorherigen Interaktion, mit der Ausnahme, die <xref:System.Windows.Forms.SizeType.Percent> Spalten oder Zeilen erhalten Sie einen Aspekt der automatischen größenanpassung.<br /><br /> Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement erweitert wird, die Spalte oder Zeile ausreichend freien Speicherplatz, zu erstellen, damit keine Spalten oder Zeilen mit <xref:System.Windows.Forms.SizeType.Percent> Formatierung schneidet, dessen Inhalt. Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement weist die neuen Platz proportional anhand der <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> Eigenschaft.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TableLayoutPanel>
- [Übersicht über das TableLayoutPanel-Steuerelement](tablelayoutpanel-control-overview.md)
