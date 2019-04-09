---
title: LIKE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8300e6d2-875b-481e-9ef4-e1e7c12d46fa
ms.openlocfilehash: 8f210c83a8220f11a5e0a461c8b72466f00a4e37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197710"
---
# <a name="like-entity-sql"></a>LIKE (Entity SQL)
Ermittelt, ob ein bestimmter Zeichen-`String` mit einem angegebenen Muster übereinstimmt.  
  
## <a name="syntax"></a>Syntax  
  
```  
match [NOT] LIKE pattern [ESCAPE escape]  
```  
  
## <a name="arguments"></a>Argumente  
 `match`  
 Ein [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Ausdruck, ergibt eine `String`.  
  
 `pattern`  
 Ein Muster, das mit dem angegebenen `String` verglichen werden soll.  
  
 `escape`  
 Ein Escapezeichen.  
  
 NICHT  
 Legt fest, dass das Ergebnis von LIKE negiert werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn die `string` mit dem Muster übereinstimmt, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Ausdrücke, die den LIKE-Operator werden im Wesentlichen die gleiche Weise wie Ausdrücke ausgewertet, die auf Gleichheit als Filterkriterium verwenden. Allerdings [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Ausdrücke, die den LIKE-Operator verwenden können sowohl Literale als auch Platzhalterzeichen enthalten.  
  
 In der folgenden Tabelle wird die Syntax des als Muster verwendeten `string` beschrieben.  
  
|Platzhalterzeichen|Beschreibung|Beispiel|  
|------------------------|-----------------|-------------|  
|%|Jeder `string` mit null oder mehr Zeichen.|`title like '%computer%'` Sucht alle Titel mit dem Wort `"computer"` an einer beliebigen Stelle im Titel.|  
|_ (Unterstrich)|Ein beliebiges einzelnes Zeichen.|`firstname like '_ean'` findet alle Vornamen mit vier Buchstaben, die mit `"ean`, "wie z. B. Dean" oder "Sean.|  
|[ ]|Beliebiges einzelnes Zeichen im angegebenen Bereich ([a-f]) oder in der angegebenen Menge ([abcdef]).|`lastname like '[C-P]arsen'` Gibt Nachnamen mit "Arsen" enden und mit einem einzelnen Zeichen zwischen C und P beginnen wie Carsen oder "Larsen".|  
|[^]|Beliebiges einzelnes Zeichen, das nicht im angegebenen Bereich ([^a-f]) oder der angegebenen Menge ([^abcdef]) liegt.|`lastname like 'de[^l]%'` Sucht alle Nachnamen zurück, die mit "de" beginnen, und schließen Sie nicht der Buchstabe "l".|  
  
> [!NOTE]
>  Der LIKE-Operator und die ESCAPE-Klausel von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können nicht auf `System.DateTime`-Werte oder `System.Guid`-Werte angewendet werden.  
  
 LIKE unterstützt Mustervergleiche im ASCII- und Unicode-Format. Wenn alle Parameter ASCII-Zeichen sind, wird ein ASCII-Mustervergleich ausgeführt. Wenn eines oder mehrere der Argumente von einem Unicode-Datentyp sind, werden alle Argumente in Unicode konvertiert, und ein Unicode-Mustervergleich wird durchgeführt. Bei der Verwendung von Unicode mit dem LIKE-Operator werden nachfolgende Leerzeichen berücksichtigt. Wird nicht der Typ Unicode verwendet, werden nachfolgende Leerzeichen ignoriert. Syntax für die Musterzeichenfolge des [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist identisch mit der [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  
  
 Zu einem Muster können normale Zeichen und Platzhalter gehören. Bei einem Mustervergleich müssen normale Zeichen exakt mit den im `string` angegebenen Zeichen übereinstimmen. Platzhalterzeichen können mit beliebigen Teilen der Zeichenfolge übereinstimmen. Wenn der LIKE-Operator mit Platzhalterzeichen verwendet wird, ist er flexibler als die Zeichenfolgen-Vergleichsoperatoren „=“ und „!=“.  
  
> [!NOTE]
>  Bei Abfragen für einen bestimmten Anbieter können anbieterspezifische Erweiterungen verwendet werden. Solche Konstrukte können jedoch von anderen Anbietern anders behandelt werden. SqlServer unterstützt beispielsweise Muster der Form [erstes Zeichen-letztes Zeichen] und [^erstes Zeichen-letztes Zeichen], wobei die erste Form mit genau einem Zeichen zwischen "erstes Zeichen" und "letztes Zeichen" und die zweite Form mit genau einem Zeichen, das nicht zwischen "erstes Zeichen" und "letztes Zeichen" liegt, übereinstimmt.  
  
### <a name="escape"></a>Escape  
 Mithilfe der ESCAPE-Klausel kann nach Zeichenfolgen gesucht werden, die einen oder mehrere der im vorherigen Abschnitt beschriebenen speziellen Platzhalterzeichen enthalten. Nehmen Sie z. B. an, dass im Titel mehrerer Dokumente das Literal "100%" enthalten ist und Sie diese Dokumente finden möchten. Da das Prozentzeichen (%) Zeichen ist ein Platzhalterzeichen, Sie müssen mit Escapezeichen versehen die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ESCAPE-Klausel, um die Suche erfolgreich ausgeführt. Im Folgenden sehen Sie ein Beispiel für diesen Filter.  
  
```  
"title like '%100!%%' escape '!'"  
```  
  
 In diesem Suchausdruck wird das Platzhalterzeichen "%", das unmittelbar auf das Ausrufezeichen (!) folgt, als Literal und nicht als Platzhalterzeichen behandelt. Sie können jedes Zeichen verwenden, als Escape-Zeichen mit Ausnahme von der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Platzhalterzeichen und den eckigen Klammern (`[ ]`) Zeichen. Im vorherigen Beispiel wird das Ausrufezeichen (!) als Escapezeichen verwendet.  
  
## <a name="example"></a>Beispiel  
 Die folgenden beiden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfragen verwenden die LIKE und ESCAPE-Operatoren, um festzustellen, ob eine bestimmte Zeichenfolge mit einem angegebenes Muster übereinstimmt. Die erste Abfrage sucht die `Name` , beginnt mit den Zeichen `Down_`. In dieser Abfrage wird die ESCAPE-Option verwendet, da der Unterstrich (`_`) ein Platzhalterzeichen ist. Ohne Angeben der ESCAPE`Name`-Option würde die Abfrage alle `Down`-Werte zurückgeben, die mit dem Wort  beginnen, gefolgt von einem einzelnen Zeichen, das kein Unterstrich ist. Die Abfragen basieren auf dem AdventureWorks Sales-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIKE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#like)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
