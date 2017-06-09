---
title: "&#196;nderungsbenachrichtigung in der Windows Forms-Datenbindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, Hinzufügen von Änderungsbenachrichtigungen für die Datenbindung"
  - "Windows Forms, Datenbindung"
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# &#196;nderungsbenachrichtigung in der Windows Forms-Datenbindung
Die *Änderungsbenachrichtigung* ist einer der wichtigsten Bestandteile der Windows Forms\-Datenbindung.  Um sicherzustellen, dass die Datenquelle und die gebundenen Steuerelemente immer über aktuelle Daten verfügen, müssen Sie die Änderungsbenachrichtigung für die Datenbindung hinzufügen.  Der Hauptzweck liegt darin, dass gebundene Steuerelemente über Änderungen an der zugehörigen Datenquelle benachrichtigt werden und die Datenquelle über Änderungen benachrichtigt wird, die an den gebundenen Eigenschaften eines Steuerelements vorgenommen wurden.  
  
 Je nach der Art der Datenbindung gibt es unterschiedliche Arten der Änderungsbenachrichtigung:  
  
-   Einfache Bindung, bei der eine einzelne Steuerelementeigenschaft an eine einzelne Instanz eines Objekts gebunden wird.  
  
-   Listenbasierte Bindung, bei der eine einzelne Steuerelementeigenschaft an die Eigenschaft eines Elements in einer Liste oder eine Steuerelementeigenschaft an eine Liste von Objekten gebunden wird.  
  
 Darüber hinaus müssen Sie beim Erstellen von Windows Forms\-Steuerelementen, die für Datenbindung vorgesehen sind, das *PropertyName*Changed\-Muster auf die Steuerelemente anwenden, sodass Änderungen an den gebundenen Eigenschaften eines Steuerelements an die Datenquelle weitergegeben werden.  
  
## Änderungsbenachrichtigung für einfache Bindung  
 Bei einfacher Bindung müssen Geschäftsobjekte Änderungsbenachrichtigung bereitstellen, wenn sich der Wert einer gebundenen Eigenschaft ändert.  Hierfür müssen Sie für jede Eigenschaft des Geschäftsobjekts ein *PropertyName*Changed\-Ereignis verfügbar machen und die Geschäftsobjekte mit <xref:System.Windows.Forms.BindingSource> oder der bevorzugten Methode an Steuerelemente binden, in der die Geschäftsobjekte die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementieren und ein <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>\-Ereignis auslösen, sobald sich der Wert einer Eigenschaft ändert.  Weitere Informationen finden Sie unter [Gewusst wie: Implementieren der INotifyPropertyChanged\-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md).  Wenn Sie Objekte verwenden, die die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementieren, müssen Sie zum Binden des Objekts an ein Steuerelement nicht die <xref:System.Windows.Forms.BindingSource> verwenden, sondern sollten stattdessen besser die <xref:System.Windows.Forms.BindingSource> verwenden.  
  
## Änderungsbenachrichtigung für listenbasierte Bindung  
 In Windows Forms beruht die Bereitstellung von Informationen über Eigenschaftenänderungen \(Änderung eines Listenelement\-Eigenschaftswerts\) und Listenänderungen \(Löschen oder Hinzufügen eines Elements aus bzw. zur Liste\) an gebundene Steuerelemente auf einer gebundenen Liste.  Listen, die für Datenbindung verwendet werden, müssen daher die <xref:System.ComponentModel.IBindingList> implementieren, die beide Arten der Änderungsbenachrichtigung bereitstellt.  Die <xref:System.ComponentModel.BindingList%601> ist eine generische Implementierung der <xref:System.ComponentModel.IBindingList> und ist für die Verwendung mit Windows Forms\-Datenbindung vorgesehen.  Sie können eine <xref:System.ComponentModel.BindingList%601> mit einem Geschäftsobjekttyp erstellen, der <xref:System.ComponentModel.INotifyPropertyChanged> implementiert, und die Liste konvertiert die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>\-Ereignisse automatisch in <xref:System.ComponentModel.IBindingList.ListChanged>\-Ereignisse.  Wenn die gebundene Liste keine <xref:System.ComponentModel.IBindingList> ist, müssen Sie die Liste der Objekte mithilfe der <xref:System.Windows.Forms.BindingSource>\-Komponente an Windows Forms\-Steuerelemente binden.  Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt, ähnlich wie die <xref:System.ComponentModel.BindingList%601>, eine Konvertierung von Eigenschaften zu Listen bereit.  Weitere Informationen finden Sie unter [Gewusst wie: Auslösen von Änderungsbenachrichtigungen mithilfe von "BindingSource" und der "INotifyPropertyChanged"\-Schnittstelle](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).  
  
## Änderungsbenachrichtigung für benutzerdefinierte Steuerelemente  
 Für das Steuerelement müssen Sie für jede Eigenschaft, die an Daten gebunden werden soll, ein *PropertyName*Changed\-Ereignis verfügbar machen.  Die Änderungen an der Steuerelementeigenschaft werden dann an die gebundene Datenquelle weitergegeben.  Weitere Informationen finden Sie unter [Gewusst wie: Anwenden des PropertyNameChanged\-Musters](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
  
## Siehe auch  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.ComponentModel.INotifyPropertyChanged>   
 <xref:System.ComponentModel.BindingList%601>   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Von Windows Forms unterstützte Datenquellen](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)