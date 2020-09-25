---
title: NULL-Literale und Typrückschluss (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 5797c9f55b1a1c89cc27787af6f9ad7bfffc5767
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185066"
---
# <a name="null-literals-and-type-inference-entity-sql"></a>NULL-Literale und Typrückschluss (Entity SQL)

NULL-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Typsystem kompatibel. Damit der Typ eines NULL-Literals ordnungsgemäß abgeleitet wird, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] erzwingt jedoch bestimmte Einschränkungen für die Verwendung eines NULL-Literals.  
  
## <a name="typed-nulls"></a>Typisierte Nullen  

 Typisierte Nullen können stets verwendet werden. Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist. Beispielsweise kann mit dem folgenden -Konstrukt eine NULL vom Typ Int16 erstellt werden:  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a>Nicht typisierte NULL-Literale  

 Nicht typisierte NULL-Literale können in den folgenden Kontexten verwendet werden:  
  
- Als Argument eines CAST-Ausdrucks oder eines TREAT-Ausdrucks. Dies ist die empfohlene Methode zur Erstellung eines typisierten NULL-Ausdrucks.  
  
- Als Argument einer Methode oder Funktion. Dabei gelten die Standardüberladungsregeln.  
  
- Als eines der Argumente eines arithmetischen Ausdrucks wie "+", "-" oder "/". Die anderen Argumente können keine NULL-Literale sein, da sonst kein Typrückschluss möglich ist.  
  
- Als Argumente eines logischen Ausdrucks (AND, OR oder NOT). Von allen Argumenten ist bekannt, dass sie vom booleschen Typ sind.  
  
- Als Argument eines IS NULL-Ausdrucks oder eines IS NOT NULL-Ausdrucks.  
  
- Als ein oder mehrere Argumente eines LIKE-Ausdrucks. Von allen Argumenten wird angenommen, dass es sich um Zeichenfolgen handelt.  
  
- Als ein oder mehrere Argumente eines Konstruktors eines benannten Typs.  
  
- Als ein oder mehrere Argumente eines Multiset-Konstruktors. Mindestens ein Argument des Multiset-Konstruktors muss ein Ausdruck sein, der kein NULL-Literal ist.  
  
- Als einer oder mehrere der THEN-Ausdrücke oder ELSE-Ausdrücke in einem CASE-Ausdruck. Mindestens einer der THEN-Audrücke oder ELSE-Ausdrücke im CASE-Ausdruck muss ein Ausdruck sein, der kein NULL-Literal ist.  
  
 Nicht typisierte NULL-Literale können nicht in anderen Szenarios verwendet werden. Zum Beispiel können sie nicht als Argumente eines Zeilenkonstruktors verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
