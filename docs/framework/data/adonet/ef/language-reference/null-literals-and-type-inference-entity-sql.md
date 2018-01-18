---
title: "NULL-Literale und Typrückschluss (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eeea6a6b1674361a605d5236e203699d08724df3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="null-literals-and-type-inference-entity-sql"></a>NULL-Literale und Typrückschluss (Entity SQL)
NULL-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Typsystem kompatibel. Für den Typ der null-Literal korrekt geschlossen werden jedoch [!INCLUDE[esql](../../../../../../includes/esql-md.md)] schränkt, in denen null-Literal verwendet werden kann.  
  
## <a name="typed-nulls"></a>Typisierte Nullen  
 Typisierte Nullen können stets verwendet werden. Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist. Beispielsweise kann mit dem folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukt eine NULL vom Typ Int16 erstellt werden:  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a>Nicht typisierte NULL-Literale  
 Nicht typisierte NULL-Literale können in den folgenden Kontexten verwendet werden:  
  
-   Als Argument eines CAST-Ausdrucks oder eines TREAT-Ausdrucks. Dies ist die empfohlene Methode zur Erstellung eines typisierten NULL-Ausdrucks.  
  
-   Als Argument einer Methode oder Funktion. Dabei gelten die Standardüberladungsregeln.  
  
-   Als eines der Argumente eines arithmetischen Ausdrucks wie "+", "-" oder "/". Die anderen Argumente können keine NULL-Literale sein, da sonst kein Typrückschluss möglich ist.  
  
-   Als Argumente eines logischen Ausdrucks (AND, OR oder NOT). Von allen Argumenten ist bekannt, dass sie vom booleschen Typ sind.  
  
-   Als Argument eines IS NULL-Ausdrucks oder eines IS NOT NULL-Ausdrucks.  
  
-   Als ein oder mehrere Argumente eines LIKE-Ausdrucks. Von allen Argumenten wird angenommen, dass es sich um Zeichenfolgen handelt.  
  
-   Als ein oder mehrere Argumente eines Konstruktors eines benannten Typs.  
  
-   Als ein oder mehrere Argumente eines Multiset-Konstruktors. Mindestens ein Argument des Multiset-Konstruktors muss ein Ausdruck sein, der kein NULL-Literal ist.  
  
-   Als einer oder mehrere der THEN-Ausdrücke oder ELSE-Ausdrücke in einem CASE-Ausdruck. Mindestens einer der THEN-Audrücke oder ELSE-Ausdrücke im CASE-Ausdruck muss ein Ausdruck sein, der kein NULL-Literal ist.  
  
 Nicht typisierte NULL-Literale können nicht in anderen Szenarios verwendet werden. Zum Beispiel können sie nicht als Argumente eines Zeilenkonstruktors verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
