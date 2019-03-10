---
title: Durch geänderte Eigenschaften ausgelöste Ereignisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 0ff5b3874d9de169f4a9f1040d601173af352c06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703230"
---
# <a name="property-changed-events"></a>Durch geänderte Eigenschaften ausgelöste Ereignisse
Wenn Sie möchten, dass das Steuerelement zum Senden von Benachrichtigungen, wenn eine Eigenschaft mit dem Namen *PropertyName* geändert wird, definieren Sie ein Ereignis, das mit dem Namen *PropertyName* `Changed` und eine Methode namens `On` *PropertyName* `Changed` , die das Ereignis auslöst. Die Namenskonvention in Windows Forms besteht darin das Wort *Changed* auf den Namen der Eigenschaft. Ist der zugeordnete Ereignis-Delegattyp für geänderte Eigenschaften ausgelöste Ereignisse <xref:System.EventHandler>, und der Ereignisdatentyp ist <xref:System.EventArgs>. Die Basisklasse <xref:System.Windows.Forms.Control> definiert viele durch geänderte Eigenschaften ausgelöste Ereignisse, z. B. <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, und andere. Hintergrundinformationen zu Ereignissen finden Sie unter [Ereignisse](../../../standard/events/index.md) und [Ereignisse in Windows Forms-Steuerelementen](events-in-windows-forms-controls.md).  
  
 Geänderte Eigenschaften ausgelöste Ereignisse sind nützlich, da damit die Consumer eines Steuerelements zum Anfügen von Ereignishandlern, die auf die Änderung reagieren können. Wenn das Steuerelement muss auf eine Eigenschaft geänderten Ereignisses zu reagieren, das ausgelöst wird, überschreiben Sie die entsprechenden `On` *PropertyName* `Changed` Methode anstelle ein Delegaten an das Ereignis anzufügen. Ein Steuerelement antwortet in der Regel auf eine Eigenschaft geänderten Ereignisses, indem Sie andere Eigenschaften aktualisieren oder Neuzeichnen einiger oder aller der Zeichenoberfläche.  
  
 Das folgende Beispiel zeigt die `FlashTrackBar` benutzerdefiniertes Steuerelement reagiert, auf einige der durch geänderte Eigenschaften ausgelöste Ereignisse, die es erbt <xref:System.Windows.Forms.Control>. Das vollständige Beispiel finden Sie unter [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- [Ereignisse](../../../standard/events/index.md)
- [Ereignisse in Windows Forms-Steuerelementen](events-in-windows-forms-controls.md)
- [Eigenschaften in Windows Forms-Steuerelementen](properties-in-windows-forms-controls.md)
