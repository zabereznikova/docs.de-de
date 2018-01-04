---
title: xml:space-Behandlung in XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b8356cdb47b6b834e8d9a6bb84b26445af6d865
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xmlspace-handling-in-xaml"></a>xml:space-Behandlung in XAML
Die `xml:space` -Attribut ist ein in XML definierten-Attribut, das Verarbeitungsverhalten für signifikante Leerräume innerhalb einer Object-Element deklariert. Dieses Verhalten ist relevant für den gesamten Inhalt (inneren Text), die im Element enthalten sind, in denen `xml:space` deklariert ist, und auch Bereiche untergeordneten Elementen.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- oder –  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Definition für die `xml:space` -Attribut in XAML, einschließlich der beiden möglichen Werte abgeleitet `xml:space` als "spezielles Attribut" von W3C-Spezifikationen für XML definiert.  
  
 Der Standardwert der `xml:space` Attribut wird der Literalwert `"default"`. Für den Wert `"default"`, oder wenn `xml:space` ist nicht angegeben, das Verhalten der Analyse signifikanten Leerräume in diesem Thema definiert die Standardbehandlung entspricht [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Geben Sie zum Beibehalten von Leerräumen in Objekt-Elementinhalt `xml:space="preserve"` für das Objektelement.  
  
 Bei den meisten Interpretationen der `xml:space` -Attributeffekte und der Wert des Attributs auf untergeordnete Elemente beschränkt.  
  
 Eine detaillierte Erläuterung der leerstellenverarbeitung in XAML, finden Sie unter [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
