---
title: "Eigenschaften von Windows&#160;Forms-Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Eigenschaften"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Eigenschaftenübersicht (mit Code)"
  - "Eigenschaften [Windows Forms]"
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Eigenschaften von Windows&#160;Forms-Steuerelementen
Ein Windows Forms\-Steuerelement erbt zahlreiche Eigenschaften von der Basisklasse <xref:System.Windows.Forms.Control?displayProperty=fullName>.  Zu diesen Eigenschaften zählen <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A> und viele andere.  Ausführliche Informationen zu geerbten Ereignissen finden Sie unter <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
 Sie können sowohl geerbte Eigenschaften in dem Steuerelement überschreiben als auch neue Eigenschaften definieren.  
  
## In diesem Abschnitt  
 [Definieren einer Eigenschaft](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 Beschreibt, wie eine Eigenschaft für ein benutzerdefiniertes Steuerelement oder eine benutzerdefinierte Komponente implementiert wird und wie die Eigenschaft in die Entwurfsumgebung integriert wird.  
  
 [Definieren von Standardwerten mit der ShouldSerialize\-Methode und der Reset\-Methode](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Beschreibt, wie Standardeigenschaftswerte für ein benutzerdefiniertes Steuerelement oder eine benutzerdefinierte Komponente definiert werden.  
  
 [Durch geänderte Eigenschaften ausgelöste Ereignisse](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 Beschreibt, wie Benachrichtigungen zu Eigenschaftenänderungen aktiviert werden, wenn sich ein Eigenschaftswert ändert.  
  
 [Gewusst wie: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 Beschreibt, wie Eigenschaften konstituierender Steuerelemente in einem benutzerdefinierten zusammengesetzten Steuerelement verfügbar gemacht werden.  
  
 [Implementierung von Methoden in benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 Beschreibt, wie Methoden in benutzerdefinierten Steuerelementen und Komponenten implementiert werden.  
  
## Referenz  
 <xref:System.Windows.Forms.UserControl>  
 Enthält die Dokumentation der Basisklasse zum Implementieren von zusammengesetzten Steuerelementen.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Enthält die Dokumentation des Attributs, das <xref:System.ComponentModel.TypeConverter> für einen benutzerdefinierten Eigenschaftentyp angibt.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Enthält die Dokumentation des Attributs, das <xref:System.Drawing.Design.UITypeEditor> für eine benutzerdefinierte Eigenschaft angibt.  
  
## Verwandte Abschnitte  
 [Attribute in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 Beschreibt die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.  
  
 [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md)  
 Enthält eine Liste von Metadatenattributen, die auf Komponenten und Steuerelemente angewendet werden, sodass diese in visuellen Designern zur Entwurfszeit korrekt angezeigt werden.  
  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)  
 Beschreibt die Implementierung von Klassen, z. B. Editoren und Designern, die Entwurfszeitunterstützung bereitstellen.