---
title: Änderungsbenachrichtigung in der Windows Forms-Datenbindung
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 79ad52b6db8cb7be7f4e3162b8f726e8cbe22dcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527731"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Änderungsbenachrichtigung in der Windows Forms-Datenbindung
Einer der wichtigsten Konzepte des Windows Forms-Datenbindung ist *änderungsbenachrichtigung*. Um sicherzustellen, dass die Datenquelle und gebundenen Steuerelementen immer die aktuellsten Daten haben, müssen Sie die änderungsbenachrichtigung für die Datenbindung hinzufügen. Insbesondere sollen, stellen Sie sicher, dass gebundene Steuerelemente Änderungen benachrichtigt werden, die mit ihrer Datenquelle vorgenommen wurden, und die Datenquelle an die gebundenen Eigenschaften eines Steuerelements vorgenommenen Änderungen benachrichtigt.  
  
 Es gibt verschiedene Arten von änderungsbenachrichtigungen, abhängig von der Art der Datenbindung:  
  
-   Einfache Bindung, in dem eine einzelne Steuerelementeigenschaft an eine einzelne Instanz eines Objekts gebunden ist.  
  
-   Listenbasierte Bindung, z. eine einzelne Steuerelementeigenschaft an die Eigenschaft eines Elements in einer Liste oder einer Steuerelementeigenschaft gebunden b., die an eine Liste der Objekte gebunden werden.  
  
 Darüber hinaus, wenn Sie Windows Forms-Steuerelemente, die Sie für die Datenbindung verwenden möchten erstellen, Sie müssen Anwenden der *PropertyName*Muster für die Steuerelemente so geändert, dass Änderungen an der gebundenen Eigenschaft eines Steuerelements an weitergegeben werden die die Datenquelle.  
  
## <a name="change-notification-for-simple-binding"></a>Änderungsbenachrichtigung für die einfache Bindung  
 Einfache Bindung müssen Geschäftsobjekte änderungsbenachrichtigung verliehen wird bei Änderung des Werts einer Eigenschaft gebunden. Hierzu können Sie durch das Verfügbarmachen von einer *PropertyName*Changed-Ereignis für jede Eigenschaft das Geschäftsobjekt einer und binden das Geschäftsobjekt auf Steuerelemente mit den <xref:System.Windows.Forms.BindingSource> oder die bevorzugte Methode, in dem das Geschäftsobjekt implementiert, die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle und löst eine <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis aus, wenn der Wert einer Eigenschaft ändert. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md). Bei Verwendung von Objekten, implementieren die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle, Sie müssen keine verwenden die <xref:System.Windows.Forms.BindingSource> zum Binden des Objekts an ein Steuerelement, während mit der <xref:System.Windows.Forms.BindingSource> wird empfohlen.  
  
## <a name="change-notification-for-list-based-binding"></a>Änderungsbenachrichtigung für listenbasierte Bindung  
 Windows Forms, hängt von einer gebundenen Liste-Eigenschaftenänderung bereitstellen (ein Liste-Eigenschaftswert ändert) und Liste geändert (ein Element gelöscht oder zur Liste hinzugefügt) Informationen an Steuerelemente gebunden. Aus diesem Grund müssen Listen, die für die Datenbindung verwendet implementieren die <xref:System.ComponentModel.IBindingList>, stellt auf beide Arten von änderungsbenachrichtigungen. Die <xref:System.ComponentModel.BindingList%601> ist eine generische Implementierung der <xref:System.ComponentModel.IBindingList> und dient zur Verwendung mit Windows Forms-Datenbindung. Können Sie erstellen eine <xref:System.ComponentModel.BindingList%601> , enthält einen Geschäftstyp für das Objekt, das implementiert <xref:System.ComponentModel.INotifyPropertyChanged> und die Liste wird automatisch konvertiert die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignisse <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse. Ist die Liste der gebundene kein <xref:System.ComponentModel.IBindingList>, müssen Sie die Liste der Objekte für Windows Forms-Steuerelemente binden, indem die <xref:System.Windows.Forms.BindingSource> Komponente. Die <xref:System.Windows.Forms.BindingSource> Komponente gebe Eigenschaftenliste-Konvertierung ähnlich dem Konzept der <xref:System.ComponentModel.BindingList%601>. Weitere Informationen finden Sie unter [wie: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Änderungsbenachrichtigung für benutzerdefinierte Steuerelemente  
 Schließlich von der Seite des Steuerelements verfügbar machen eine *PropertyName*Changed-Ereignis für jede Eigenschaft, die an Daten gebunden werden soll. Die Änderungen an der Steuerelementeigenschaft werden dann an die gebundene Datenquelle weitergegeben werden. Weitere Informationen finden Sie unter [wie: Anwenden des PropertyNameChanged-Musters](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 <xref:System.ComponentModel.BindingList%601>  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Von Windows Forms unterstützte Datenquellen](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
