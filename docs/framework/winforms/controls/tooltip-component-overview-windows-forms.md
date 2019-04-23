---
title: Übersicht über die ToolTip-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 3fbe883501d1ce36ca25ea07631f98042f451e07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197307"
---
# <a name="tooltip-component-overview-windows-forms"></a>Übersicht über die ToolTip-Komponente (Windows Forms)
Die <xref:System.Windows.Forms.ToolTip>-Komponente in Windows Forms zeigt Text an, wenn der Benutzer auf Steuerelemente zeigt. Jedem Steuerelement kann eine QuickInfo zugeordnet werden. Ein Beispiel für die Verwendung dieser Komponente: um Speicherplatz auf einem Formular zu speichern, können Sie ein kleines Symbol auf einer Schaltfläche anzeigen und verwenden Sie eine QuickInfo, um die Funktion der Schaltfläche zu erklären.  
  
## <a name="working-with-the-tooltip-component"></a>Arbeiten mit der ToolTip-Komponente  
 Ein <xref:System.Windows.Forms.ToolTip> Komponente bietet eine `ToolTip` -Eigenschaft für mehrere Steuerelemente auf einem Windows Form oder einem anderen Container. Z. B., wenn Sie eine <xref:System.Windows.Forms.ToolTip> Komponente in einem Formular anzeigen "Geben Sie hier Ihre Namen" für eine <xref:System.Windows.Forms.TextBox> steuern und "Klicken Sie hier, um Änderungen zu speichern" für eine <xref:System.Windows.Forms.Button> Steuerelement.  
  
 Folgende Schlüsselmethoden der <xref:System.Windows.Forms.ToolTip> Komponente <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> und <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. Sie können die <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode, um die QuickInfos für Steuerelemente festzulegen. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen von QuickInfos für Steuerelemente in Windows Forms zur Entwurfszeit](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Die wichtigsten Eigenschaften sind <xref:System.Windows.Forms.ToolTip.Active%2A>, die muss festgelegt werden, um `true` für die QuickInfo angezeigt wird, und <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, wodurch die Zeitspanne, die die QuickInfo-Zeichenfolge angezeigt wird, wie lange muss der Benutzer auf das Steuerelement für die QuickInfo angezeigt wird, verweisen und wie er zu lang dauert, bis Weitere QuickInfo-Fenster angezeigt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente von Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolTip>
- [Vorgehensweise: Festlegen von QuickInfos für Steuerelemente in Windows Forms zur Entwurfszeit](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente von Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
