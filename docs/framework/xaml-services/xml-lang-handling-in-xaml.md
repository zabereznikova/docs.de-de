---
title: xml:lang-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 025e4b2865fe3938e5f1454f87e90bae7a85bcfd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399662"
---
# <a name="xmllang-handling-in-xaml"></a>xml:lang-Behandlung in XAML
Das `xml:lang` -Attribut ist ein [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]-definiertes Attribut, das die Informationen zur Sprache und Kultur für ein Element in XML deklariert. Das Attribut weist in XAML dieselbe Bedeutung auf, es müssen jedoch einige zusätzliche Aspekte berücksichtigt werden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object xml:lang="rfc3066lang" />  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*rfc3066lang*|Eine Zeichenfolge, die von abgeleitet ist die [RFC 3066](https://go.microsoft.com/fwlink/?LinkId=132454) standard und identifiziert entweder eine Sprache oder eine Sprache-Region. In letzterem Fall werden Sprache und Region durch einen einzelnen Bindestrich getrennt. Weitere Informationen zu den Werten und zum Format finden Sie unter <xref:System.Windows.Markup.XmlLanguage> .|  
  
## <a name="remarks"></a>Hinweise  
 Die Definition für das `xml:lang` -Attribut in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ist von `xml:lang` abgeleitet, das vom [!INCLUDE[TLA#tla_w3c](../../../includes/tlasharptla-w3c-md.md)] für [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]als „spezielles Attribut“ definiert ist. Informationen zu Sprache und Kultur werden von Elementen je nach deren Implementierung möglicherweise unterschiedlich verarbeitet. Es gibt jedoch keine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Standardverarbeitung für das `xml:lang` -Attribut.  
  
 Der Standardwert des `xml:lang` -Attributs ist eine leere Zeichenfolge auf Attributebene.  
  
 Die `xml:lang` -Attributeffekte und der Wert des Attributs werden im Allgemeinen in untergeordneten Elementen bewahrt, wenn sie von Systemen interpretiert werden, die auf `xml:lang` -Werte einwirken.  
  
 Bei der Interpretation von XAML-Writern von XAML-Diensten des .NET Frameworks kann ein `xml:lang` -Wert <xref:System.Windows.Markup.XmlLanguage> - oder <xref:System.Globalization.CultureInfo> -Objekte in der zugrunde liegenden Objektdarstellung erstellen. Dieses Verhalten hängt jedoch davon ab, ob der für `xml:lang` angegebene Wert eine gültige Ausführung für diese Klassen ist.  
  
 Frameworks können zwischen den vom Framework definierten Eigenschaften und der Bedeutung der `xml:lang` in XML durch Anwenden von <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf die Eigenschaft entsprechende Zuordnungen erstellen.  
  
## <a name="wpf-usage-nodes"></a>Hinweise zur WPF-Verwendung  
 Für Elemente, die abgeleitete Klassen von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>darstellen, können Sie die entsprechende <xref:System.Windows.FrameworkElement.Language%2A> -Abhängigkeitseigenschaft anstelle des `xml:lang` -Attributs verwenden. Die <xref:System.Windows.FrameworkElement.Language%2A> -Eigenschaft verwendet standardmäßig „en-US“, wenn sie nicht anderweitig festgelegt wird. Dies erfolgt entweder über die Eigenschaft oder durch die Verarbeitung des `xml:lang` -Attributs.  
  
## <a name="see-also"></a>Siehe auch  
 [Globalisierung für WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
