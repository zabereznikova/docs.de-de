---
title: "&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;. Re-implementation of &lt;type&gt; assumed | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42015"
  - "bc42015"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42015"
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;. Re-implementation of &lt;type&gt; assumed
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

In einer Eigenschaft, einer Prozedur oder einem Ereignis in einer abgeleiteten Klasse wird eine `Implements`\-Klausel verwendet, die einen Schnittstellenmember angibt, der bereits in der Basisklasse implementiert ist.  
  
 Eine abgeleitete Klasse kann einen Schnittstellenmember erneut implementieren, der durch seine Basisklasse implementiert ist.  Dies ist nicht mit dem Überschreiben der Basisklassenimplementierung identisch.  Weitere Informationen finden Sie unter [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42015  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie den Schnittstellenmember erneut implementieren möchten, müssen Sie keine Maßnahmen ergreifen.  Code in der abgeleiteten Klasse greift auf den erneut implementierten Member zu, es sei denn, Sie verwenden das `MyBase`\-Schlüsselwort, um auf die Basisklassenimplementierung zuzugreifen.  
  
-   Wenn Sie den Schnittstellenmember nicht erneut implementieren möchten, entfernen Sie die `Implements`\-Klausel aus der Deklaration der Eigenschaft, der Prozedur bzw. des Ereignisses.  
  
## Siehe auch  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)