---
title: "xml:lang Handling in XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XAML [XAML Services], xml:lang attribute"
  - "xml:lang attribute [XAML Services]"
  - "RFC 3066 standard [XAML Services]"
  - "standards [XAML Services], RFC 3066"
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
caps.latest.revision: 16
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 15
---
# xml:lang Handling in XAML
Das `xml:lang`\-Attribut ist ein [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]\-definiertes Attribut, das die Informationen zur Sprache und Kultur für ein Element in XML deklariert. Das Attribut weist in XAML dieselbe Bedeutung auf, es müssen jedoch einige zusätzliche Aspekte berücksichtigt werden.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object xml:lang="rfc3066lang" />  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|*rfc3066lang*|Eine vom [RFC 3066](http://go.microsoft.com/fwlink/?LinkId=132454)\-Standard abgeleitete Zeichenfolge, die entweder eine Sprache oder eine Kombination von Sprache\-Region kennzeichnet. In letzterem Fall werden Sprache und Region durch einen einzelnen Bindestrich getrennt. Weitere Informationen zu den Werten und zum Format finden Sie unter <xref:System.Windows.Markup.XmlLanguage>.|  
  
## Hinweise  
 Die Definition für das `xml:lang`\-Attribut in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ist von `xml:lang` abgeleitet, das vom [!INCLUDE[TLA#tla_w3c](../../../includes/tlasharptla-w3c-md.md)] für [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)] als „spezielles Attribut“ definiert ist. Informationen zu Sprache und Kultur werden von Elementen je nach deren Implementierung möglicherweise unterschiedlich verarbeitet. Es gibt jedoch keine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Standardverarbeitung für das `xml:lang`\-Attribut.  
  
 Der Standardwert des `xml:lang`\-Attributs ist eine leere Zeichenfolge auf Attributebene.  
  
 Die `xml:lang`\-Attributeffekte und der Wert des Attributs werden im Allgemeinen in untergeordneten Elementen bewahrt, wenn sie von Systemen interpretiert werden, die auf `xml:lang`\-Werte einwirken.  
  
 Bei der Interpretation von XAML\-Writern von XAML\-Diensten des .NET Frameworks kann ein `xml:lang`\-Wert <xref:System.Windows.Markup.XmlLanguage>\- oder <xref:System.Globalization.CultureInfo>\-Objekte in der zugrunde liegenden Objektdarstellung erstellen. Dieses Verhalten hängt jedoch davon ab, ob der für `xml:lang` angegebene Wert eine gültige Ausführung für diese Klassen ist.  
  
 Frameworks können zwischen den vom Framework definierten Eigenschaften und der Bedeutung der `xml:lang` in XML durch Anwenden von <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf die Eigenschaft entsprechende Zuordnungen erstellen.  
  
## Hinweise zur WPF\-Verwendung  
 Für Elemente, die abgeleitete Klassen von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> darstellen, können Sie die entsprechende <xref:System.Windows.FrameworkElement.Language%2A>\-Abhängigkeitseigenschaft anstelle des `xml:lang`\-Attributs verwenden. Die <xref:System.Windows.FrameworkElement.Language%2A>\-Eigenschaft verwendet standardmäßig „en\-US“, wenn sie nicht anderweitig festgelegt wird. Dies erfolgt entweder über die Eigenschaft oder durch die Verarbeitung des `xml:lang`\-Attributs.  
  
## Siehe auch  
 [Globalisierung für WPF](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md)