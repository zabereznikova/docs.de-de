---
title: Übersicht über das FlowLayoutPanel-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 73767114da1c04222fb8ceaf812153421c4597aa
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425503"
---
# <a name="flowlayoutpanel-control-overview"></a>Übersicht über das FlowLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement ordnet seinen Inhalt in horizontaler oder vertikaler Flussrichtung an. Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umgebrochen werden. Wahlweise können Sie den Inhalt auch abschneiden statt ihn umzubrechen.  
  
 Sie können die Flussrichtung angeben, indem Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>-Eigenschaft festlegen. Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement kehrt seine Flussrichtung in Layouts mit Leserichtung von rechts nach links (RTL) entsprechend um. Darüber hinaus können Sie angeben, ob der Inhalt des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements umgebrochen oder abgeschnitten wird, indem Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>-Eigenschaft festlegen.  
  
 Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement wird automatisch an seinen Inhalt angepasst, wenn Sie die <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft auf `true` festlegen. Es bietet auch eine **FlowBreak** Eigenschaft für seine untergeordneten Steuerelemente. Wenn Sie den Wert der FlowBreak-Eigenschaft auf `true` festlegen, ordnet das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement andere Steuerelemente nicht mehr in der aktuellen Flussrichtung an und bricht diese auch nicht mehr in die nächste Zeile oder Spalte um.  
  
 Jedes Windows Forms-Steuerelement kann ein untergeordnetes Element des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements sein, einschließlich anderer Instanzen von <xref:System.Windows.Forms.FlowLayoutPanel>. Dadurch sind Sie in der Lage, anspruchsvolle Layouts zu erstellen, die sich zur Laufzeit an die Maße des Formulars anpassen.  
  
 Siehe auch [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [FlowLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
