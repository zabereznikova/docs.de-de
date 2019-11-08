---
title: Behandeln von NULL-Werten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
ms.openlocfilehash: 091fde9a6149f72577e0cf38c8ebf1536abdf6ea
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738202"
---
# <a name="handling-null-values"></a>Behandeln von NULL-Werten
Wenn der Wert in einer Spalte unbekannt ist oder fehlt, wird in einer relationalen Datenbank ein NULL-Wert verwendet. NULL ist weder eine leere Zeichenfolge (für Zeichen- oder Datetime-Datentypen) noch ein Wert 0 (null) (für numerische Datentypen). Die ANSI SQL-92-Spezifikation legt fest, dass NULL für alle Datentypen gleich sein muss, sodass alle NULL-Werte einheitlich behandelt werden können. Der <xref:System.Data.SqlTypes>-Namespace stellt durch Implementieren der <xref:System.Data.SqlTypes.INullable>-Schnittstelle eine NULL-Semantik bereit. Jeder Datentyp in <xref:System.Data.SqlTypes> besitzt eine eigene `IsNull`-Eigenschaft und einen `Null`-Wert. Diese können einer Instanz dieses Datentyps zugewiesen werden.  
  
> [!NOTE]
> Neu in .NET Framework 2.0 ist die Unterstützung für Typen, die NULL-Werte zulassen. Programmierer können damit einen Werttyp so erweitern, dass dieser alle Werte des zugrunde liegenden Typs darstellen kann. Die CLR-Typen, die NULL-Werte zulassen, stellen eine Instanz der <xref:System.Nullable>-Struktur dar. Diese Funktion erweist sich vor allem dann als hilfreich, wenn Werttypen geschachtelt und nicht geschachtelt sind, wodurch sich die Kompatibilität mit Objekttypen verbessert. CLR-Typen, die NULL-Werte zulassen, sind nicht zum Speichern von Datenbank-NULL-Werten gedacht, weil sich ein ANSI-SQL-NULL-Wert anders als ein `null`-Verweis (oder `Nothing` in Visual Basic) verhält. Verwenden Sie zum Arbeiten mit ANSI SQL-Datenbank-NULL-Werten statt <xref:System.Data.SqlTypes> lieber <xref:System.Nullable>-NULL-Werte. Weitere Informationen zum Arbeiten mit CLR- C# [Typen, die NULL-Werte zulassen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) [, finden Sie Visual Basic unter.](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)  
  
## <a name="nulls-and-three-valued-logic"></a>NULL-Werte und dreiwertige Logik  
 Wenn in Spaltendefinitionen NULL-Werte zugelassen werden, wird dreiwertige Logik in die Anwendung eingeführt. Eine Vergleichsoperation wird mit einer der drei nachfolgenden Bedingungen ausgewertet:  
  
- True  
  
- False  
  
- Unbekannt  
  
 Da NULL als unbekannt betrachtet wird, gelten zwei miteinander verglichene NULL-Werte nicht als gleich. In Ausdrücken, die arithmetische Operatoren verwenden, ist das Ergebnis NULL, wenn einer der Operanden NULL ist.  
  
## <a name="nulls-and-sqlboolean"></a>NULL-Werte und SqlBoolean  
 Ein Vergleich zwischen beliebigen <xref:System.Data.SqlTypes> gibt einen <xref:System.Data.SqlTypes.SqlBoolean> zurück. Die `IsNull`-Funktion für jeden `SqlType` gibt einen <xref:System.Data.SqlTypes.SqlBoolean>-Wert zurück und kann dazu verwendet werden, das Vorhandensein von NULL-Werten zu überprüfen. Den folgenden Tabellen mit Wahrheitswerten können Sie entnehmen, wie die Operatoren AND, OR und NOT bei Vorhandensein eines NULL-Werts funktionieren. (T=true (wahr), F=false (falsch) und U=unknown (unbekannt) oder NULL.)  
  
 ![Wahrheitstabelle](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")  
  
### <a name="understanding-the-ansi_nulls-option"></a>Informationen zur ANSI_NULLS-Option  
 Mit <xref:System.Data.SqlTypes> wird dieselbe Semantik bereitgestellt wie bei aktivierter ANSI_NULLS-Option in SQL Server. Alle arithmetischen Operatoren (+,-, \*,/,%), bitweise Operatoren (~, &, \|) und die meisten Funktionen geben NULL zurück, wenn einer der Operanden oder Argumente NULL ist, mit Ausnahme der Eigenschaften `IsNull`.  
  
 Der ANSI SQL-92-Standard unterstützt *ColumnName* = NULL in einer WHERE-Klausel nicht. In SQL Server steuert die ANSI_NULLS-Option die Fähigkeit, in der Standardeinstellung NULL-Werte in der Datenbank zuzulassen sowie die Auswertung von Vergleichen mit NULL-Werten. Wenn ANSI_NULLS aktiviert ist (Standardeinstellung), muss der IS NULL-Operator beim Testen auf NULL-Werte in Ausdrücken verwendet werden. Der folgende Vergleich ergibt z. B. immer "Unknown", wenn ANSI_NULLS aktiviert ist:  
  
```sql
colname > NULL  
```  
  
 Der Vergleich mit einer Variablen, die einen NULL-Wert enthält, ergibt auch "Unknown":  
  
```sql
colname > @MyVariable  
```  
  
 Verwenden Sie zum Testen auf einen NULL-Wert das IS NULL-Prädikat oder das IS NOT NULL-Prädikat. Dies kann die Komplexität der WHERE-Klausel erhöhen. Die TerritoryID-Spalte in der AdventureWorks Customer-Tabelle lässt z. B. NULL-Werte zu. Wenn eine SELECT-Anweisung zusätzlich zu anderen Werten auf NULL-Werte getestet werden soll, muss sie ein IS NULL-Prädikat enthalten:  
  
```sql
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 Wenn Sie in SQL Server ANSI_NULLS deaktivieren, können Sie Ausdrücke erstellen, die mithilfe des Gleichheitsoperators einen Vergleich mit NULL durchführen. Sie können jedoch nicht verhindern, dass verschiedene Verbindungen NULL-Optionen für diese Verbindung festlegen. Die Verwendung von IS NULL funktioniert zum Testen auf NULL-Werte immer, unabhängig von den für eine Verbindung festgelegten ANSI_NULLS-Einstellungen.  
  
 Die Deaktivierung von ANSI_NULLS wird in einem `DataSet` nicht unterstützt. Dieses befolgt immer den ANSI SQL-92-Standard für die Behandlung von NULL-Werten in <xref:System.Data.SqlTypes>.  
  
## <a name="assigning-null-values"></a>Zuweisen von NULL-Werten  
 NULL-Werte weisen einige Besonderheiten auf und ihre Speicherung und Zuweisungssemantik ist in verschiedenen Typ- und Speichersystemen unterschiedlich. Ein `Dataset` ist für die Verwendung mit verschiedenen Typ- und Speichersystemen vorgesehen.  
  
 In diesem Abschnitt wird die NULL-Semantik zum Zuweisen von NULL-Werten zu einer <xref:System.Data.DataColumn> in einer <xref:System.Data.DataRow> in den verschiedenen Typsystemen beschrieben.  
  
 `DBNull.Value`  
 Diese Zuweisung ist für eine `DataColumn` eines beliebigen Typs gültig. Wenn der Typ `INullable` implementiert, wird `DBNull.Value` in den entsprechenden stark typisierten NULL-Wert umgewandelt.  
  
 `SqlType.Null`  
 Alle <xref:System.Data.SqlTypes>-Datentypen implementieren `INullable`. Wenn der stark typisierte NULL-Wert mit impliziten Umwandlungsoperatoren in den Datentyp der Spalte umgewandelt werden kann, sollte die Zuweisung durchgeführt werden können. Andernfalls wird eine Ausnahme für eine ungültige Umwandlung ausgelöst.  
  
 `null`  
 Wenn 'NULL' ein zulässiger Wert für den angegebenen `DataColumn`-Datentyp ist, wird er in den entsprechenden `DbNull.Value` oder `Null` umgewandelt, der dem `INullable`-Typ (`SqlType.Null`) zugeordnet ist.  
  
 `derivedUdt.Null`  
 Bei UDT-Spalten werden NULL-Werte immer auf der Grundlage des Typs gespeichert, der der `DataColumn` zugeordnet ist. Nehmen wir einen UDT, der einer `DataColumn` zugeordnet ist und der `INullable` im Gegensatz zu seiner Unterklasse nicht implementiert. In diesem Fall wird er als nicht typisierter `DbNull.Value` gespeichert, wenn ein stark typisierter NULL-Wert zugewiesen wird, der der abgeleiteten Klasse zugeordnet ist, da die Speicherung von NULL-Werten immer mit dem Datentyp der DataColumn konsistent ist.  
  
> [!NOTE]
> Die `Nullable<T>`-Struktur und die <xref:System.Nullable>-Struktur werden im `DataSet` derzeit nicht unterstützt.  
  
### <a name="multiple-column-row-assignment"></a>Zuweisung mehrerer Spalten (Zeilen)  
 `DataTable.Add`, `DataTable.LoadDataRow` oder andere APIs, die ein <xref:System.Data.DataRow.ItemArray%2A> akzeptieren, das einer Reihe zugeordnet wird, ordnen dem Standardwert der &lt;legacyBold&gt;DataColumn&lt;/legacyBold&gt; 'NULL' zu. Wenn ein Objekt im Array `DbNull.Value` oder dessen stark typisierte Entsprechung enthält, gelten dieselben Regeln wie oben beschrieben.  
  
 Darüber hinaus gelten für Instanzen von `DataRow.["columnName"]`-NULL-Zuweisungen die folgenden Regeln:  
  
1. Der Standard *mäßige Standardwert ist* `DbNull.Value` für alle außer den stark typisierten NULL-Spalten, bei denen es sich um den entsprechenden stark typisierten NULL-Wert handelt.  
  
2. NULL-Werte werden bei der Serialisierung in XML-Dateien (wie in "xsi:nil") nie ausgegeben.  
  
3. Alle Nicht-NULL-Werte einschließlich der Standardwerte werden bei der Serialisierung nach XML immer ausgegeben. Dies entspricht nicht der XSD/XML-Semantik, bei der ein NULL-Wert (xsi:nil) explizit und der Standardwert implizit ist (wenn nicht in XML vorhanden, kann der Wert von einem validierenden Parser aus einem zugeordneten XSD-Schema abgerufen werden). Das Gegenteil gilt für eine `DataTable`: Ein NULL-Wert ist implizit, und der Standardwert ist explizit.  
  
4. Allen fehlenden Spaltenwerten für Zeilen, die aus der XML-Eingabe gelesen werden, wird NULL zugewiesen. Zeilen, die mithilfe von <xref:System.Data.DataTable.NewRow%2A> oder ähnlichen Methoden erstellt wurden, wird der Standardwert von DataColumn zugewiesen.  
  
5. Die <xref:System.Data.DataRow.IsNull%2A>-Methode gibt sowohl für `true` als auch für `DbNull.Value``INullable.Null` zurück.  
  
## <a name="assigning-null-values"></a>Zuweisen von NULL-Werten  
 Der Standardwert für alle <xref:System.Data.SqlTypes>-Instanzen ist NULL.  
  
 NULL-Werte in <xref:System.Data.SqlTypes> sind typspezifisch und können nicht von einem einzelnen Wert (z. B. `DbNull`) dargestellt werden. Mit der `IsNull`-Eigenschaft können Sie überprüfen, ob NULL-Werte vorliegen.  
  
 NULL-Werte können einer <xref:System.Data.DataColumn> wie im folgenden Codebeispiel dargestellt zugewiesen werden. Sie können `SqlTypes`-Variablen direkt NULL-Werte zuweisen, ohne eine Ausnahme auszulösen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine <xref:System.Data.DataTable> mit zwei Spalten erstellt, die als <xref:System.Data.SqlTypes.SqlInt32> und <xref:System.Data.SqlTypes.SqlString> definiert werden. Der Code fügt eine Zeile mit bekannten Werten und eine Zeile mit NULL-Werten hinzu und durchläuft dann die <xref:System.Data.DataTable>. Dabei werden den Variablen die Werte zugewiesen und die Ausgabe im Konsolenfenster angezeigt.  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 In diesem Beispiel werden die folgenden Ergebnisse angezeigt:  
  
```output
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a>Vergleichen von NULL-Werten mit "SqlTypes" und CLR-Typen  
 Beim Vergleichen von NULL-Werten ist es wichtig zu verstehen, wie die `Equals`-Methode NULL-Werte in <xref:System.Data.SqlTypes> auswertet und wie sie im Unterschied dazu bei CLR-Typen vorgeht. Alle <xref:System.Data.SqlTypes>`Equals`-Methoden verwenden für die Auswertung von NULL-Werten die Datenbanksemantik: Wenn mindestens einer der Werte NULL ist, ergibt der Vergleich NULL. Andererseits ergibt die Anwendung der CLR-`Equals`-Methode auf zwei <xref:System.Data.SqlTypes> &lt;legacyBold&gt;true&lt;/legacyBold&gt;, wenn beide NULL sind. Dies spiegelt den Unterschied zwischen der Verwendung einer Instanzmethode wie der CLR-`String.Equals`-Methode und der Verwendung der &lt;legacyBold&gt;static&lt;/legacyBold&gt;/&lt;legacyBold&gt;shared&lt;/legacyBold&gt;-Methode `SqlString.Equals` wider.  
  
 Das folgende Beispiel zeigt den Unterschied in den Ergebnissen zwischen der `SqlString.Equals`-Methode und der `String.Equals`-Methode, wenn beiden Methoden ein Paar von NULL-Werten und dann ein Paar leerer Zeichenfolgen übergeben wird.  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 Der Code erzeugt die folgende Ausgabe:  
  
```output
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True   
```  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](sql-server-data-types.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
