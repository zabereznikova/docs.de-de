---
title: "Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48bb8c08fa02a54f9bfd3febbe99f683fd68d7f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms
Es gibt mehrere Verzögerungswerte, die Sie für eine Windows Forms festlegen können <xref:System.Windows.Forms.ToolTip> Komponente. Die Maßeinheit für alle diese Eigenschaften ist Millisekunden. Die <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> Eigenschaft bestimmt, wie lange der Benutzer zeigen muss, auf das zugeordnete Steuerelement für die QuickInfo-Zeichenfolge, die angezeigt werden. Die <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> Eigenschaft legt die Anzahl der Millisekunden dauert die QuickInfo-Zeichenfolgen angezeigt werden, während die Maus von einem zugeordneten QuickInfo-Steuerelement in einen anderen bewegt. Die <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> Eigenschaft bestimmt die Zeitdauer, die die Zeichenfolge für die QuickInfo wird angezeigt. Sie können diese Werte festlegen, einzeln oder durch Festlegen des Werts, der die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Eigenschaft; die anderen Eigenschaften werden auf der Basis der zugewiesene Wert Verzögerung der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Eigenschaft. Z. B., wenn <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> festgelegt ist, auf einen Wert von N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> festgelegt ist, bis N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> festgelegt ist, auf den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividiert durch fünf (oder N/5) und <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> festgelegt ist, auf einen Wert, der fünf Mal den Wert der die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> -Eigenschaft (oder 5N).  
  
### <a name="to-set-the-delay"></a>Die Verzögerung festlegen  
  
1.  Die folgenden Eigenschaften fest, wie im folgenden Beispiel gezeigt.  
  
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
 [Übersicht über die ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
