---
title: "NULL-Literale und Typr&#252;ckschluss (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# NULL-Literale und Typr&#252;ckschluss (Entity SQL)
NULL\-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Typsystem kompatibel.  Damit der Typ eines NULL\-Literals jedoch korrekt geschlossen werden kann, schränkt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] die Verwendung von NULL\-Literalen ein.  
  
## Typisierte Nullen  
 Typisierte Nullen können stets verwendet werden.  Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist.  Beispielsweise kann mit dem folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Konstrukt eine NULL vom Typ **Int16** erstellt werden:  
  
 `(cast(null as Int16))`  
  
## Nicht typisierte NULL\-Literale  
 Nicht typisierte NULL\-Literale können in den folgenden Kontexten verwendet werden:  
  
-   Als Argument eines **CAST**\-Ausdrucks oder eines **TREAT**\-Ausdrucks.  Dies ist die empfohlene Methode zur Erstellung eines typisierten NULL\-Ausdrucks.  
  
-   Als Argument einer Methode oder Funktion.  Dabei gelten die Standardüberladungsregeln.  
  
-   Als eines der Argumente eines arithmetischen Ausdrucks wie "\+", "\-" oder "\/".  Die anderen Argumente können keine NULL\-Literale sein, da sonst kein Typrückschluss möglich ist.  
  
-   Als Argumente eines logischen Ausdrucks \(**AND**, **OR** oder **NOT**\).  Von allen Argumenten ist bekannt, dass sie vom booleschen Typ sind.  
  
-   Als Argument eines **IS NULL**\-Ausdrucks oder eines **IS NOT NULL**\-Ausdrucks.  
  
-   Als ein oder mehrere Argumente eines **LIKE**\-Ausdrucks.  Von allen Argumenten wird angenommen, dass es sich um Zeichenfolgen handelt.  
  
-   Als ein oder mehrere Argumente eines Konstruktors eines benannten Typs.  
  
-   Als ein oder mehrere Argumente eines Multiset\-Konstruktors.  Mindestens ein Argument des Multiset\-Konstruktors muss ein Ausdruck sein, der kein NULL\-Literal ist.  
  
-   Als einer oder mehrere der **THEN**\-Ausdrücke oder **ELSE**\-Ausdrücke in einem **CASE**\-Ausdruck.  Mindestens einer der **THEN**\-Audrücke oder **ELSE**\-Ausdrücke im **CASE**\-Ausdruck muss ein Ausdruck sein, der kein NULL\-Literal ist.  
  
 Nicht typisierte NULL\-Literale können nicht in anderen Szenarios verwendet werden.  Zum Beispiel können sie nicht als Argumente eines Zeilenkonstruktors verwendet werden.  
  
## Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)