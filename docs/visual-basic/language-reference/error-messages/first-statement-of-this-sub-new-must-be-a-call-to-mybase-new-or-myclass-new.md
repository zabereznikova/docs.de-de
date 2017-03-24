---
title: "First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30148"
  - "vbc30148"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30148"
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Die erste Anweisung dieses "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da die Basisklasse "\<Basisname\>" von "\<abgeleiteter Name\>" keine zugreifbare "Sub New" hat, die ohne Argumente aufgerufen werden kann.  
  
 In einer abgeleiteten Klasse muss jeder Konstruktor einen Basisklassenkonstruktor \(`MyBase.New`\) aufrufen.  Wenn die Basisklasse einen Konstruktor ohne Parameter enthält, auf den abgeleitete Klassen zugreifen können, kann `MyBase.New` automatisch aufgerufen werden.  Andernfalls muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden. Dies kann nicht automatisch ausgeführt werden.  In diesem Fall muss die erste Anweisung jedes abgeleiteten Klassenkonstruktors einen parametrisierten Konstruktor der Basisklasse oder einen anderen Konstruktor in der abgeleiteten Klasse aufrufen, die einen Aufruf eines Basisklassenkonstruktors ausführt.  
  
 **Fehler\-ID:** BC30148  
  
### So beheben Sie diesen Fehler  
  
-   Rufen Sie entweder `MyBase.New` unter Angabe der erforderlichen Parameter auf, oder rufen Sie einen Peerkonstruktor auf, der einen solchen Aufruf ausführt.  
  
     Wenn z. B. die Basisklasse über einen Konstruktor verfügt, der als `Public Sub New(ByVal index as Integer)` deklariert ist, kann die erste Anweisung im Konstruktor der abgeleiteten Klasse `MyBase.New(100)`.  
  
## Siehe auch  
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)