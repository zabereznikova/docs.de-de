---
title: "Eingabezeichensatz (Entity SQL) | Microsoft Docs"
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
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Eingabezeichensatz (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] akzeptiert in UTF\-16 codierte UNICODE\-Zeichen.  
  
 Zeichenfolgenliterale können jedes in einfache Anführungszeichen eingeschlossene UTF\-16\-Zeichen enthalten.  Beispiel: N'文字列リテラル'.  Beim Vergleich von Zeichenfolgenliteralen werden die ursprünglichen UTF\-16\-Werte verwendet.  Zum Beispiel ist N'ABC' in japanischen und lateinischen Codepages unterschiedlich.  
  
 Kommentare können jedes UTF\-16\-Zeichen enthalten.  
  
 Escapebezeichner können jedes in eckige Klammern eingeschlossene UTF\-16\-Zeichen enthalten.  Beispiel: \[エスケープされた識別子\].  Beim Vergleich von UTF\-16\-Escapebezeichnern wird die Groß\-\/Kleinschreibung nicht beachtet.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen.  Beispiel: \[ABC\] ist äquivalent zu \[abc\], wenn die entsprechenden Zeichen in der gleichen Codepage enthalten sind.  Stammen die beiden gleichen Bezeichner jedoch aus anderen Codepages, sind sie nicht äquivalent.  
  
 Jedes UTF\-16\-Leerraumzeichen wird als Leerzeichen aufgefasst.  
  
 Jedes normalisierte UTF\-16\-Zeilenumbruchzeichen wird als Zeilenumbruch aufgefasst.  Zum Beispiel werden '\\n' und '\\r\\n' als Zeilenumbruchzeichen aufgefasst, '\\r' jedoch nicht.  
  
 Für Schlüsselwörter, Ausdrücke und Interpunktion können alle UTF\-16\-Zeichen verwendet werden, die sich zu lateinischen Zeichen normalisieren lassen.  Zum Beispiel ist **SELECT** in einer japanischen Codepage ein gültiges Schlüsselwort.  
  
 Schlüsselwörter, Ausdrücke und Interpunktionszeichen können nur lateinische Zeichen sein.  `SELECT` ist in einer japanischen Codepage kein Schlüsselwort.  Bei \+, \-, \*, \/, \=, \(, \), ‘, \[, \] sowie allen anderen nicht angeführten Sprachkonstrukten können nur lateinische Zeichen verwendet werden.  
  
 Als einfache Bezeichner können nur lateinische Zeichen verwendet werden.  Damit wird Mehrdeutigkeit bei Vergleichen vermieden, da ursprüngliche Werte verglichen werden.  Zum Beispiel wäre ABC in japanischen und lateinischen Codepages unterschiedlich.  
  
## Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)