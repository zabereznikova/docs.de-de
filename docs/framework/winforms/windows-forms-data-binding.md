---
title: "Datenbindung in Web&#160;Forms | Microsoft Docs"
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
  - "Gebundene Steuerelemente, Windows Forms"
  - "Daten [Windows Forms]"
  - "Daten [Windows Forms], Architektur"
  - "Steuerelemente für Windows Forms, Datenbindung"
  - "Windows Forms, Datenbindung"
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Datenbindung in Web&#160;Forms
Mit der Datenbindung in Windows Forms erhalten Sie die Möglichkeit, Informationen aus einer Datenquelle in Steuerelementen im Formular anzuzeigen und zu ändern.  Sie können sowohl herkömmliche Datenquellen als auch beinahe alle Strukturen binden, die Daten enthalten.  
  
## In diesem Abschnitt  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 Bietet eine Übersicht über die Datenbindung in Windows Forms.  
  
 [Von Windows Forms unterstützte Datenquellen](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 Beschreibt die Datenquellen, die in Verbindung mit Windows Forms verwendet werden können.  
  
 [Auf Datenbindung bezogene Schnittstellen](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 Beschreibt einige der Schnittstellen, die für die Windows Forms\-Datenbindung verwendet werden.  
  
 [Gewusst wie: Navigieren durch Daten in Windows Forms](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 Zeigt, wie Sie in den Elementen einer Datenquelle navigieren können.  
  
 [Änderungsbenachrichtigung in der Windows Forms\-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 Beschreibt die unterschiedlichen Arten von Änderungsbenachrichtigungen für die Datenbindung in Windows Forms.  
  
 [Gewusst wie: Implementieren der INotifyPropertyChanged\-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 Zeigt, wie die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementiert wird.  Die Schnittstelle übergibt die Eigenschaftenänderungen an einem Geschäftsobjekt an ein gebundenes Steuerelement.  
  
 [Gewusst wie: Anwenden des PropertyNameChanged\-Musters](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 Zeigt, wie das *PropertyNameChanged*\-Muster auf die Eigenschaften eines Windows Forms\-Benutzersteuerelements angewendet wird.  
  
 [Gewusst wie: Implementieren der ITypedList\-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 Zeigt, wie die Ermittlung des Schemas für eine bindbare Liste durch Implementieren der <xref:System.ComponentModel.ITypedList>\-Schnittstelle ermöglicht wird.  
  
 [Gewusst wie: Implementieren der IListSource\-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 Zeigt, wie die <xref:System.ComponentModel.IListSource>\-Schnittstelle implementiert wird, um eine bindbare Klasse zu erstellen, die nicht <xref:System.Collections.IList> implementiert, sondern eine Liste von einem anderen Speicherort bereitstellt.  
  
 [Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 Zeigt, wie das <xref:System.Windows.Forms.BindingSource.BindingComplete>\-Ereignis behandelt wird, um sicherzustellen, dass alle an eine Datenquelle gebundenen Steuerelemente synchronisiert bleiben.  
  
 [Gewusst wie: Sicherstellen, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 Beschreibt, wie Sie sicherstellen können, dass die ausgewählte Zeile in einer untergeordneten Tabelle nicht geändert wird, wenn an einem Feld in der übergeordneten Tabelle eine Änderung vorgenommen wird.  
  
 Lesen Sie hierzu auch [Auf Datenbindung bezogene Schnittstellen](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [Gewusst wie: Navigieren durch Daten in Windows Forms](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).  
  
## Referenz  
 <xref:System.Windows.Forms.Binding?displayProperty=fullName>  
 Beschreibt die Klasse, die für die Bindung zwischen einer bindbaren Komponente und einer Datenquelle steht.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=fullName>  
 Beschreibt die Klasse, die eine Datenquelle für die Bindung an Steuerelemente kapselt.  
  
## Verwandte Abschnitte  
 [BindingSource\-Komponente](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 Enthält eine Liste mit Themen, in denen gezeigt wird, wie die <xref:System.Windows.Forms.BindingSource>\-Komponente verwendet wird.  
  
 [DataGridView\-Steuerelement](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 Enthält eine Liste mit Themen, in denen gezeigt wird, wie ein bindbares DataGrid\-Steuerelement verwendet wird.  
  
 Siehe auch [Zugreifen auf Daten in Visual Studio](http://msdn.microsoft.com/library/wzabh8c4\(v=vs.110\)) oder [Zugreifen auf Daten in Visual Studio](http://msdn.microsoft.com/library/wzabh8c4\(v=vs.110\)).