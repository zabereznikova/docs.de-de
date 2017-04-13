---
title: "Attribute in Windows Forms-Steuerelementen | Microsoft Docs"
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
  - "Attribute [Windows Forms]"
  - "Attribute [Windows Forms], Klassen"
  - "Attribute [Windows Forms], Steuerelementeigenschaften"
  - "Attribute [Windows Forms], Datenbindungseigenschaften"
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Attribute in Windows Forms-Steuerelementen
.NET Framework stellt zahlreiche Attribute bereit, die Sie auf die Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.  Einige dieser Attribute beeinflussen das Laufzeitverhalten einer Klasse, während andere das Entwurfszeitverhalten beeinflussen.  
  
## Attribute für Steuerelement\- und Komponenteneigenschaften  
 Die folgende Tabelle enthält die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.  Ein Beispiel, in dem viele dieser Attribute verwendet werden, finden Sie unter [Gewusst wie: Anwenden von Attributen auf Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Gibt den an eine Eigenschaft zu übergebenden Wert an, durch den die Eigenschaft ihren Wert von einer anderen Quelle bezieht.  Dies wird als *Umgebung* bezeichnet.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Gibt an, ob eine Eigenschaft oder ein Ereignis im **Eigenschaftenfenster** angezeigt werden sollte.|  
|<xref:System.ComponentModel.CategoryAttribute>|Gibt den Namen der Kategorie an, in der die Eigenschaft oder das Ereignis gruppiert werden soll, wenn diese in einem <xref:System.Windows.Forms.PropertyGrid>\-Steuerelement mit dem <xref:System.Windows.Forms.PropertySort>\-Modus angezeigt werden.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Gibt den Standardwert für eine Eigenschaft an.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Gibt eine Beschreibung für eine Eigenschaft oder ein Ereignis an.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Gibt den Anzeigenamen für eine Eigenschaft, ein Ereignis oder eine `public``void`\-Methode an, die keine Argumente verwendet.|  
|<xref:System.ComponentModel.EditorAttribute>|Gibt den Editor an, mit dem eine Eigenschaft geändert werden soll.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Gibt an, dass eine Eigenschaft oder eine Methode in einem Editor angezeigt werden kann.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Gibt das Kontextschlüsselwort für eine Klasse oder einen Member an.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Gibt an, ob eine Eigenschaft lokalisiert werden sollte.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Gibt an, dass die Textdarstellung eines Objekts von Zeichen wie Sternchen verdeckt wird.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Gibt an, ob die Eigenschaft, an die dieses Attribut gebunden ist, zur Entwurfszeit schreibgeschützt ist.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Gibt an, dass das Eigenschaftenraster aktualisiert werden sollte, wenn sich der zugehörige Eigenschaftswert ändert.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Gibt an, welcher Typ als Konverter für das Objekt verwendet werden sollte, an das dieses Attribut gebunden ist.|  
  
## Attribute für Datenbindungseigenschaften  
 Die folgende Tabelle enthält die Attribute, die Sie anwenden können, um die Interaktion der benutzerdefinierten Steuerelemente und Komponenten mit der Datenbindung anzugeben.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|<xref:System.ComponentModel.BindableAttribute>|Gibt an, ob eine Eigenschaft normalerweise zum Binden verwendet wird.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Gibt die Datenquellen\- und Datenmembereigenschaften für eine Komponente an.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Gibt die Standardbindungseigenschaft für eine Komponente an.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Gibt die Datenquellen\- und Datenmembereigenschaften für eine Komponente an.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Aktiviert die Attributumleitung.|  
  
## Attribute für Klassen  
 Die folgende Tabelle enthält die Attribute, die Sie anwenden können, um das Verhalten der benutzerdefinierten Steuerelemente und Komponenten zur Entwurfszeit anzugeben.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Gibt das Standardereignis für eine Komponente an.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Gibt die Standardeigenschaft für eine Komponente an.|  
|<xref:System.ComponentModel.DesignerAttribute>|Gibt die Klasse an, die verwendet wird, um Entwurfszeitdienste für eine Komponente zu implementieren.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Gibt an, dass der Designer für eine Klasse zu einer bestimmten Kategorie gehört.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Stellt ein Attribut eines Toolboxelements dar.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Gibt die Filterzeichenfolge und den Filtertyp an, die für ein Toolboxelement verwendet werden sollen.|  
  
## Siehe auch  
 <xref:System.Attribute>   
 [Gewusst wie: Anwenden von Attributen auf Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)