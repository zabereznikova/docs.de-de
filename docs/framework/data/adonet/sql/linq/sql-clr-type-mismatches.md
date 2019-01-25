---
title: SQL-CLR-Typenkonflikte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
ms.openlocfilehash: 0abb1bd25c40ba55806fe80b39db1ac418f3f308
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700948"
---
# <a name="sql-clr-type-mismatches"></a>SQL-CLR-Typenkonflikte
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatisiert einen Großteil des Übersetzungsprozesses zwischen dem Objektmodell und SQL Server. Trotzdem verhindern einige Situationen die genaue Übersetzung. In den folgenden Abschnitten werden diese wichtigen Konflikte zwischen den CLR (Common Language Runtime)-Typen und den SQL Server-Datenbanktypen zusammengefasst. Sie finden weitere Informationen zu bestimmten Typmappings und funktionsübersetzungen am [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) und [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).  
  
## <a name="data-types"></a>Datentypen  
 Eine Übersetzung zwischen CLR und SQL Server wird ausgeführt, wenn eine Abfrage an die Datenbank gesendet und die Ergebnisse an das Objektmodell zurückgesendet werden. Zum Beispiel erfordert folgende Transact-SQL-Abfrage zwei Wertekonvertierungen:  
  
```  
Select DateOfBirth From Customer Where CustomerId = @id     
```  
  
 Damit die Abfrage von SQL Server ausgeführt werden kann, muss der Wert für den Transact-SQL-Parameter angegeben werden. In diesem Beispiel muss der `id`-Parameterwert zunächst von einem CLR-<xref:System.Int32?displayProperty=nameWithType>-Typ in einen SQL Server-`INT`-Typ übersetzt werden, damit die Datenbank den Wert interpretieren kann. Um anschließend die Ergebnisse abzurufen, muss die `DateOfBirth`-Spalte von SQL Server von einem SQL Server-`DATETIME`-Typ in einen CLR-<xref:System.DateTime?displayProperty=nameWithType>-Typ übersetzt werden, damit er im Objektmodell verwendet werden kann. In diesem Beispiel haben die Typen im CLR-Objektmodell und der SQL Server-Datenbank natürliche Mappings. Dies ist jedoch nicht immer der Fall.  
  
### <a name="missing-counterparts"></a>Fehlende Gegenstücke  
 Die folgenden Typen weisen keine angemessenen Gegenstücke auf.  
  
-   Konflikte im CLR-<xref:System>-Namespace:  
  
    -   **Ganze Zahlen ohne Vorzeichen**. Diese Typen werden in der Regel größeren Äquivalenten mit Vorzeichen zugeordnet, um ein Überlaufen zu vermeiden. Literale können auf der Basis des Werts in eine mit Vorzeichen versehene Zahl der gleichen oder einer kleineren Größe umgewandelt werden.  
  
    -   **Boolean**. Diese Typen können einem Bit oder einem größeren numerischen Wert/einer Zeichenfolge zugeordnet werden. Ein Literal kann einem Ausdruck zugeordnet werden, der den gleichen Wert ergibt (Beispiel: `1=1` in SQL für `True` in CLS).  
  
    -   **TimeSpan**. Dieser Typ steht für den Unterschied zwischen zwei `DateTime`-Werten und entspricht nicht dem `timestamp` von SQL Server. Die CLR-<xref:System.TimeSpan?displayProperty=nameWithType> wird möglicherweise auch dem `TIME`-Typ in SQL Server zugeordnet. Der `TIME`-Typ in SQL Server kann nur positive Werte unter 24 Stunden darstellen. Die CLR-<xref:System.TimeSpan> hat einen viel größeren Bereich.  
  
    > [!NOTE]
    >  SQL Server-spezifische [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] Typen im <xref:System.Data.SqlTypes> sind in diesem Vergleich nicht enthalten.  
  
-   Konflikte in SQL Server:  
  
    -   **Fester Länge Zeichentypen**. Transact-SQL unterscheidet zwischen Unicode- und nicht-Unicode-Kategorien und verfügt über drei unterschiedliche Arten in den einzelnen Kategorien: feste Länge `nchar` / `char`, variabler Länge `nvarchar` / `varchar`, und größere `ntext` / `text`. Typen mit Zeichen fester Länge könnten zum Abrufen von Zeichen dem CLR-<xref:System.Char?displayProperty=nameWithType>-Typ zugeordnet werden. Hinsichtlich Konvertierung und Verhalten entsprechen sie jedoch nicht dem gleichen Typ.  
  
    -   **Bit**. Obwohl die `bit`-Domäne die gleiche Anzahl von Werten aufweist wie `Nullable<Boolean>`, handelt es sich um verschiedene Typen. `Bit` übernimmt die Werte der `1` und `0` anstelle von `true` / `false`, und nicht als äquivalent zu booleschen Ausdrücken verwendet werden.  
  
    -   **Zeitstempel**. Im Gegensatz zum CLR-<xref:System.TimeSpan?displayProperty=nameWithType>-Typ stellt der SQL Server-`TIMESTAMP`-Typ eine von der Datenbank erzeugte Zahl mit 8 Bytes dar, die für jedes Update eindeutig ist und nicht auf dem Unterschied zwischen <xref:System.DateTime>-Werten basiert.  
  
    -   **Money** und **SmallMoney**. Diese Typen können <xref:System.Decimal> zugewiesen werden, sie sind jedoch grundsätzlich verschieden und werden von serverbasierten Funktionen und Konvertierungen dementsprechend behandelt.  
  
### <a name="multiple-mappings"></a>Mehrere Mappings  
 Einem oder mehreren CLR-Datentypen können viele SQL Server-Datentypen zugeordnet werden. Genauso können einem oder mehreren SQL Server-Typen mehrere CLR-Typen zugeordnet werden. Zwar wird ein Mapping möglicherweise von LINQ to SQL unterstützt, dies bedeutet jedoch nicht, dass die beiden zwischen CLR und SQL Server zugeordneten Typen in Genauigkeit, Bereich und Semantik übereinstimmen. Einige Mappings schließen möglicherweise Abweichungen in einer oder allen Dimensionen ein. Finden Sie Informationen zu diesen potenziellen unterschieden für die verschiedenen mappingmöglichkeiten am [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
### <a name="user-defined-types"></a>Benutzerdefinierte Typen  
 Benutzerdefinierte CLR-Typen werden für die Überbrückung der Typsystemlücke entworfen. Sie fördern jedoch interessante Aspekte der Typversionierung zu Tage. Eine Versionsänderung auf dem Client kann ggf. nicht durch Änderung des Typs auf dem Datenbankserver zugeordnet werden. Eine solche Änderung führt zu einem weiteren Typenkonflikt, bei dem die Typsemantik möglicherweise abweicht und die Versionslücke sichtbar wird. Weitere Komplikationen treten auf, wenn Vererbungshierarchien in aufeinander folgenden Versionen umgestaltet werden.  
  
## <a name="expression-semantics"></a>Ausdruckssemantik  
 Zusätzlich zum paarweisen Konflikt zwischen CLR- und Datenbanktypen wird die Komplexität des Konflikts durch Ausdrücke erhöht. Konflikte in der Operatorsemantik, der Funktionssemantik, der impliziten Typkonvertierung und in den Rangfolgenregeln müssen berücksichtigt werden.  
  
 Die folgenden Unterabschnitte veranschaulichen den Konflikt zwischen anscheinend ähnlichen Ausdrücken. Möglicherweise können SQL-Ausdrücke erzeugt werden, die zu einem angegebenen CLR-Ausdruck semantisch äquivalent sind. Es ist jedoch nicht klar, ob die semantischen Unterschiede zwischen anscheinend ähnlichen Ausdrücken für einen CLR-Benutzer erkennbar sind und ob die für die semantische Gleichheit erforderlichen Änderungen beabsichtigt sind oder nicht. Dies ist insbesondere dann ein Problem, wenn ein Ausdruck für einen Satz von Werten ausgewertet wird. Die Sichtbarkeit der Unterschiede kann je nach den Daten variieren und lässt sich beim Codieren und Debuggen nur schwer identifizieren.  
  
### <a name="null-semantics"></a>NULL-Semantik  
 SQL-Ausdrücke stellen eine Logik mit drei Werten für boolesche Ausdrücke bereit. Das Ergebnis kann den Wert true, false oder NULL haben. Im Gegensatz dazu gibt CLR ein boolesches Ergebnis mit zwei Werten für Vergleiche an, die NULL-Werte einschließen. Betrachten Sie folgenden Code:  
  
 [!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
 [!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]  
  
```  
-- Assume col1 and col2 are integer columns with null values.   
-- Assume that ANSI null behavior has not been explicitly  
--    turned off.  
Select …  
From …  
Where col1 = col2  
-- Evaluates to null, not true and the corresponding row is not  
--     selected.  
-- To obtain matching behavior (i -> col1, j -> col2) change  
--     the query to the following:  
Select …  
From …  
Where  
    col1 = col2   
or (col1 is null and col2 is null)  
-- (Visual Basic 'Nothing'.)  
```  
  
 Ein ähnliches Problem tritt bei Annahme von Ergebnissen mit zwei Werten auf.  
  
 [!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
 [!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]  
  
```  
-- Assume col1 and col2 are nullable columns.  
-- Assume that ANSI null behavior has not been explicitly  
--     turned off.  
Select …  
From …  
Where  
    col1 = col2        
or col1 != col2  
-- Visual Basic: col1 <> col2.  
  
-- Excludes the case where the boolean expression evaluates  
--     to null. Therefore the where clause does not always  
--     evaluate to true.  
```  
  
 Im vorherigen Fall erhalten Sie bei der SQL-Erzeugung ein gleichwertiges Verhalten, die Übersetzung kann jedoch Ihre Absicht möglicherweise nicht korrekt widerspiegeln.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entstehen keine C# `null` oder Visual Basic `nothing` Vergleichssemantik auf SQL. Vergleichsoperatoren werden syntaktisch zu ihren SQL-Entsprechungen übersetzt. Die Semantik reflektiert SQL-Semantik, wie von den Server- oder Verbindungseinstellungen definiert. Die beiden NULL-Werte gelten bei den standardmäßigen SQL Server-Einstellungen als ungleich (obwohl Sie die Semantik über die Einstellungen ändern können). Dennoch berücksichtigt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keine Servereinstellungen in der Abfrageübersetzung.  
  
 Ein Vergleich mit dem `null`-Literal (`nothing`-Literal) wird zur entsprechenden SQL-Version (`is null` oder `is not null`) übersetzt.  
  
 Der Wert von `null` (`nothing`) in der Zusammenstellung wird von SQL Server definiert. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ändert die Zusammenstellung nicht.  
  
### <a name="type-conversion-and-promotion"></a>Typkonvertierung und Heraufstufung  
 SQL unterstützt einen umfangreichen Satz impliziter Konvertierungen in Ausdrücken. Ähnliche Ausdrücke in C# würden eine explizite Umwandlung erfordern. Beispiel:  
  
-   Der `Nvarchar`-Typ und der `DateTime`-Typ können in SQL ohne explizite Umwandlungen verglichen werden. C# erfordert explizite Konvertierung.  
  
-   `Decimal` wird in SQL implizit in `DateTime` konvertiert. C# ermöglicht keine implizite Konvertierung.  
  
 In gleicher Weise unterscheidet sich die Typreihenfolge in Transact-SQL von derjenigen in C#, da der zu Grunde liegende Typsatz abweicht. In der Tat gibt es keine klare Teilmenge-Obermenge-Beziehung zwischen den Rangfolgenlisten. Beispielsweise führt der Vergleich von `nvarchar` mit `varchar` zur impliziten Konvertierung des `varchar`-Ausdrucks in `nvarchar`. CLR bietet keine äquivalente Heraufstufung.  
  
 In einfachen Fällen führen diese Unterschiede zu CLR-Ausdrücken mit Umwandlungen, die für den entsprechenden SQL-Ausdruck redundant sind. Noch wichtiger ist, dass die direkten Ergebnisse eines SQL-Ausdrucks implizit auf einen Typ heraufgestuft werden können, der kein genaues Gegenstück in C# aufweist (und umgekehrt). Insgesamt führen Tests, Debuggen und Validierung solcher Ausdrücke zu einer erheblichen Belastung für die Benutzer.  
  
### <a name="collation"></a>Sortierreihenfolge  
 Transact-SQL unterstützt explizite Sortierungen als Anmerkungen zu Zeichenfolgentypen. Diese Sortierreihenfolgen bestimmen die Gültigkeit von bestimmten Vergleichen. Zwei Spalten mit anderen expliziten Sortierreihenfolgen zu vergleichen ist z. B. unzulässig. Die Verwendung eines erheblich einfacheren CTS-Zeichenfolgentyps verursacht keine solchen Fehler. Betrachten Sie das folgende Beispiel:  
  
```  
create table T2 (  
    Col1 nvarchar(10),  
    Col2      nvarchar(10) collate Latin_general_ci_as  
)  
```  
  
 [!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
 [!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]  
  
```  
Select …  
From …  
Where Col1 = Col2  
-- Error, collation conflict.  
```  
  
 Die Sortierreihenfolge-Unterklausel aktiviert ist, erstellt eine *beschränkten Typ* , die nicht ersetzbar ist.  
  
 Auf ähnliche Weise kann die Sortierreihenfolge über Typsysteme hinweg deutlich abweichen. Dieser Unterschied wirkt sich auf die Ergebnissortierung aus. <xref:System.Guid> wird über alle 16 Bytes hinweg in lexikografischer Reihenfolge (`IComparable()`), sortiert. T-SQL hingegen vergleicht GUIDs in folgender Reihenfolge: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3). Diese Sortierung wurde in SQL 7.0 erstellt, als von NT erstellte GUIDs eine entsprechende Oktettreihenfolge hatten. Dieser Ansatz stellte sicher, dass auf dem gleichen Node-Cluster erzeugte GUIDs nach Timestamp in sequenzieller Reihenfolge zusammengestellt wurden. Der Ansatz war auch für die Erstellung von Indizes nützlich (inserts werden nicht zu zufälligen E/As, sondern zu appends). Die Reihenfolge wurde aufgrund von Datenschutzaspekten später in Windows durcheinander gebracht, SQL muss jedoch kompatibel bleiben. Dieses Problem zu umgehen ist die Verwendung <xref:System.Data.SqlTypes.SqlGuid> anstelle von <xref:System.Guid>.  
  
### <a name="operator-and-function-differences"></a>Unterschiede zwischen Operatoren und Funktionen  
 Im Wesentlichen vergleichbare Operatoren und Funktionen verfügen über eine leicht andere Semantik. Beispiel:  
  
-   C# gibt auf der Grundlage der lexikalischen Reihenfolge von Operanden für logische Operatoren `&&` und `||` als Kurzschlusssemantik an. SQL wurde andererseits für satzbasierte Abfragen definiert und bietet daher mehr Optimierungsfreiheit hinsichtlich der Ausführungsreihenfolge. Einige der Auswirkungen schließen Folgendes ein:  
  
    -   Semantisch angemessene Übersetzung erfordert "`CASE` ... `WHEN` … `THEN`"erstellen Sie, in SQL, um die neuanordnung der operandenausführung zu vermeiden.  
  
    -   Eine freie Übersetzung in `AND` / `OR` Operatoren können unerwartete Fehler verursachen, wenn die C# Ausdruck basiert auf die Auswertung den zweiten Operand wird basierend auf dem Ergebnis der Auswertung des ersten Operanden.  
  
-   Die `Round()`-Funktion weist in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] und in T-SQL unterschiedliche Semantiken auf.  
  
-   Der Startindex für Zeichenfolgen in CLR ist 0, in SQL jedoch 1. Aus diesem Grund muss jede Funktion mit einem Index übersetzt werden.  
  
-   CLR unterstützt den Modulusoperator ("%") für Gleitkommazahlen, SQL jedoch nicht.  
  
-   Der `Like`-Operator ruft automatische Überladungen auf der Grundlage von impliziten Konvertierungen ab. Obwohl der `Like`-Operator für Zeichenfolgen mit Zeichen definiert ist, ermöglicht die implizite Konvertierung von numerischen Typen oder `DateTime`-Typen die Verwendung dieser abweichenden Typen auch mit `Like`. In CTS sind vergleichbare implizite Konvertierungen nicht vorhanden. Deshalb werden zusätzliche Überladungen benötigt.  
  
    > [!NOTE]
    >  Dieses Verhalten des `Like`-Operators gilt nur für C#, das `Like`-Schlüsselwort in Visual Basic ist unverändert.  
  
-   Überlauf ist in SQL stets geprüft, aber in explizit angegeben werden über C# (nicht in Visual Basic) um Umbrüche zu vermeiden. Gegeben sind die Ganzzahlspalten C1, C2 und C3, wenn C1+C2 in C3 gespeichert wird (Update von T-Satz C3 = C1 + C2).  
  
    ```  
    create table T3 (  
        Col1      integer,  
        Col2      integer  
    )  
    insert into T3 (col1, col2) values (2147483647, 5)  
    -- Valid values: max integer value and 5.  
    select * from T3 where col1 + col2 < 0  
    -- Produces arithmetic overflow error.  
    ```  
  
 [!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
 [!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]  
  
-   SQL führt eine symmetrische arithmetische Rundung aus, während [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] unverzerrte Rundung (Banker's Rounding) verwendet. Weitere Informationen finden Sie im Knowledge Base-Artikel 196652.  
  
-   Standardmäßig wird in SQL die Groß- und Kleinschreibung bei Zeichenfolgenvergleichen für allgemeine Gebietsschemas nicht beachtet. In Visual Basic und C# wird die Groß-/Kleinschreibung beachtet. Z. B. `s == "Food"` (`s = "Food"` in Visual Basic) und `s == "Food"` können unterschiedliche Ergebnisse liefern, wenn `s` ist `food`.  
  
    ```  
    -- Assume default US-English locale (case insensitive).  
    create table T4 (  
        Col1      nvarchar (256)  
    )  
    insert into T4 values (‘Food’)   
    insert into T4 values (‘FOOD’)  
    select * from T4 where Col1 = ‘food’  
    -- Both the rows are returned because of case-insensitive matching.  
    ```  
  
 [!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
 [!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]  
  
-   Operatoren/Funktionen, die in SQL auf Argumente des Typs mit Zeichen fester Länge angewendet werden, weisen eine deutlich andere Semantik auf als die gleichen Operatoren/Funktionen, die auf eine CLR-<xref:System.String?displayProperty=nameWithType> angewendet werden. Dies kann auch als Erweiterung der Problematik fehlender Gegenstücke angesehen werden, die in den Abschnitten zu Typen behandelt wird.  
  
    ```  
    create table T4 (  
        Col1      nchar(4)  
    )  
    Insert into T5(Col1) values ('21');  
    Insert into T5(Col1) values ('1021');  
    Select * from T5 where Col1 like '%1'  
    -- Only the second row with Col1 = '1021' is returned.  
    -- Not the first row!  
    ```  
  
     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]  
  
     Ein ähnliches Problem tritt bei der Zeichenfolgenverkettung auf.  
  
    ```  
    create table T6 (  
        Col1      nchar(4)  
        Col2       nchar(4)  
    )  
    Insert into T6 values ('a', 'b');  
    Select Col1+Col2 from T6  
    -- Returns concatenation of padded strings "a   b   " and not "ab".  
    ```  
  
 Zusammenfassend kann eine Konvolutübersetzung für CLR-Ausdrücke erforderlich sein. Es können auch weitere Operatoren/Funktionen benötigt werden, um SQL-Funktionen zur Verfügung zu stellen.  
  
### <a name="type-casting"></a>Typumwandlung  
 In C# und SQL können Benutzer die Standardsemantik von Ausdrücken überschreiben, indem sie explizite Typen (`Cast` und `Convert`) verwenden. Die Nutzung dieser Möglichkeit über die Grenzen des Typsystems hinweg führt jedoch zu einem Dilemma. Eine SQL-Umwandlung, die die gewünschte Semantik bereitstellt, kann nicht einfach in eine entsprechende C#-Umwandlung übersetzt werden. Andererseits kann eine C#-Umwandlung nicht direkt in eine äquivalente SQL-Umwandlung übersetzt werden, da es zu Typenkonflikten, fehlenden Gegenstücken und unterschiedlichen Typhierarchien kommt. Es gibt einen Kompromiss zwischen der Darstellung des Typsystemkonflikts und dem Verlust eines großen Teils der Ausdrucksfunktionalität.  
  
 In anderen Fällen ist die Typumwandlung möglicherweise nicht in beiden Domänen für die Validierung eines Ausdrucks erforderlich. Sie kann jedoch u. U. notwendig sein, um sicherzustellen, dass ein vom Standard abweichendes Mapping korrekt auf den Ausdruck angewendet wird.  
  
```  
-- Example from "Non-default Mapping" section extended  
create table T5 (  
    Col1      nvarchar(10),  
    Col2      nvarchar(10)  
)  
Insert into T5(col1, col2) values (‘3’, ‘2’);  
```  
  
 [!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
 [!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]  
  
```  
Select *  
From T5  
Where Col1 + Col2 > 4     
-- "Col1 + Col2" expr evaluates to '32'   
```  
  
## <a name="performance-issues"></a>Leistungsaspekte  
 Für einige SQL Server-CLR-Kontoführung können der Unterschiede bei in eine Abnahme der Leistung führen, wenn zwischen der CLR und SQL Server Typsystemen. Im Folgenden finden Sie Beispielszenarien, die sich auf die Leistung auswirken:  
  
-   Erzwungene Reihenfolge der Evaluierung für logische AND/OR-Operatoren  
  
-   Das Generieren von SQL, um durchzusetzen, dass die Reihenfolge der Prädikatevaluierung die Fähigkeit des SQL-Optimierungsprogramms einschränkt.  
  
-   Typkonvertierungen durch einen CLR-Compiler oder durch eine objektrelationale Abfrageimplementierung können zu Problemen bei der Indexverwendung führen.  
  
     Beispiel:  
  
    ```  
    -- Table DDL  
    create table T5 (  
        Col1      varchar(100)  
    )  
    ```  
  
     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]  
  
     Berücksichtigen Sie die Übersetzung des Ausdrucks `(s = SOME_STRING_CONSTANT)`.  
  
    ```  
    -- Corresponding part of SQL where clause  
    Where …  
    Col1 = SOME_STRING_CONSTANT  
    -- This expression is of the form <varchar> = <nvarchar>.  
    -- Hence SQL introduces a conversion from varchar to nvarchar,  
    --     resulting in  
    Where …  
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT  
    -- Cannot use the index for column Col1 for some implementations.  
    ```  
  
 Zusätzlich zu Semantikunterschieden müssen bei Schnittstellen der Typsysteme von SQL Server und CLR Auswirkungen auf die Leistung berücksichtigt werden. Bei großen Datensätzen können solche Leistungsprobleme aufzeigen, ob eine Anwendung zur Bereitstellung geeignet ist.  
  
## <a name="see-also"></a>Siehe auch
- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
