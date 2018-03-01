---
title: '{}-Escapesequenz - Markuperweiterung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a>{}-Escapesequenz/Markuperweiterung
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
|*literalValue*|Das Zeichenfolgenliteral, das die-Escapesequenz folgt. Diese Zeichenfolge enthält in der Regel eine öffnende oder schließende Klammer ({oder}).|  
  
## <a name="remarks"></a>Hinweise  
 Die Escapesequenz ({}) wird verwendet, sodass eine öffnende geschweifte Klammer ({}) als Literalzeichen in XAML verwendet werden kann.  
  
 XAML-Readern in der Regel verwenden die öffnende geschweifte Klammer ({}), um den Einstiegspunkt einer Markuperweiterung zu kennzeichnen; allerdings überprüfen sie zunächst das nächste Zeichen aus, um festzustellen, ob es sich um eine schließende geschweifte Klammer (}) ist. Nur, wenn die beiden geschweiften Klammern ({}) nebeneinander angeordnet sind, werden sie eine Escapesequenz angesehen.  
  
 Wenn die-Escapesequenz gefunden wird, sollte der XAML-Reader die restliche Zeichenfolge als Zeichenfolge verarbeiten. Jedoch wenn Escape-Zeichenfolge auf ein Element angewendet wird, einen Typkonverter hat, kann die Zeichenfolge Konvertierung vom Typ unterzogen werden, wenn er von einem XAML-Writer interpretiert wird.  
  
 Die-Escapesequenz ist eine Markuperweiterung und nicht durch eine Klasse unterstützt wird. Es ist jedoch eine Konvention, die XAML-Reader (einschließlich benutzerdefinierter XAML-Reader) berücksichtigen sollten.  
  
 Ein Anführungszeichen (") kann nicht als Escapesequenz auf diese Weise verwendet werden. Wenn Sie ein Anführungszeichen als einen Eigenschaftswert für eine Eigenschaft des Eigenschaftenelements festlegen müssen, verwenden Sie Eigenschaftenelementsyntax und platzieren Sie die Anführungszeichen als Zeichenfolge innerhalb der Property-Element, oder eine XML-Zeichen-Entität. Für einen Content-Eigenschaft kann das Anführungszeichen der gesamte Inhalt sein.  
  
 Die Escapesequenz ({}) ist häufig erforderlich, wenn Sie einen XML-Datentyp angeben, der einen Namespacequalifizierer an einem Ort einschließen muss, in dem dargestellt wird, eine XAML-Markuperweiterung. Dies schließt den Beginn des XAML-Attributwert und in eine Markuperweiterung, sofort nach einem Gleichheitszeichen (=). Das folgende Beispiel zeigt die Escapesequenzen für einen XML-Namespace, der am Anfang des XAML-Attributwert angezeigt wird.  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typkonverter und Markuperweiterungen für XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [XML-Zeichenentitäten und XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
