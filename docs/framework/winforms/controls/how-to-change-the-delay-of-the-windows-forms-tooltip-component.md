---
title: Ändern der Verzögerung der ToolTip-Komponente
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
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746589"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms
Es gibt mehrere Delay-Werte, die Sie für eine Windows Forms <xref:System.Windows.Forms.ToolTip> Komponente festlegen können. Die Maßeinheit für alle diese Eigenschaften beträgt Millisekunden. Die <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>-Eigenschaft bestimmt, wie lange der Benutzer auf das zugeordnete Steuerelement zeigen muss, damit die QuickInfo-Zeichenfolge angezeigt wird. Mit der <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>-Eigenschaft wird die Anzahl der Millisekunden festgelegt, die für nachfolgende QuickInfo-Zeichen folgen benötigt werden Die <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>-Eigenschaft bestimmt, wie lange die QuickInfo-Zeichenfolge angezeigt wird. Sie können diese Werte einzeln festlegen oder indem Sie den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>-Eigenschaft festlegen. die anderen Verzögerungs Eigenschaften werden basierend auf dem Wert festgelegt, der der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>-Eigenschaft zugewiesen ist. Wenn <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> z. b. auf den Wert n festgelegt ist, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> auf N festgelegt ist, wird <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> auf den Wert <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividiert durch 5 (oder N/5) festgelegt, und <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> wird auf einen Wert festgelegt, der fünfmal den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>-Eigenschaft (oder 5N) ist.  
  
### <a name="to-set-the-delay"></a>So legen Sie die Verzögerung fest  
  
1. Legen Sie die folgenden Eigenschaften fest, wie in diesem Beispiel gezeigt.  
  
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
- [Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [ToolTip-Komponente](tooltip-component-windows-forms.md)
