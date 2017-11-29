---
title: Mauserfassung in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8004b05ea25341a142bfcfd9ae812ee3bebd6d5b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a>Mauserfassung in Windows Forms
*Mauseingaben* bezieht sich auf, wenn ein Befehl, der alle Mauseingaben hat. Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben, und zwar unabhängig davon, ob der Zeiger innerhalb seiner Grenzen befindet.  
  
## <a name="setting-mouse-capture"></a>Festlegen von Mauseingaben  
 In Windows Forms ist die Maus vom Steuerelement erfasst, wenn der Benutzer eine Maustaste für ein Steuerelement drückt, und die Maus vom Steuerelement freigegeben, wenn der Benutzer die Maustaste loslässt.  
  
 Die <xref:System.Windows.Forms.Control.Capture%2A> Eigenschaft von der <xref:System.Windows.Forms.Control> Klasse angibt, ob ein Steuerelement die Maus erfasst hat. Um zu bestimmen, wenn ein Steuerelement keine Mauseingaben mehr erfasst, verarbeitet die <xref:System.Windows.Forms.Control.MouseCaptureChanged> Ereignis.  
  
 Nur Vordergrundfenster kann die Maus erfassen. Wenn ein Hintergrundfenster versucht, das die Maus erfasst, empfängt das Fenster Nachrichten nur für Mausereignisse, die auftreten, wenn der Mauszeiger innerhalb der sichtbare Teil des Fensters befindet. Darüber hinaus auch, wenn das Fenster im Vordergrund die Maus erfasst hat, kann der Benutzer noch ein weiteres Fenster klicken er in den Vordergrund gestellt. Wenn die Maus erfasst sind, funktionieren Tastenkombinationen nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Mauseingabe in einer Windows Forms-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
