---
title: xml:space-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458796"
---
# <a name="xmlspace-handling-in-xaml"></a>xml:space-Behandlung in XAML
Das `xml:space`-Attribut ist ein XML-definiertes Attribut, das das signifikante Verhalten der Leerraum Verarbeitung in einem Object-Element deklariert. Dieses Verhalten ist relevant für den gesamten Inhalt (inneren Text), der in dem Element enthalten ist, in dem `xml:space` deklariert ist, und auch Bereiche für untergeordnete Elemente.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- oder -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Definition für das `xml:space`-Attribut in XAML, einschließlich der beiden möglichen Werte, wird von `xml:space` abgeleitet, wie von den W3C-Spezifikationen für XML als "spezielles Attribut" definiert.  
  
 Der Standardwert des `xml:space` Attributs ist der Literalwert `"default"`. Für den Wert `"default"`oder wenn `xml:space` überhaupt nicht angegeben wird, ist das Verhalten der signifikanten Leerraum-Verarbeitung die Standardbehandlung, wie im Thema [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md)definiert.  
  
 Um Leerraum im Inhalt von Objekt Elementen beizubehalten, geben Sie `xml:space="preserve"` für dieses Objekt Element an.  
  
 Bei den meisten Interpretationen werden die Auswirkungen des `xml:space` Attributs und der Wert des Attributs auf untergeordnete Elemente beschränkt.  
  
 Eine vollständige Erläuterung der Leerraum Verarbeitung in XAML finden Sie unter [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
