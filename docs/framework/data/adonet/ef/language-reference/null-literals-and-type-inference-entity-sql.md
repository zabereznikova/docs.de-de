---
title: NULL-Literale und Typrückschluss (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 22b548f2fc889b20f76a41001438f75c25f99c00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760401"
---
# <a name="null-literals-and-type-inference-entity-sql"></a>NULL-Literale und Typrückschluss (Entity SQL)
NULL-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Typsystem kompatibel. Für den Typ der null-Literal korrekt geschlossen werden jedoch [!INCLUDE[esql](../../../../../../includes/esql-md.md)] gelten bestimmte Einschränkungen auf, in dem ein null-Literal verwendet werden kann.  
  
## <a name="typed-nulls"></a>Typisierte Nullen  
 Typisierte Nullen können stets verwendet werden. Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist. Beispielsweise kann mit dem folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukt eine NULL vom Typ Int16 erstellt werden:  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
