---
title: Eingabezeichensatz (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1a830d9df1f94bd21689cba9a9893cb9c344dfdb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="input-character-set-entity-sql"></a>Eingabezeichensatz (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] akzeptiert in UTF-16 codierte UNICODE-Zeichen.  
  
 Zeichenfolgenliterale können jedes in einfache Anführungszeichen eingeschlossene UTF-16-Zeichen enthalten. Beispiel: N'文字列リテラル'. Beim Vergleich von Zeichenfolgenliteralen werden die ursprünglichen UTF-16-Werte verwendet. Zum Beispiel ist N'ABC' in japanischen und lateinischen Codepages unterschiedlich.  
  
 Kommentare können jedes UTF-16-Zeichen enthalten.  
  
 Escapebezeichner können jedes in eckige Klammern eingeschlossene UTF-16-Zeichen enthalten. Beispiel: [エスケープされた識別子]. Beim Vergleich von UTF-16-Escapebezeichnern wird die Groß-/Kleinschreibung nicht beachtet. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen. Beispielsweise entspricht [ABC] [Abc] Wenn die entsprechenden Zeichen von der gleichen Codepage sind. Wenn die beiden gleichen Bezeichner aus unterschiedlichen Codepages sind, sind sie jedoch nicht entspricht.  
  
 Jedes UTF-16-Leerraumzeichen wird als Leerzeichen aufgefasst.  
  
 Jedes normalisierte UTF-16-Zeilenumbruchzeichen wird als Zeilenumbruch aufgefasst. Zum Beispiel werden '\n' und '\r\n' als Zeilenumbruchzeichen aufgefasst, '\r' jedoch nicht.  
  
 Für Schlüsselwörter, Ausdrücke und Interpunktion können alle UTF-16-Zeichen verwendet werden, die sich zu lateinischen Zeichen normalisieren lassen. Zum Beispiel ist SELECT in einer japanischen Codepage ein gültiges Schlüsselwort.  
  
 Schlüsselwörter, Ausdrücke und Interpunktionszeichen können nur lateinische Zeichen sein. `SELECT` ist in einer japanischen Codepage kein Schlüsselwort. Bei +, -, *, /, =, (, ), ‘, [, ] sowie allen anderen nicht angeführten Sprachkonstrukten können nur lateinische Zeichen verwendet werden.  
  
 Als einfache Bezeichner können nur lateinische Zeichen verwendet werden. Damit wird Mehrdeutigkeit bei Vergleichen vermieden, da ursprüngliche Werte verglichen werden. Zum Beispiel wäre ABC in japanischen und lateinischen Codepages unterschiedlich.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
