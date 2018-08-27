---
title: xml:space-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 051cb6b3a314509e9593ee570fd659098670e88b
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925856"
---
# <a name="xmlspace-handling-in-xaml"></a>xml:space-Behandlung in XAML
Die `xml:space` -Attribut ist ein XML-definiertes Attribut, das das Verhalten der Verarbeitung von signifikanten Leerzeichen in einem Objektelement deklariert. Dieses Verhalten gilt für den gesamten Inhalt (inneren Text), die im Element enthalten, in denen `xml:space` wird deklariert, und auch Bereiche von untergeordneten Elementen.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- oder –  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Definition für die `xml:space` -Attribut in XAML, einschließlich der zwei möglichen Werten ergibt sich aus `xml:space` W3C-Spezifikationen für XML als "spezielles Attribut" definiert.  
  
 Der Standardwert der `xml:space` -Attribut ist der literale Wert `"default"`. Für den Wert `"default"`, oder wenn `xml:space` ist nicht angegeben, das Verhalten der signifikanten Leerzeichen Analyse wird die Standardbehandlung verwendet, wie im folgenden Thema beschrieben [White-Space-Verarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Geben Sie zum Beibehalten von Leerraum im Elementinhalt Objekt `xml:space="preserve"` für dieses Objektelement.  
  
 Bei den meisten Interpretationen der `xml:space` -Attributeffekte und der Wert des Attributs definiert und gelten für untergeordnete Elemente.  
  
 Eine vollständige Erläuterung der Leerzeichen in XAML verarbeitet, finden Sie unter [White-Space-Verarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Leerzeichen in XAML verarbeitet](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
