---
title: LIKE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8300e6d2-875b-481e-9ef4-e1e7c12d46fa
ms.openlocfilehash: 58828b812ce374a664e4d232b707f22d5ca438c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912281"
---
# <a name="like-entity-sql"></a>LIKE (Entity SQL)
Ermittelt, ob ein bestimmter Zeichen-`String` mit einem angegebenen Muster übereinstimmt.  
  
## <a name="syntax"></a>Syntax  
  
```  
match [NOT] LIKE pattern [ESCAPE escape]  
```  
  
## <a name="arguments"></a>Argumente  
 `match`  
 Ein [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Ausdruck, der als `String`ausgewertet wird.  
  
 `pattern`  
 Ein Muster, das mit dem angegebenen `String` verglichen werden soll.  
  
 `escape`  
 Ein Escapezeichen.  
  
 NICHT  
 Legt fest, dass das Ergebnis von LIKE negiert werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn `string` mit dem Muster übereinstimmt, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]Ausdrücke, die den Like-Operator verwenden, werden auf die gleiche Weise ausgewertet wie Ausdrücke, die Gleichheit als Filterkriterien verwenden. Ausdrücke, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] die den Like-Operator verwenden, können jedoch sowohl Literale als auch Platzhalter Zeichen enthalten.  
  
 In der folgenden Tabelle wird die Syntax des als Muster verwendeten `string` beschrieben.  
  
|Platzhalterzeichen|Beschreibung|Beispiel|  
|------------------------|-----------------|-------------|  
|%|Jeder `string` mit null oder mehr Zeichen.|`title like '%computer%'`sucht alle Titel mit dem Wort `"computer"` an beliebiger Stelle im Titel.|  
|_ (Unterstrich)|Ein beliebiges einzelnes Zeichen.|`firstname like '_ean'`sucht alle aus vier Buchstaben bestehenden Vornamen, die `"ean`mit beginnen, z. b. "Dean" oder "Sean".|  
|[ ]|Beliebiges einzelnes Zeichen im angegebenen Bereich ([a-f]) oder in der angegebenen Menge ([abcdef]).|`lastname like '[C-P]arsen'`sucht nach Nachnamen, die mit "Arsen" enden und mit einem beliebigen einzelnen Zeichen zwischen C und P beginnen, wie z. b. Carsen oder Larsen.|  
|[^]|Beliebiges einzelnes Zeichen, das nicht im angegebenen Bereich ([^a-f]) oder der angegebenen Menge ([^abcdef]) liegt.|`lastname like 'de[^l]%'`sucht alle Nachnamen, die mit "de" beginnen, und schließt "l" nicht als folgenden Buchstaben ein.|  
  
> [!NOTE]
> Der LIKE-Operator und die ESCAPE-Klausel von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können nicht auf `System.DateTime`-Werte oder `System.Guid`-Werte angewendet werden.  
  
 LIKE unterstützt Mustervergleiche im ASCII- und Unicode-Format. Wenn alle Parameter ASCII-Zeichen sind, wird ein ASCII-Mustervergleich ausgeführt. Wenn eines oder mehrere der Argumente von einem Unicode-Datentyp sind, werden alle Argumente in Unicode konvertiert, und ein Unicode-Mustervergleich wird durchgeführt. Bei der Verwendung von Unicode mit dem LIKE-Operator werden nachfolgende Leerzeichen berücksichtigt. Wird nicht der Typ Unicode verwendet, werden nachfolgende Leerzeichen ignoriert. Die Syntax der Muster Zeichenfolge von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist mit der von Transact-SQL identisch.  
  
 Zu einem Muster können normale Zeichen und Platzhalter gehören. Bei einem Mustervergleich müssen normale Zeichen exakt mit den im `string` angegebenen Zeichen übereinstimmen. Platzhalterzeichen können mit beliebigen Teilen der Zeichenfolge übereinstimmen. Wenn der LIKE-Operator mit Platzhalterzeichen verwendet wird, ist er flexibler als die Zeichenfolgen-Vergleichsoperatoren „=“ und „!=“.  
  
> [!NOTE]
> Bei Abfragen für einen bestimmten Anbieter können anbieterspezifische Erweiterungen verwendet werden. Solche Konstrukte können jedoch von anderen Anbietern anders behandelt werden. SqlServer unterstützt beispielsweise Muster der Form [erstes Zeichen-letztes Zeichen] und [^erstes Zeichen-letztes Zeichen], wobei die erste Form mit genau einem Zeichen zwischen "erstes Zeichen" und "letztes Zeichen" und die zweite Form mit genau einem Zeichen, das nicht zwischen "erstes Zeichen" und "letztes Zeichen" liegt, übereinstimmt.  
  
### <a name="escape"></a>Escape  
 Mithilfe der ESCAPE-Klausel kann nach Zeichenfolgen gesucht werden, die einen oder mehrere der im vorherigen Abschnitt beschriebenen speziellen Platzhalterzeichen enthalten. Nehmen Sie z. B. an, dass im Titel mehrerer Dokumente das Literal "100%" enthalten ist und Sie diese Dokumente finden möchten. Da der Prozentsatz (%) das Zeichen ist ein Platzhalter Zeichen. Sie müssen es mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] der Escape-Klausel versehen, um die Suche erfolgreich auszuführen. Im Folgenden sehen Sie ein Beispiel für diesen Filter.  
  
```  
"title like '%100!%%' escape '!'"  
```  
  
 In diesem Suchausdruck wird das Platzhalterzeichen "%", das unmittelbar auf das Ausrufezeichen (!) folgt, als Literal und nicht als Platzhalterzeichen behandelt. Sie können ein beliebiges Zeichen als Escapezeichen verwenden, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] mit Ausnahme der Platzhalter Zeichen und`[ ]`der eckigen Klammer Zeichen (). Im vorherigen Beispiel wird das Ausrufezeichen (!) als Escapezeichen verwendet.  
  
## <a name="example"></a>Beispiel  
 Die folgenden beiden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfragen verwenden die like-und Escape-Operatoren, um zu bestimmen, ob eine bestimmte Zeichenfolge mit einem angegebenen Muster übereinstimmt. Die erste Abfrage sucht nach der `Name` , die mit den- `Down_`Zeichen beginnt. In dieser Abfrage wird die ESCAPE-Option verwendet, da der Unterstrich (`_`) ein Platzhalterzeichen ist. Ohne Angeben der ESCAPE`Name`-Option würde die Abfrage alle `Down`-Werte zurückgeben, die mit dem Wort  beginnen, gefolgt von einem einzelnen Zeichen, das kein Unterstrich ist. Die Abfragen basieren auf dem AdventureWorks Sales-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIKE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#like)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
