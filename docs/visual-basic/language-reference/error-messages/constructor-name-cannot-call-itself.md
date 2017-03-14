---
title: "Constructor &#39;&lt;name&gt;&#39; cannot call itself | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30298"
  - "vbc30298"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30298"
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Constructor &#39;&lt;name&gt;&#39; cannot call itself
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine `Sub New`\-Prozedur in einer Klasse oder Struktur ruft sich selbst auf.  
  
 Der Zweck eines Konstruktors besteht im Initialisieren der Instanz einer Klasse oder Struktur, wenn die Klasse bzw. Struktur das erste Mal erstellt wird.  Eine Klasse oder Struktur kann über mehrere Konstruktoren verfügen, sofern alle Konstruktoren unterschiedliche Parameterlisten aufweisen.  Ein Konstruktor kann einen anderen Konstruktor aufrufen, um zusätzlich zu den eigenen Funktionen die Funktionen dieses Konstruktor auszuführen.  Der Aufruf eines Konstruktors durch sich selbst ist jedoch sinnlos und führt zu einer Endlosschleife, falls solch ein Aufruf zugelassen wird.  
  
 **Fehler\-ID:** BC30298  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Parameterliste des aufgerufenen Konstruktors.  Sie muss sich von der Parameterliste des aufrufenden Konstruktors unterscheiden.  
  
2.  Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufzurufen, entfernen Sie den `Sub New`\-Aufruf vollständig.  
  
## Siehe auch  
 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)