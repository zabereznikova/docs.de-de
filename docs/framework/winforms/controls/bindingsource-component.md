---
title: BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683417"
---
# <a name="bindingsource-component"></a>BindingSource-Komponente
Kapselt eine Datenquelle zum Binden an Steuerelemente.  
  
 Die <xref:System.Windows.Forms.BindingSource>-Komponente dient zwei Zwecken. Als erstes stellt sie eine Dereferenzierungsschicht bereit, wenn die Steuerelemente in einem Formular an Daten gebunden werden. Bei diesem Vorgang wird die <xref:System.Windows.Forms.BindingSource>-Komponente an die Datenquelle gebunden, und anschließend werden die Steuerelemente im Formular an die <xref:System.Windows.Forms.BindingSource>-Komponente gebunden. Alle weiteren Interaktionen mit den Daten, einschließlich Navigieren, Sortieren, Filtern und Aktualisieren, werden durch Aufrufe an die <xref:System.Windows.Forms.BindingSource>-Komponente ausgeführt.  
  
 Zweitens kann die <xref:System.Windows.Forms.BindingSource>-Komponente als Datenquelle mit starker Typisierung fungieren. Wenn Sie der <xref:System.Windows.Forms.BindingSource>-Komponente einen Typ mit der <xref:System.Windows.Forms.BindingSource.Add%2A>-Methode hinzuzufügen, wird eine Liste dieses Typs erstellt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die BindingSource-Komponente](bindingsource-component-overview.md)  
 Stellt die allgemeinen Konzepte der <xref:System.Windows.Forms.BindingSource>-Komponente vor, mit deren Hilfe eine Datenquelle an ein Steuerelement gebunden werden kann.  
  
 [Vorgehensweise: Binden von Windows Forms-Steuerelementen an DBNull-Datenbankwerte](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 Veranschaulicht, wie ein <xref:System.DBNull>-Wert von der Datenquelle mit der <xref:System.Windows.Forms.BindingSource>-Komponente behandelt wird.  
  
 [Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der Windows Forms-BindingSource-Komponente](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Sortierungen und Filter auf angezeigte Daten angewendet werden.  
  
 [Vorgehensweise: Binden Sie an einen Webdienst mithilfe der BindingSource in Windows Forms](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Bindungen an einen Webdienst vorgenommen werden können.  
  
 [Vorgehensweise: Behandeln von Fehlern und Ausnahmen, die auftreten, mit der Datenbindung](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Fehler bei Datenbindungsvorgängen erfolgreich behandelt werden.  
  
 [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)  
 Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Binden an einen Typ.  
  
 [Vorgehensweise: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Binden an ein Factoryobjekt oder eine Methode.  
  
 [Vorgehensweise: Anpassen der Hinzufügung mithilfe der BindingSource von Windows Forms](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente, um neue Elemente zu erstellen und sie einer Datenquelle hinzuzufügen.  
  
 [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource ResetItem-Methode](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Auslösen von Änderungsbenachrichtigungsereignissen für Datenquellen, die keine Änderungsbenachrichtigung unterstützen.  
  
 [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle](raise-change-notifications--bindingsource.md)  
 Veranschaulicht die Verwendung eines Typs, der von <xref:System.ComponentModel.INotifyPropertyChanged> mit einem <xref:System.Windows.Forms.BindingSource>-Steuerelement erbt.  
  
 [Vorgehensweise: Datenquellenaktualisierungen Sie in einem Windows Forms-Steuerelement mit der BindingSource-Komponente](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente auf Änderungen in der Datenquelle reagiert werden kann.  
  
 [Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 Veranschaulicht die Verwendung der <xref:System.Windows.Forms.BindingSource> zum Binden mehrerer Formulare an die gleiche Datenquelle.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.BindingSource>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Windows Forms-Datenbindung](../windows-forms-data-binding.md)  
 Enthält Links zu Themen, in denen die Architektur für die Datenbindung in Windows Forms beschrieben wird.  
  
 Siehe auch [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).
