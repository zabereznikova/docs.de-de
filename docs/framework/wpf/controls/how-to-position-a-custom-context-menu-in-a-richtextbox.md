---
title: "Gewusst wie: Positionieren eines benutzerdefinierten Kontextmenüs in einem \"RichTextBox\"-Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4651953ec8ae6373b9a6946b31f96213bec570cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a>Gewusst wie: Positionieren eines benutzerdefinierten Kontextmenüs in einem "RichTextBox"-Element
In diesem Beispiel wird gezeigt, wie zum Positionieren eines benutzerdefinierten Kontextmenüs für eine <xref:System.Windows.Controls.RichTextBox>.  
  
 Bei der Implementierung eines benutzerdefinierten Kontextmenüs für ein **RichTextBox**-Element sind Sie verantwortlich für die Positionierung des Kontextmenüs.  Standardmäßig wird ein benutzerdefiniertes Kontextmenü in der Mitte des **RichTextBox**-Elements geöffnet.  
  
## <a name="example"></a>Beispiel  
 Um das Standardverhalten für die Platzierung außer Kraft setzen, fügen Sie einen Listener für die <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignis.  Im folgenden Beispiel wird veranschaulicht, wie dies programmgesteuert erfolgt.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einer Implementierung der entsprechenden <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignislistener.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
