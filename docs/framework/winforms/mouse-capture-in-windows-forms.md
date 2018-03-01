---
title: Mauserfassung in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7cc62780579c852aaa637a3ccc13ce2929423868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a>Mauserfassung in Windows Forms
*Mauseingaben* bezieht sich auf, wenn ein Befehl, der alle Mauseingaben hat. Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben, und zwar unabhängig davon, ob der Zeiger innerhalb seiner Grenzen befindet.  
  
## <a name="setting-mouse-capture"></a>Festlegen von Mauseingaben  
 In Windows Forms ist die Maus vom Steuerelement erfasst, wenn der Benutzer eine Maustaste für ein Steuerelement drückt, und die Maus vom Steuerelement freigegeben, wenn der Benutzer die Maustaste loslässt.  
  
 Die <xref:System.Windows.Forms.Control.Capture%2A> Eigenschaft von der <xref:System.Windows.Forms.Control> Klasse angibt, ob ein Steuerelement die Maus erfasst hat. Um zu bestimmen, wenn ein Steuerelement keine Mauseingaben mehr erfasst, verarbeitet die <xref:System.Windows.Forms.Control.MouseCaptureChanged> Ereignis.  
  
 Nur Vordergrundfenster kann die Maus erfassen. Wenn ein Hintergrundfenster versucht, das die Maus erfasst, empfängt das Fenster Nachrichten nur für Mausereignisse, die auftreten, wenn der Mauszeiger innerhalb der sichtbare Teil des Fensters befindet. Darüber hinaus auch, wenn das Fenster im Vordergrund die Maus erfasst hat, kann der Benutzer noch ein weiteres Fenster klicken er in den Vordergrund gestellt. Wenn die Maus erfasst sind, funktionieren Tastenkombinationen nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Mauseingabe in einer Windows Forms-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
