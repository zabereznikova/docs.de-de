---
title: 'Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: cf257cccd272c16c3d7c3d403456265444fc8ac8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345481"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms
Es gibt mehrere Verzögerungswerte, die Sie für eine Windows Forms festlegen können <xref:System.Windows.Forms.ToolTip> Komponente. Die Maßeinheit für alle diese Eigenschaften ist Millisekunden. Die <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> Eigenschaft bestimmt, wie lange der Benutzer zeigen muss, auf das zugeordnete Steuerelement für die QuickInfo-Zeichenfolge, die angezeigt werden. Die <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> Eigenschaft legt fest, die Anzahl der Millisekunden, die es für QuickInfo-Zeichenfolgen angezeigt werden dauert, wenn die Maus von einem zugeordneten QuickInfo-Steuerelement in einen anderen bewegt. Die <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> Eigenschaft bestimmt die Zeitdauer, die die QuickInfo-Zeichenfolge wird angezeigt. Sie können diese Werte festlegen, einzeln oder durch Festlegen des Werts, der die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> -Eigenschaft, die anderen Eigenschaften werden auf der Basis der zugewiesene Wert Verzögerung der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Eigenschaft. Z. B., wenn <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> festgelegt ist, auf einen Wert von N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> nastaven NA hodnotu N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> festgelegt ist, auf den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> durch fünf geteilt (oder N/5) und <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> nastaven NA hodnotu ein Wert, der fünf Mal der Wert ist die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> -Eigenschaft (oder 5N).  
  
### <a name="to-set-the-delay"></a>Um die Verzögerung festzulegen.  
  
1. Legen Sie die folgenden Eigenschaften an, wie im folgenden Beispiel gezeigt.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [ToolTip-Komponente](tooltip-component-windows-forms.md)
