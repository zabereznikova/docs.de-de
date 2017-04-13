---
title: "xml:space Handling in XAML | Microsoft Docs"
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
  - "XAML [XAML Services], xml:space attribute"
  - "XAML [XAML Services], whitespace processing"
  - "xml:space attribute [XAML Services]"
  - "whitespace processing [XAML Services]"
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 15
---
# xml:space Handling in XAML
Das `xml:space`\-Attribut ist ein per XML definiertes Attribut, das das relevante Leerraumverarbeitungsverhalten in einem Objektelement deklariert.  Dieses Verhalten ist für den gesamten Inhalt \(inneren Text\) in dem Element relevant, für das `xml:space` deklariert ist, und das bis zu untergeordneten Elementen reicht.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object xml:space="preserve" />  
```  
  
 \- oder \-  
  
```  
<object xml:space="default" />  
```  
  
## Hinweise  
 Die Definition für das `xml:space`\-Attribut in XAML einschließlich der beiden möglichen Werte wird vom `xml:space`\-Element abgeleitet, das von W3C\-Spezifikationen für XML als "spezielles Attribut" definiert ist.  
  
 Der Standardwert des `xml:space`\-Attributs ist der Literalwert `"default"`.  Bei dem Wert `"default"` oder wenn `xml:space` nicht angegeben wurde, wird als Analyseverhalten für signifikante Leerzeichen die Standardbehandlung verwendet, die im Thema [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md) definiert ist.  
  
 Um Leerzeichen innerhalb des Objektelementinhalts beizubehalten, geben Sie `xml:space="preserve"` für das Objektelement an.  
  
 Bei den meisten Interpretationen, sind die `xml:space`\-Attributeffekte und der Wert des Attributs auf untergeordnete Elemente beschränkt.  
  
 Eine vollständige Erläuterung der Leerzeichenverarbeitung in XAML finden Sie unter [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## Siehe auch  
 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)   
 [Übersicht über XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)