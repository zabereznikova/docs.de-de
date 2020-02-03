---
title: Attribute in Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: b32e4f87e953438a3bb11569445a9270e11c7922
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732124"
---
# <a name="attributes-in-windows-forms-controls"></a>Attribute in Windows Forms-Steuerelementen
Das .NET Framework bietet eine Vielzahl von Attributen, die Sie auf die Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können. Einige dieser Attribute haben Auswirkungen auf das Laufzeitverhalten einer Klasse, während andere Auswirkungen auf das Entwurfszeitverhalten haben.  
  
## <a name="attributes-for-control-and-component-properties"></a>Attribute für Steuerelement- und Komponenteneigenschaften  
 Die folgende Tabelle enthält die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können. Ein Beispiel, in dem viele dieser Attribute verwendet werden, finden Sie unter [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](how-to-apply-attributes-in-windows-forms-controls.md).  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Gibt den Wert an, der an eine Eigenschaft übergeben werden soll, damit die Eigenschaft den zugehörigen Wert von einer anderen Quelle abrufen kann. Dies wird als *Umgebung* bezeichnet.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Gibt an, ob eine Eigenschaft oder ein Ereignis im Fenster **Eigenschaften** angezeigt werden soll.|  
|<xref:System.ComponentModel.CategoryAttribute>|Gibt den Namen der Kategorie an, in der die Eigenschaft oder das Ereignis gruppiert werden soll, wenn Sie in einem <xref:System.Windows.Forms.PropertyGrid> Steuerelement <xref:System.Windows.Forms.PropertySort.Categorized> Modus angezeigt wird.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Gibt den Standardwert für eine Eigenschaft an.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Gibt die Beschreibung einer Eigenschaft oder eines Ereignisses an.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Gibt den Anzeigenamen für eine Eigenschaft, ein Ereignis oder eine `public void`-Methode an, die keine Argumente akzeptiert.|  
|<xref:System.ComponentModel.EditorAttribute>|Gibt den Editor an, der zum Ändern einer Eigenschaft verwendet wird.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Gibt an, dass eine Eigenschaft oder Methode in einem Editor angezeigt werden kann.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Gibt das Kontextschlüsselwort für eine Klasse oder ein Element an.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Gibt an, ob eine Eigenschaft lokalisiert werden soll.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Gibt an, dass die Textdarstellung eines Objekts von Zeichen wie Sternchen verdeckt wird.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Gibt an, ob die Eigenschaft, an die dieses Attribut gebunden ist, schreibgeschützt ist oder ob zur Entwurfszeit Lese-/Schreibzugriff gewährt wird.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Gibt an, dass das Eigenschaftenraster aktualisiert werden sollte, wenn sich der zugehörige Eigenschaftswert ändert.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Gibt an, welcher Typ als Konverter für das Objekt verwendet werden sollte, an das dieses Attribut gebunden ist.|  
  
## <a name="attributes-for-data-binding-properties"></a>Attribute für Datenbindungseigenschaften  
 In der folgenden Tabelle werden die Attribute angezeigt, die Sie für die Angabe anwenden können, wie Ihre benutzerdefinierten Steuerelemente und Komponenten mit der Datenbindung interagieren.  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|Gibt an, ob eine Eigenschaft in der Regel für die Bindung verwendet wird.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Gibt die Eigenschaften der Datenquelle und des Datenmembers für eine Komponente an.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Gibt die Standardbindungseigenschaft für eine Komponente an.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Gibt die Eigenschaften der Datenquelle und des Datenmembers für eine Komponente an.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Ermöglicht die Umleitung von Attributen.|  
  
## <a name="attributes-for-classes"></a>Attribute für Klassen  
 In der folgenden Tabelle werden die Attribute angezeigt, die Sie anwenden können, um das Verhalten Ihrer benutzerdefinierten Steuerelemente und Komponenten zur Entwurfszeit anzugeben.  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Gibt das Standardereignis für eine Komponente an.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Gibt die Standardeigenschaft für eine Komponente an.|  
|<xref:System.ComponentModel.DesignerAttribute>|Gibt die Klasse an, die zum Implementieren von Entwurfszeitdiensten für eine Komponente verwendet wird.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Gibt an, dass der Designer für eine Klasse zu einer bestimmten Kategorie gehört.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Stellt ein Attribut eines Werkzeugkastenelements dar.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Gibt die Filterzeichenfolge und den Filtertyp an, die für ein Werkzeugkastenelement verwendet werden sollen.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Attribute>
- [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](how-to-apply-attributes-in-windows-forms-controls.md)
- [Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
