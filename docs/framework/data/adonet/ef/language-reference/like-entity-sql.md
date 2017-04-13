---
title: "LIKE (Entity SQL) | Microsoft Docs"
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
ms.assetid: 8300e6d2-875b-481e-9ef4-e1e7c12d46fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LIKE (Entity SQL)
Ermittelt, ob ein bestimmter Zeichen\-`String` mit einem angegebenen Muster übereinstimmt.  
  
## Syntax  
  
```  
  
match [NOT] LIKE pattern [ESCAPE escape]  
```  
  
## Argumente  
 `match`  
 Ein [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Ausdruck, der zu einem `String` ausgewertet wird.  
  
 `pattern`  
 Ein Muster, das mit dem angegebenen `String` verglichen werden soll.  
  
 `escape`  
 Ein Escapezeichen.  
  
 NOT  
 Legt fest, dass das Ergebnis von LIKE negiert werden soll.  
  
## Rückgabewert  
 `true`, wenn `string` mit dem Muster übereinstimmt, andernfalls `false`.  
  
## Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Ausdrücke, in denen der LIKE\-Operator verwendet wird, werden ähnlich ausgewertet wie Ausdrücke, in denen Gleichheit als Filterkriterium verwendet wird.[!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Ausdrücke, in denen der LIKE\-Operator verwendet wird, können jedoch sowohl Literale als auch Platzhalterzeichen enthalten.  
  
 In der folgenden Tabelle wird die Syntax des als Muster verwendeten `string` beschrieben.  
  
|Platzhalterzeichen|Beschreibung|Beispiel|  
|------------------------|------------------|--------------|  
|%|Jeder `string` mit null oder mehr Zeichen.|`title like '%computer%'` gibt alle Titel zurück, die das Wort `"computer"` enthalten.|  
|\_ \(Unterstrich\)|Ein beliebiges einzelnes Zeichen.|`firstname like '_ean'`  gibt alle aus vier Buchstaben bestehenden Vornamen zurück, die mit `"ean`" enden wie "Dean" oder "Sean".|  
|\[ \]|Beliebiges einzelnes Zeichen im angegebenen Bereich \(\[a\-f\]\) oder in der angegebenen Menge \(\[abcdef\]\).|`lastname like '[C-P]arsen'` gibt Nachnamen zurück, die mit "arsen" enden und mit einem einzelnen Zeichen zwischen C und P beginnen wie "Carsen" oder "Larsen".|  
|\[^\]|Beliebiges einzelnes Zeichen, das nicht im angegebenen Bereich \(\[^a\-f\]\) oder der angegebenen Menge \(\[^abcdef\]\) liegt.|`lastname like 'de[^l]%'`  gibt alle Nachnamen zurück, die mit "de" beginnen und in denen auf "de" nicht der Buchstabe "l" folgt.|  
  
> [!NOTE]
>  Der LIKE\-Operator und die ESCAPE\-Klausel von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können nicht auf `System.DateTime`\-Werte oder `System.Guid`\-Werte angewendet werden.  
  
 LIKE unterstützt Mustervergleiche im ASCII\- und Unicode\-Format. Wenn alle Parameter ASCII\-Zeichen sind, wird ein ASCII\-Mustervergleich ausgeführt. Wenn eines oder mehrere der Argumente von einem Unicode\-Datentyp sind, werden alle Argumente in Unicode konvertiert, und ein Unicode\-Mustervergleich wird durchgeführt. Bei der Verwendung von Unicode mit dem LIKE\-Operator werden nachfolgende Leerzeichen berücksichtigt. Wird nicht der Typ Unicode verwendet, werden nachfolgende Leerzeichen ignoriert. Die Syntax für die Musterzeichenfolge ist in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dieselbe wie in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  
  
 Zu einem Muster können normale Zeichen und Platzhalter gehören. Bei einem Mustervergleich müssen normale Zeichen exakt mit den im `string` angegebenen Zeichen übereinstimmen. Platzhalterzeichen können mit beliebigen Teilen der Zeichenfolge übereinstimmen. Wenn der LIKE\-Operator mit Platzhalterzeichen verwendet wird, ist er flexibler als die Zeichenfolgen\-Vergleichsoperatoren „\=“ und „\!\=“.  
  
> [!NOTE]
>  Bei Abfragen für einen bestimmten Anbieter können anbieterspezifische Erweiterungen verwendet werden. Solche Konstrukte können jedoch von anderen Anbietern anders behandelt werden. SqlServer unterstützt beispielsweise Muster der Form \[erstes Zeichen\-letztes Zeichen\] und \[^erstes Zeichen\-letztes Zeichen\], wobei die erste Form mit genau einem Zeichen zwischen "erstes Zeichen" und "letztes Zeichen" und die zweite Form mit genau einem Zeichen, das nicht zwischen "erstes Zeichen" und "letztes Zeichen" liegt, übereinstimmt.  
  
### Escape  
 Mithilfe der ESCAPE\-Klausel kann nach Zeichenfolgen gesucht werden, die einen oder mehrere der im vorherigen Abschnitt beschriebenen speziellen Platzhalterzeichen enthalten. Nehmen Sie z. B. an, dass im Titel mehrerer Dokumente das Literal "100%" enthalten ist und Sie diese Dokumente finden möchten. Da das Prozentzeichen \(%\) ein Platzhalterzeichen ist, muss es mithilfe der ESCAPE\-Klausel von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] geschützt werden, damit die Suche durchgeführt werden kann. Im Folgenden sehen Sie ein Beispiel für diesen Filter.  
  
```  
"title like '%100!%%' escape '!'"  
```  
  
 In diesem Suchausdruck wird das Platzhalterzeichen "%", das unmittelbar auf das Ausrufezeichen \(\!\) folgt, als Literal und nicht als Platzhalterzeichen behandelt. Es können alle Zeichen als Escapezeichen verwendet werden außer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Platzhalterzeichen und den eckigen Klammern \(`[ ]`\). Im vorherigen Beispiel wird das Ausrufezeichen \(\!\) als Escapezeichen verwendet.  
  
## Beispiel  
 In den folgenden beiden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Abfragen werden die Operatoren LIKE und ESCAPE verwendet, um zu überprüfen, ob eine bestimmte Zeichenfolge mit einem angegebenen Muster übereinstimmt. Mit der ersten Abfrage wird nach einem `Name` gesucht, der mit den Zeichen `Down_` beginnt. In dieser Abfrage wird die ESCAPE\-Option verwendet, da der Unterstrich \(`_`\) ein Platzhalterzeichen ist. Ohne Angeben der ESCAPE\-Option würde die Abfrage alle `Name`\-Werte zurückgeben, die mit dem Wort `Down` beginnen, gefolgt von einem einzelnen Zeichen, das kein Unterstrich ist. Die Abfragen basieren auf dem AdventureWorks Sales\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIKE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#like)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)