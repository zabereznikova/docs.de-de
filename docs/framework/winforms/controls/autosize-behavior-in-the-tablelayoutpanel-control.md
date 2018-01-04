---
title: Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06bd0686b31b52ccb8580a545910339d2e2cd5bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement
## <a name="distinct-autosize-behaviors"></a>Verschiedene AutoSize-Verhalten  
 Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement das automatische Größenanpassungsverhalten unterstützt, auf folgende Weise:  
  
-   Über die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft ein.  
  
-   Über die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> Eigenschaft auf die <xref:System.Windows.Forms.TableLayoutPanel> Zeilen- und Spaltenstile des Steuerelements.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>Der AutoSize-Eigenschaft mit Zeilen- und Spaltenformate  
 Die folgende Tabelle beschreibt die Interaktion zwischen der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft und die <xref:System.Windows.Forms.TableLayoutPanel> Zeilen- und Spaltenstile des Steuerelements.  
  
|AutoSize-Einstellung|Stil-Aktivität|  
|----------------------|-----------------------|  
|`false`|Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement geht von links nach rechts und weist Speicherplatz für die Spalte oder Zeile oder in der folgenden Reihenfolge.<br /><br /> 1.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.SizeType.Absolute>, die Anzahl der Pixel, die vom angegebenen <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> zugeordnet ist.<br />2.  Wenn die <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.SizeType.AutoSize>, die Anzahl der Pixel des untergeordneten Steuerelements zurückgegebene <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methode zugeordnet ist.<br />3.  Nach der Speicherplatz für alle <xref:System.Windows.Forms.SizeType.Absolute> und <xref:System.Windows.Forms.SizeType.AutoSize> Spalten oder Zeilen belegt, alle Spalten oder Zeilen mit <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> festgelegt <xref:System.Windows.Forms.SizeType.Percent> werden verwendet, um den verbleibenden freien Speicherplatz proportional zu verteilen|  
|`true`|Ähnelt der vorherigen Interaktion, mit der Ausnahme, die <xref:System.Windows.Forms.SizeType.Percent> Spalten oder Zeilen erhalten Sie einen automatische größenanpassung Aspekt.<br /><br /> Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement nach unten erweitert die Spalte oder Zeile ausreichend freien Speicherplatz zu erstellen, damit keine Spalte oder Zeile mit <xref:System.Windows.Forms.SizeType.Percent> Styling clips seinen Inhalt. Die <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement ordnet den neuen Platz proportional anhand der <xref:System.Windows.Forms.ColumnStyle.Width%2A> oder <xref:System.Windows.Forms.RowStyle.Height%2A> Eigenschaft.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Übersicht über das TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
