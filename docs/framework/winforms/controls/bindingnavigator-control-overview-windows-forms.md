---
title: Übersicht über das BindingNavigator-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
ms.openlocfilehash: ae1e8273c39122e094817e28379e52c19c573a3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bindingnavigator-control-overview-windows-forms"></a>Übersicht über das BindingNavigator-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.BindingNavigator>-Steuerelement können Sie ein standardisiertes Instrument erstellen, mit dem Benutzer Daten in einem Windows Form suchen und ändern können. <xref:System.Windows.Forms.BindingNavigator> wird häufig zusammen mit der <xref:System.Windows.Forms.BindingSource>-Komponente verwendet, damit Benutzer Datensätze in einem Formular durchlaufen und bearbeiten können.  
  
## <a name="how-the-bindingnavigator-works"></a>So funktioniert der BindingNavigator  
 Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement besteht aus einem <xref:System.Windows.Forms.ToolStrip>-Objekt mit einer Reihe von <xref:System.Windows.Forms.ToolStripItem>-Objekten für die meisten gängigen datenbezogenen Aktionen: Hinzufügen von Daten, Löschen von Daten und Navigieren durch Daten. Standardmäßig enthält das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement enthält diese Standardschaltflächen. Die folgende Abbildung zeigt das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement in einem Formular.  
  
 ![BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "CpDataContainerCtrl")  
  
 In der folgende Tabelle sind die Steuerelemente aufgelistet und deren Funktionen beschrieben.  
  
|Steuerelement|Funktion|  
|-------------|--------------|  
|<xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A>-Schaltfläche|Fügt eine neue Zeile in der zugrunde liegenden Datenquelle ein.|  
|<xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A>-Schaltfläche|Löscht die aktuelle Zeile aus der zugrunde liegenden Datenquelle.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>-Schaltfläche|Wechselt zum ersten Element in der zugrunde liegenden Datenquelle.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A>-Schaltfläche|Wechselt zum letzten Element in der zugrunde liegenden Datenquelle.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A>-Schaltfläche|Wechselt zum nächsten Element in der zugrunde liegenden Datenquelle.|  
|<xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A>-Schaltfläche|Wechselt zum vorherigen Element in der zugrunde liegenden Datenquelle.|  
|<xref:System.Windows.Forms.BindingNavigator.PositionItem%2A>-Textfeld|Gibt die aktuelle Position in der zugrunde liegenden Datenquelle zurück.|  
|<xref:System.Windows.Forms.BindingNavigator.CountItem%2A>-Textfeld|Gibt die Gesamtzahl von Elementen in der zugrunde liegenden Datenquelle zurück.|  
  
 Für jedes Steuerelement in dieser Auflistung gibt es einen entsprechenden Member der <xref:System.Windows.Forms.BindingSource>-Komponente, die dieselbe Funktionalität programmgesteuert bereitstellt. Beispielsweise entspricht die <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>-Schaltfläche der <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>-Methode der <xref:System.Windows.Forms.BindingSource>-Komponente, die <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A>-Schaltfläche der <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A>-Methode usw.  
  
 Wenn die Standardschaltflächen für Ihre Anwendung nicht geeignet sind, oder wenn Sie weitere Schaltflächen benötigen, um andere Funktionalitäten zu unterstützen, können Sie Ihre eigenen <xref:System.Windows.Forms.ToolStrip>-Schaltflächen bereitstellen. Siehe auch [Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 [BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
