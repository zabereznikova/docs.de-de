---
title: "&#39; &lt;Ausdruck&gt;&#39; kann nicht als eine typeinschränkung verwendet werden"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c7271018a93c97ed90dc272f7f5404c0f0a22d42
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a>&#39; &lt;Ausdruck&gt;&#39; kann nicht als eine typeinschränkung verwendet werden
Eine Einschränkungsliste enthält einen Ausdruck, der keine gültige Einschränkung für einen Typparameter darstellt.  
  
 Eine Einschränkungsliste erzwingt Anforderungen an das Typargument, das an den Typparameter übergeben wird. Sie können die folgenden Anforderungen in beliebiger Kombination angeben:  
  
-   Das Typargument muss mindestens eine Schnittstelle implementieren.  
  
-   Das Typargument darf von höchstens einer Klasse erben.  
  
-   Das Typargument muss einen parameterlosen Konstruktor verfügbar machen, auf den der erstellende Code zugreifen kann (die `New` -Einschränkung muss enthalten sein)  
  
 Wenn Sie keine bestimmte Klasse oder Schnittstelle in die Einschränkungsliste aufnehmen, können Sie eine allgemeinere Anforderung festlegen, indem Sie eine der folgenden Festlegungen treffen:  
  
-   Das Typargument muss ein Werttyp sein (die Einschränkung `Structure` enthalten)  
  
-   Das Typargument muss ein Verweistyp sein (die Einschränkung `Class` enthalten)  
  
 Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.  
  
 **Fehler-ID:** BC32061  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass der Ausdruck und dessen Elemente richtig geschrieben sind.  
  
-   Wenn der Ausdruck die Anforderungen der vorangehenden Liste nicht erfüllt, entfernen Sie ihn aus der Einschränkungsliste.  
  
-   Wenn der Ausdruck auf eine Schnittstelle oder Klasse verweist, stellen Sie sicher, dass der Compiler Zugriff auf diese Schnittstelle oder Klasse hat. Möglicherweise müssen Sie deren Namen qualifizieren und einen Verweis auf Ihr Projekt hinzufügen. Weitere Informationen finden Sie unter "Verweise auf Projekte" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Werttypen und Verweistypen](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 
