---
title: '{} Escapesequenz - Markuperweiterung'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: a90f6928d68eddd29762e6206769dd7f07704e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564520"
---
# <a name="-escape-sequence--markup-extension"></a>{} Escapesequenz / Markuperweiterung
Stellt die Verwendung von XAML-Escapesequenz für Attributwerte bereit. Die-Escapesequenz kann nachfolgende Werte im Attribut als Literal interpretiert werden soll.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Verwendung von XAML-Eigenschaftenelementen  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*LiteralValue*|Das Zeichenfolgenliteral, das die-Escapesequenz folgt. Diese Zeichenfolge enthält in der Regel eine öffnende oder schließende Klammer ({oder}).|  
  
## <a name="remarks"></a>Hinweise  
 Die Escapesequenz ({}) wird verwendet, damit eine öffnende geschweifte Klammer ({}) als Literalzeichen in XAML verwendet werden kann.  
  
 XAML-Readern in der Regel verwenden die öffnende geschweifte Klammer ({}), um den Einstiegspunkt einer Markuperweiterung zu kennzeichnen; allerdings überprüfen sie zunächst das nächste Zeichen aus, um festzustellen, ob es sich um eine schließende geschweifte Klammer (}) ist. Nur wenn die beiden geschweifte Klammern ({}) sind von angrenzenden, werden sie als eine Escapesequenz betrachtet.  
  
 Wenn die-Escapesequenz gefunden wird, sollte der XAML-Reader die restliche Zeichenfolge als Zeichenfolge verarbeiten. Jedoch wenn Escape-Zeichenfolge auf ein Element angewendet wird, einen Typkonverter hat, kann die Zeichenfolge Konvertierung vom Typ unterzogen werden, wenn er von einem XAML-Writer interpretiert wird.  
  
 Die-Escapesequenz ist eine Markuperweiterung und nicht durch eine Klasse unterstützt wird. Es ist jedoch eine Konvention, die XAML-Reader (einschließlich benutzerdefinierter XAML-Reader) berücksichtigen sollten.  
  
 Ein Anführungszeichen (") kann nicht als Escapesequenz auf diese Weise verwendet werden. Wenn Sie ein Anführungszeichen als einen Eigenschaftswert für eine Eigenschaft des Eigenschaftenelements festlegen müssen, verwenden Sie Eigenschaftenelementsyntax und platzieren Sie die Anführungszeichen als Zeichenfolge innerhalb der Property-Element, oder eine XML-Zeichen-Entität. Für einen Content-Eigenschaft kann das Anführungszeichen der gesamte Inhalt sein.  
  
 Die Escapesequenz ({}) ist häufig erforderlich, wenn Sie einen XML-Datentyp angeben, die einen Namespacequalifizierer an einem Ort einschließen muss, in denen möglicherweise eine XAML-Markuperweiterung angezeigt. Dies schließt den Beginn des XAML-Attributwert und in eine Markuperweiterung, sofort nach einem Gleichheitszeichen (=). Das folgende Beispiel zeigt die Escapesequenzen für einen XML-Namespace, der am Anfang des XAML-Attributwert angezeigt wird.  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typkonverter und Markuperweiterungen für XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [XML-Zeichenentitäten und XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
