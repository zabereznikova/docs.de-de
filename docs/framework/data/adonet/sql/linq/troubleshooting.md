---
title: Problembehandlung
ms.date: 03/30/2017
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
ms.openlocfilehash: 0ac71d9a55e92161f24deb490b8df6148bfc840c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202187"
---
# <a name="troubleshooting"></a>Problembehandlung

Die folgenden Informationen beziehen sich auf Probleme, die in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen auftreten können, und enthalten Vorschläge dazu, wie diese Probleme vermieden bzw. deren Auswirkungen auf andere Weise verringert werden können.  
  
 In den [häufig gestellten Fragen](frequently-asked-questions.md)werden weitere Probleme behandelt.  
  
## <a name="unsupported-standard-query-operators"></a>Nicht unterstützte Standardabfrageoperatoren  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt nicht alle Standardabfrageoperator-Methoden (z. B. <xref:System.Linq.Enumerable.ElementAt%2A>). Folglich können Projekte, die kompiliert werden, immer noch Laufzeitfehler verursachen. Weitere Informationen finden Sie unter [Übersetzung von Standard Abfrage Operatoren](standard-query-operator-translation.md).  
  
## <a name="memory-issues"></a>Arbeitsspeicherprobleme  

 Wenn eine Abfrage eine Auflistung im Arbeitsspeicher und enthält [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> , wird die Abfrage möglicherweise im Arbeitsspeicher ausgeführt, abhängig von der Reihenfolge, in der die beiden Auflistungen angegeben sind. Wenn die Abfrage im Arbeitsspeicher ausgeführt werden muss, müssen die Daten aus der Datenbanktabelle abgerufen werden.  
  
 Dieser Ansatz ist ineffizient und könnte zu einem erheblichen Anstieg der Arbeitsspeicher- und Prozessornutzung führen. Versuchen Sie, derartige Abfragen über mehrere Domänen zu vermeiden.  
  
## <a name="file-names-and-sqlmetal"></a>Dateinamen und SQLMetal  

 Um einen Namen für eine Eingabedatei anzugeben, fügen Sie den Namen der Befehlszeile als Eingabedatei hinzu. Die Angabe des Dateinamens in der Verbindungszeichenfolge (mithilfe der Option **/conn** ) wird nicht unterstützt. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="class-library-projects"></a>Klassenbibliotheksprojekte  

 Das objektrelationaler Designer erstellt eine Verbindungs Zeichenfolge in der `app.config` Datei des Projekts. In Klassenbibliotheksprojekten wird die Datei `app.config` nicht verwendet. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet die in den Entwurfszeitdateien bereitgestellte Verbindungszeichenfolge. Wenn Sie den Wert in `app.config` ändern, wird die Datenbank, mit der die Anwendung eine Verbindung herstellt, nicht geändert.  
  
## <a name="cascade-delete"></a>Kaskadierendes Delete  

 Kaskadierte Löschvorgänge werden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt bzw. erkannt. Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, führen Sie eines der folgenden Verfahren aus:  
  
- Legen Sie die `ON DELETE CASCADE`-Regel in der Fremdschlüsseleinschränkung in der Datenbank fest.  
  
- Verwenden Sie eigenen Code, um zunächst die untergeordneten Objekte zu löschen, die das Löschen des übergeordneten Objekts verhindern.  
  
 Andernfalls wird eine <xref:System.Data.SqlClient.SqlException>-Ausnahme ausgelöst.  
  
 Weitere Informationen finden Sie unter Vorgehens [Weise: Löschen von Zeilen aus der Datenbank](how-to-delete-rows-from-the-database.md).  
  
## <a name="expression-not-queryable"></a>Ausdruck kann nicht abgefragt werden  

 Falls der Fehler "Der Ausdruck [Ausdruck] kann nicht abgefragt werden. Möglicherweise fehlt ein Assemblyverweis" auftritt, stellen Sie Folgendes sicher:  
  
- Ihre Anwendung zielt auf .NET Compact Framework 3,5 ab.  
  
- Sie müssen über einen Verweis auf `System.Core.dll` und `System.Data.Linq.dll` verfügen.  
  
- Sie verfügen über eine `Imports` -Direktive (Visual Basic) oder eine `using` -Direktive (c#) für <xref:System.Linq> und <xref:System.Data.Linq> .  
  
## <a name="duplicatekeyexception"></a>DuplicateKeyException  

 Während des Debuggens eines [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekts können Sie die Beziehungen einer Entität durchlaufen. Auf diese Weise werden diese Elemente in den Cache umgewandelt, und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Anwesenheit wird Ihnen bewusst. Wenn Sie dann versuchen, <xref:System.Data.Linq.Table%601.Attach%2A> oder <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> bzw. eine ähnliche Methode auszuführen, durch die mehrere Zeilen mit demselben Schlüssel generiert werden, wird eine <xref:System.Data.Linq.DuplicateKeyException> ausgelöst.  
  
## <a name="string-concatenation-exceptions"></a>Ausnahmen bei der Zeichenfolgenverkettung  

 Die Verkettung von Operanden, die `[n]text` zugeordnet sind, und anderen, die `[n][var]char` zugeordnet sind, wird nicht unterstützt. Bei der Verkettung von Zeichenfolgen, die zwei verschiedenen Typsätzen zugeordnet sind, wird eine Ausnahme ausgelöst. Weitere Informationen finden Sie unter [System. String-Methoden](system-string-methods.md).  
  
## <a name="skip-and-take-exceptions-in-sql-server-2000"></a>Überspringen und Behandeln von Ausnahmen in SQL Server 2000  

 Bei Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> oder <xref:System.Linq.Queryable.Take%2A> für eine SQL Server 2000-Datenbank müssen Identitätsmember (<xref:System.Linq.Queryable.Skip%2A>) verwendet werden. Die Abfrage muss gegen eine einzelne Tabelle (keinen Join) ausgeführt werden oder einen der Vorgänge <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> oder <xref:System.Linq.Queryable.Union%2A> darstellen und darf keinen <xref:System.Linq.Queryable.Concat%2A>-Vorgang beinhalten. Weitere Informationen finden Sie im Abschnitt "SQL Server 2000-Unterstützung" in der [Standard Abfrage Operator-Übersetzung](standard-query-operator-translation.md).  
  
 Diese Anforderung gilt nicht für SQL Server 2005.  
  
## <a name="groupby-invalidoperationexception"></a>GroupBy InvalidOperationException  

 Diese Ausnahme wird ausgelöst, wenn ein Spaltenwert in einer <xref:System.Linq.Enumerable.GroupBy%2A>-Abfrage, die eine Gruppierung nach einem `boolean`-Ausdruck ausführt, z. B. `group x by (Phone==@phone)`, NULL ist. Da der Ausdruck eine ist `boolean` , wird der Schlüssel als abgeleitet, `boolean` nicht als `nullable` `boolean` . Wenn der übersetzte Vergleich Null ergibt, wird versucht, eine einer zuzuweisen `nullable` `boolean` `boolean` , und die Ausnahme wird ausgelöst.  
  
 Um diese Situation zu vermeiden (vorausgesetzt, NULL soll als false behandelt werden), verwenden Sie eine Lösung wie die folgende:  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## <a name="oncreated-partial-method"></a>OnCreated() (Partielle Methode)  

 Die generierte `OnCreated()`-Methode wird jedes Mal aufgerufen, sobald der Objektkonstruktor aufgerufen wird, beispielsweise auch dann, wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] den Konstruktor aufruft, um eine Kopie für ursprüngliche Werte zu erstellen. Sie sollten dieses Verhalten berücksichtigen, wenn Sie die `OnCreated()`-Methode in einer eigenen partiellen Klasse implementieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugunterstützung](debugging-support.md)
- [Häufig gestellte Fragen](frequently-asked-questions.md)
