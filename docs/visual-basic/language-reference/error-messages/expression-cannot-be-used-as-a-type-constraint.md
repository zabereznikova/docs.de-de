---
title: "&#39;&lt;expression&gt;&#39; cannot be used as a type constraint | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32061"
  - "vbc32061"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32061"
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# &#39;&lt;expression&gt;&#39; cannot be used as a type constraint
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Einschränkungsliste enthält einen Ausdruck, der keine gültige Einschränkung für einen Typparameter darstellt.  
  
 Eine Einschränkungsliste erzwingt Anforderungen an das Typargument, das an den Typparameter übergeben wird.  Sie können die folgenden Anforderungen in beliebiger Kombination angeben:  
  
-   Das Typargument muss mindestens eine Schnittstelle implementieren.  
  
-   Das Typargument darf von höchstens einer Klasse erben.  
  
-   Das Typargument muss einen parameterlosen Konstruktor verfügbar machen, auf den der erstellende Code zugreifen kann \(fügen Sie die `New`\-Einschränkung hinzu\).  
  
 Wenn Sie der Einschränkungsliste keine spezielle Klasse oder Schnittstelle hinzufügen, können Sie eine allgemeinere Anforderung festlegen, indem Sie eine der folgenden Bedingungen angeben:  
  
-   Das Typargument muss ein Werttyp sein \(fügen Sie die `Structure`\-Einschränkung hinzu\).  
  
-   Das Typargument muss ein Verweistyp sein \(fügen Sie die `Class`\-Einschränkung hinzu\).  
  
 Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.  
  
 **Fehler\-ID:** BC32061  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie die richtige Schreibweise des Ausdrucks und seiner Elemente sicher.  
  
-   Wenn der Ausdruck nicht der obigen Liste von Anforderungen entspricht, entfernen Sie ihn aus der Einschränkungsliste.  
  
-   Wenn der Ausdruck auf eine Schnittstelle oder eine Klasse verweist, stellen Sie sicher, dass der Compiler auf diese Schnittstelle bzw. Klasse zugreifen kann.  Möglicherweise müssen Sie ihren Namen qualifizieren, und eventuell müssen Sie dem Projekt einen Verweis hinzufügen.  Weitere Informationen finden Sie in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) unter "Verweise auf Projekte".  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweise hinzufügen"](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)