---
title: Eingabezeichensatz (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 7bed10f6e4a9fb01abe825e5eb798da2d866ca84
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976758"
---
# <a name="input-character-set-entity-sql"></a>Eingabezeichensatz (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] akzeptiert in UTF-16 codierte UNICODE-Zeichen.  
  
 Zeichenfolgenliterale können jedes in einfache Anführungszeichen eingeschlossene UTF-16-Zeichen enthalten. Beispiel: N'文字列リテラル'. Beim Vergleich von Zeichenfolgenliteralen werden die ursprünglichen UTF-16-Werte verwendet. Zum Beispiel ist N'ABC' in japanischen und lateinischen Codepages unterschiedlich.  
  
 Kommentare können jedes UTF-16-Zeichen enthalten.  
  
 Escapebezeichner können jedes in eckige Klammern eingeschlossene UTF-16-Zeichen enthalten. Beispiel: [エスケープされた識別子]. Beim Vergleich von UTF-16-Escapebezeichnern wird die Groß-/Kleinschreibung nicht beachtet. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen. Beispielsweise entspricht [ABC] [Abc] Wenn die entsprechenden Zeichen von der gleichen Codepage sind. Wenn die beiden gleichen Bezeichner aus anderen Codepages sind, sind sie jedoch nicht entspricht.  
  
 Jedes UTF-16-Leerraumzeichen wird als Leerzeichen aufgefasst.  
  
 Jedes normalisierte UTF-16-Zeilenumbruchzeichen wird als Zeilenumbruch aufgefasst. Zum Beispiel werden '\n' und '\r\n' als Zeilenumbruchzeichen aufgefasst, '\r' jedoch nicht.  
  
 Für Schlüsselwörter, Ausdrücke und Interpunktion können alle UTF-16-Zeichen verwendet werden, die sich zu lateinischen Zeichen normalisieren lassen. Zum Beispiel ist SELECT in einer japanischen Codepage ein gültiges Schlüsselwort.  
  
 Schlüsselwörter, Ausdrücke und Interpunktionszeichen können nur lateinische Zeichen sein. `SELECT` ist in einer japanischen Codepage kein Schlüsselwort. +,-, \*, /, =, (,), ', [,], und alle anderen nicht angeführten Sprachkonstrukten Sprachkonstrukt kann nur lateinische Zeichen sein.  
  
 Als einfache Bezeichner können nur lateinische Zeichen verwendet werden. Damit wird Mehrdeutigkeit bei Vergleichen vermieden, da ursprüngliche Werte verglichen werden. Zum Beispiel wäre ABC in japanischen und lateinischen Codepages unterschiedlich.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
