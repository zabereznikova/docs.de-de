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
ms.openlocfilehash: eaee0a1f92d8b7cb3810651eda21f1cc800ebf57
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58018548"
---
# <a name="-escape-sequence--markup-extension"></a>{} Escapesequenz / Markuperweiterung
Stellt die XAML-Escapesequenz für Attributwerte bereit. Die-Escapesequenz kann nachfolgende Werte im Attribut als Literal interpretiert werden soll.  
  
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
|*literalValue*|Das Zeichenfolgenliteral, das die Escape-Sequenz folgt. Diese Zeichenfolge enthält in der Regel eine öffnende oder schließende Klammer ({oder}).|  
  
## <a name="remarks"></a>Hinweise  
 Die Escape-Sequenz ({}) wird verwendet, damit eine öffnende geschweifte Klammer ({}) als Literalzeichen in XAML verwendet werden kann.  
  
 XAML-Reader in der Regel verwenden die öffnende geschweifte Klammer ({}), um anzugeben, den Einstiegspunkt einer Markuperweiterung; allerdings überprüfen sie zuerst das nächste Zeichen aus, um festzustellen, ob es sich um eine schließende geschweifte Klammer (}) ist. Nur wenn die beiden geschweiften Klammern ({}) angrenzende sind, werden sie als eine Escapesequenz betrachtet.  
  
 Wenn die Escape-Sequenz auftritt, sollte der XAML-Reader der Rest der Zeichenfolge als Zeichenfolge verarbeiten. Allerdings, wenn die Escape-Sequenz auf einen Member, die über einen Typkonverter verfügt angewendet wird, kann die Zeichenfolge Typ umgewandelt werden, wenn er von einem XAML-Writer interpretiert wird.  
  
 Die-Escapesequenz ist es sich nicht um eine Markuperweiterung und nicht durch eine Klasse gesichert. Es ist jedoch eine Konvention, die XAML-Reader (einschließlich benutzerdefinierte XAML-Reader) berücksichtigen sollten.  
  
 Ein Anführungszeichen (") kann nicht als eine Escapesequenz, die auf diese Weise verwendet werden. Wenn Sie ein Anführungszeichen als Eigenschaftswert für eine Eigenschaft des Eigenschaftenelements festlegen müssen, verwenden Sie die Syntax und platzieren Sie die Anführungszeichen als Zeichenfolge innerhalb der Property-Element, oder Verwenden einer XML-Zeichen-Entität. Für eine Inhaltseigenschaft kann das Anführungszeichen der gesamte Inhalt sein.  
  
 Die Escape-Sequenz ({}) ist häufig erforderlich, wenn einen XML-Datentyp angeben, die an einem Ort Namespacequalifizierer einschließen muss, wo eine XAML-Markuperweiterung angezeigt werden kann. Dies schließt den Start einen XAML-Attributwert, und klicken Sie in einer Markuperweiterung, sofort nach einem Gleichheitszeichen (=). Das folgende Beispiel zeigt die Escapesequenzen für einen XML-Namespace, der am Anfang einer XAML-Attributwert angezeigt wird.  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Siehe auch
- [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md)
- [XML-Zeichenentitäten und XAML](xml-character-entities-and-xaml.md)
