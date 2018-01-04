---
title: "Durch geänderte Eigenschaften ausgelöste Ereignisse"
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
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad22d77043f00ab0caaa6d8b08b6b0a9eef1fed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="property-changed-events"></a>Durch geänderte Eigenschaften ausgelöste Ereignisse
Wenn Sie möchten, dass das Steuerelement zum Senden von Benachrichtigungen, wenn sich eine Eigenschaft mit dem Namen *PropertyName* ändert, definieren Sie ein Ereignis namens *PropertyName* `Changed` und eine Methode namens `On` *PropertyName* `Changed` , der das Ereignis auslöst. Die Benennungskonvention in Windows Forms wird das Wort anzufügende *Changed* auf den Namen der Eigenschaft. Ist der Delegattyp zugeordneten Ereignissen durch geänderte Eigenschaften ausgelöste Ereignisse <xref:System.EventHandler>, und der Ereignis-Datentyp ist <xref:System.EventArgs>. Die Basisklasse <xref:System.Windows.Forms.Control> definiert viele durch geänderte Eigenschaften ausgelöste Ereignisse, z. B. <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, und andere. Hintergrundinformationen zu Ereignissen finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md) und [Ereignisse in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Durch geänderte Eigenschaften ausgelöste Ereignisse eignen sich, denn sie Consumern eines Steuerelements ermöglichen, fügen Sie Ereignishandler, die auf die Änderung reagieren. Wenn das Steuerelement muss auf ein Eigenschaftenänderungsereignis zu reagieren, das ausgelöst wird, überschreiben Sie die entsprechende `On` *PropertyName* `Changed` Methode anstatt durch Anfügen ein Delegaten das Ereignis. Ein Steuerelement reagiert in der Regel auf ein Eigenschaftenänderungsereignis, andere Eigenschaften aktualisieren oder durch das Neuzeichnen erhalten einiger oder aller der Zeichenoberfläche.  
  
 Das folgende Beispiel zeigt wie die `FlashTrackBar` benutzerdefiniertes Steuerelement reagiert, auf einige der durch geänderte Eigenschaften ausgelöste Ereignisse, die es erbt <xref:System.Windows.Forms.Control>. Das vollständige Beispiel finden Sie unter [Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass zeigt Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../../docs/standard/events/index.md)  
 [Ereignisse in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Eigenschaften in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
