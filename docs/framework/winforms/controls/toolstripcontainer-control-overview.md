---
title: "Übersicht über das ToolStripContainer-Steuerelement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a1a4c9c77e1f347f95c0a5e17ab0d37e0013d6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="toolstripcontainer-control-overview"></a>Übersicht über das ToolStripContainer-Steuerelement
Ein <xref:System.Windows.Forms.ToolStripContainer> weist Bereiche auf die Links, rechts, oben und unten Seiten zum Positionieren und rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, und <xref:System.Windows.Forms.StatusStrip> Steuerelemente. Mehrere <xref:System.Windows.Forms.ToolStrip>-Steuerelemente werden vertikal gestapelt, wenn sie im linken oder rechten <xref:System.Windows.Forms.ToolStripContainer> abgelegt werden. Wenn Sie sie im oberen oder unteren <xref:System.Windows.Forms.ToolStripContainer> ablegen, werden sie horizontal gestapelt. Sie können das zentrale <xref:System.Windows.Forms.ToolStripContentPanel> von <xref:System.Windows.Forms.ToolStripContainer> verwenden, um herkömmliche Steuerelemente auf dem Formular zu positionieren.  
  
 Einige oder alle <xref:System.Windows.Forms.ToolStripContainer>-Steuerelemente sind zur Entwurfszeit direkt auswählbar und können gelöscht werden. Jeder Bereich von einer <xref:System.Windows.Forms.ToolStripContainer> ist erweiterbar und reduzierbar und passt seine Größe an die die darin enthaltenen Steuerelemente.  
  
### <a name="important-toolstripcontainer-members"></a>Wichtige ToolStripContainer-Member  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Ruft den unteren Bereich der <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Ruft ab oder legt einen Wert, der angibt, ob im unteren Bereich, der die <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|Ruft den linken Bereich der <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Ruft ab oder legt einen Wert, der angibt, ob der linke Bereich des der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Ruft den rechten Bereich der <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Ruft ab oder legt einen Wert, der angibt, ob im rechten Bereich, der die <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Ruft den oberen Bereich der <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Ruft ab oder legt einen Wert, der angibt, ob der obere Bereich von der <xref:System.Windows.Forms.ToolStripContainer> sichtbar ist.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
