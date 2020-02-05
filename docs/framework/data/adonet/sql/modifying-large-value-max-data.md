---
title: Ändern von Daten mit umfangreichen Werten (max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: cb37fdb85d323d4f0816a3667a4624da8ec75e65
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979845"
---
# <a name="modifying-large-value-max-data-in-adonet"></a>Ändern von Daten mit umfangreichen Werten (max) in ADO.NET
Bei LOB-Datentypen übersteigt die Zeilengröße die maximal zulässige Zeilengröße von 8 KB. SQL Server umfasst einen `max`-Spezifizierer für die Datentypen `varchar`, `nvarchar` und `varbinary`, der das Speichern Werten mit einer Größe bis zu 2^32 Bytes ermöglicht. Tabellenspalten und Transact-SQL-Variablen können die Datentypen `varchar(max)`, `nvarchar(max)` oder `varbinary(max)` angeben. In ADO.NET können die `max`-Datentypen durch einen `DataReader` abgerufen werden. Außerdem können sie ohne spezielle Behandlung sowohl als Eingabe- als auch als Ausgabeparameterwerte angegeben werden. Bei großen `varchar`-Datentypen können Daten inkrementell abgerufen und aktualisiert werden.  
  
 Die `max`-Datentypen können für Vergleiche, als Transact-SQL-Variablen und zum Verketten verwendet werden. Auch der Einsatz in den Klauseln DISTINCT, ORDER BY und GROUP BY einer SELECT-Anweisung sowie in Aggregaten, Joins und Unterabfragen ist möglich.  
  
 Die folgende Tabelle enthält Links zur Dokumentation in der SQL Server-Onlinedokumentation.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1. [Verwenden von Datentypen mit umfangreichen Werten](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a>Einschränkungen für große Werttypen  
 Für die `max`-Datentypen gelten die folgenden Einschränkungen, die für kleinere Datentypen nicht vorhanden sind:  
  
- Ein `sql_variant` kann keinen großen `varchar`-Datentyp enthalten.  
  
- Große `varchar`-Spalten können nicht als Schlüsselspalte in einem Index angegeben werden. In einer eingeschlossenen Spalte in einem nicht gruppierten Index sind sie jedoch zulässig.  
  
- Große `varchar`-Spalten können nicht zum Partitionieren von Schlüsselspalten verwendet werden.  
  
## <a name="working-with-large-value-types-in-transact-sql"></a>Arbeiten mit großen Werttypen in Transact-SQL  
 Die Transact-SQL-`OPENROWSET`-Funktion ist eine für den Einmalgebrauch bestimmte Methode zum Herstellen einer Verbindung mit Remotedaten und den Zugriff auf diese Daten. Sie enthält alle erforderlichen Verbindungsinformationen für den Zugriff auf Remotedaten von einer OLE DB-Datenquelle. Auf `OPENROWSET` kann in der FROM-Klausel einer Abfrage so verwiesen werden, als ob es ein Tabellenname wäre. Abhängig von den Funktionen des OLE DB-Anbieters kann OPENROWSET auch als Zieltabelle einer INSERT-, UPDATE- oder DELETE-Anweisung dienen.  
  
 Die `OPENROWSET`-Funktion umfasst den `BULK`-Rowsetanbieter, mit dem Sie Daten direkt aus einer Datei lesen können, ohne sie in eine Zieltabelle zu laden. Auf diese Weise können Sie `OPENROWSET` in einer einfachen INSERT SELECT-Anweisung verwenden.  
  
 Die Argumente für die `OPENROWSET BULK` Option bieten eine bedeutende Kontrolle darüber, wo das Lesen von Daten begonnen und beendet werden soll, wie mit Fehlern umzugehen ist und wie Daten interpretiert werden. So können Sie z. B. angeben, dass die Datendatei als Rowset mit einer einzelnen Zeile und einer einzelnen Spalte vom Typ `varbinary`, `varchar` oder `nvarchar` gelesen werden soll. Die vollständige Syntax und alle Optionen finden Sie in der SQL Server-Onlinedokumentation.  
  
 Im folgenden Beispiel wird ein Foto in die ProductPhoto-Tabelle der AdventureWorks-Beispieldatenbank eingefügt. Wenn Sie den `BULK OPENROWSET`-Anbieter verwenden, müssen Sie die benannte Liste der Spalten angeben, auch wenn Sie keine Werte in jede Spalte einfügen. Der Primärschlüssel ist in diesem Fall als Identitätsspalte definiert und kann in der Liste der Spalten weggelassen werden. Beachten Sie, dass Sie am Ende der `OPENROWSET`-Anweisung auch einen Korrelationsnamen angeben müssen. In diesem Fall lautet er "ThumbnailPhoto". Dies korreliert mit der Spalte in der `ProductPhoto`-Tabelle, in die die Datei geladen wird.  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a>Aktualisieren von Daten mithilfe von UPDATE .WRITE  
 Die Transact-SQL-Anweisung UPDATE weist eine neue WRITE-Syntax zum Ändern des Inhalts in den Spalten `varchar(max)`, `nvarchar(max)` oder `varbinary(max)` auf. Dies ermöglicht es Ihnen, teilweise Updates der Daten durchzuführen. Die UPDATE .WRITE-Syntax wird hier in gekürzter Form dargestellt:  
  
 AKTUALISIEREN  
  
 { *\<Objekt >* }  
  
 SET  
  
 { *column_name* = {. Write ( *Ausdruck* , @Offset @Length)}  
  
 Die Write-Methode gibt an, dass ein Abschnitt des Werts des *column_name* geändert wird. Der Ausdruck ist der Wert, der in den *column_name*kopiert wird, der `@Offset` ist der Anfangspunkt, an dem der Ausdruck geschrieben wird, und das `@Length`-Argument ist die Länge des Abschnitts in der Spalte.  
  
|Wenn virtuelle Maschinen mit|Then|  
|--------|----------|  
|Der Ausdruck ist auf NULL festgelegt.|`@Length` wird ignoriert, und der Wert in *column_name* wird am angegebenen `@Offset`abgeschnitten.|  
|`@Offset` ist NULL|Der Aktualisierungs Vorgang fügt den Ausdruck am Ende des vorhandenen *column_name* Werts an, und `@Length` wird ignoriert.|  
|`@Offset` ist größer als die Länge des &lt;legacyItalic&gt;column_name&lt;/legacyItalic&gt;-Werts|SQL Server gibt einen Fehler zurück.|  
|`@Length` ist NULL|Beim Updatevorgang werden alle Daten ab `@Offset` bis zum Ende des `column_name`-Werts entfernt.|  
  
> [!NOTE]
> Weder `@Offset` noch `@Length` darf eine negative Zahl sein.  
  
## <a name="example"></a>Beispiel  
 In diesem Transact-SQL-Beispiel wird ein Teil eines Werts in &lt;legacyBold&gt;DocumentSummary&lt;/legacyBold&gt; aktualisiert. Dabei handelt es sich um eine `nvarchar(max)`-Spalte in der &lt;legacyBold&gt;Document&lt;/legacyBold&gt;-Tabelle in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank. Das Wort "components" wird ersetzt durch "features". Dazu wird das Ersatzwort, die Anfangsposition (Offset) des zu ersetzenden Worts in den vorhandenen Daten und die Anzahl der zu ersetzenden Zeichen (Length) angegeben. Das Beispiel enthält SELECT-Anweisungen vor und nach der UPDATE-Anweisung, damit die Ergebnisse verglichen werden können.  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO   
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a>Arbeiten mit großen Werttypen in ADO.NET  
 Sie können mit großen Werttypen in ADO.NET arbeiten, indem Sie große Werttypen als <xref:System.Data.SqlClient.SqlParameter> Objekte in einem <xref:System.Data.SqlClient.SqlDataReader> angeben, um ein Resultset zurückzugeben, oder indem Sie einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Ausfüllen eines `DataSet`/`DataTable`verwenden. Sie können mit großen Datentypen genauso arbeiten wie mit den entsprechenden kleineren Datentypen.  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a>Abrufen von Daten mit "GetSqlBytes"  
 Mit der `GetSqlBytes`-Methode von <xref:System.Data.SqlClient.SqlDataReader> können Sie den Inhalt einer `varbinary(max)`-Spalte abrufen. Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt mit dem Namen `cmd` ausgegangen, das `varbinary(max)`-Daten aus einer Tabelle auswählt. Außerdem gibt es ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader`, das die Daten als <xref:System.Data.SqlTypes.SqlBytes> abruft.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a>Abrufen von Daten mit "GetSqlChars"  
 Mit der `GetSqlChars`-Methode von <xref:System.Data.SqlClient.SqlDataReader> können Sie den Inhalt einer `varchar(max)`-Spalte oder einer `nvarchar(max)`-Spalte abrufen. Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt mit dem Namen `cmd` ausgegangen, das `nvarchar(max)`-Daten aus einer Tabelle auswählt. Außerdem gibt es ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader`, das die Daten abruft.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a>Abrufen von Daten mit "GetSqlBinary"  
 Mit der `GetSqlBinary`-Methode eines <xref:System.Data.SqlClient.SqlDataReader> können Sie den Inhalt einer `varbinary(max)`-Spalte abrufen. Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt mit dem Namen `cmd` ausgegangen, das `varbinary(max)`-Daten aus einer Tabelle auswählt. Außerdem gibt es ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader`, das die Daten als <xref:System.Data.SqlTypes.SqlBinary>-Stream abruft.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a>Abrufen von Daten mit "GetBytes"  
 Die `GetBytes`-Methode eines <xref:System.Data.SqlClient.SqlDataReader> liest einen Bytestream, beginnend am angegebenen Spaltenoffset, in ein Bytearray, beginnend am angegebenen Arrayoffset. Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader` ausgegangen, das Bytes in ein Bytearray abruft. Beachten Sie, dass `GetSqlBytes` im Unterschied zu `GetBytes` eine Größe für den Arraypuffer benötigt.  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a>Abrufen von Daten mit "GetValue"  
 Die `GetValue`-Methode eines <xref:System.Data.SqlClient.SqlDataReader> liest den Wert, beginnend am angegebenen Spaltenoffset, in ein Array. Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader` ausgegangen, das zuerst binäre Daten abruft und damit am ersten Spaltenoffset beginnt. Anschließend werden Zeichenfolgendaten abgerufen, wobei am zweiten Spaltenoffset begonnen wird.  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a>Konvertieren von großen Werttypen in CLR-Typen  
 Sie können den Inhalt einer `varchar(max)`-Spalte oder einer `nvarchar(max)`-Spalte mit einer beliebigen Methode zur Zeichenfolgenkonvertierung konvertieren, z. B. mit `ToString`. Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader` ausgegangen, das die Daten abruft.  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a>Beispiel  
 Der folgende Code ruft den Namen und das `LargePhoto`-Objekt aus der `ProductPhoto`-Tabelle in der `AdventureWorks`-Datenbank ab und speichert das Objekt in einer Datei. Die Assembly muss mit einem Verweis auf den <xref:System.Drawing>-Namespace kompiliert werden.  Die <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gibt ein <xref:System.Data.SqlTypes.SqlBytes>-Objekt zurück, das eine `Stream`-Eigenschaft verfügbar macht. Der Code verwendet diese, um ein neues `Bitmap` Objekt zu erstellen, und speichert es dann in der GIF-`ImageFormat`.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a>Verwenden großer Werttypparameter  
 Große Werttypen können in <xref:System.Data.SqlClient.SqlParameter>-Objekten auf dieselbe Weise verwendet werden wie kleinere Werttypen in <xref:System.Data.SqlClient.SqlParameter>-Objekten. Sie können große Werttypen als <xref:System.Data.SqlClient.SqlParameter> Werte abrufen, wie im folgenden Beispiel gezeigt. Im Code wird davon ausgegangen, dass in der AdventureWorks-Beispieldatenbank die folgende gespeicherte GetDocumentSummary-Prozedur vorhanden ist. Die gespeicherte Prozedur nimmt einen Eingabeparameter mit dem Namen @DocumentID und gibt den Inhalt der DocumentSummary-Spalte im @DocumentSummary Output-Parameter zurück.  
  
```sql
CREATE PROCEDURE GetDocumentSummary   
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a>Beispiel  
 Der ADO.NET-Code erstellt ein <xref:System.Data.SqlClient.SqlConnection>-Objekt und ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, um die gespeicherte GetDocumentSummary-Prozedur auszuführen und die Dokumentübersicht abzurufen, die als großer Werttyp gespeichert ist. Der Code übergibt einen Wert für den @DocumentID Eingabeparameter und zeigt die Ergebnisse an, die im @DocumentSummary Output-Parameter im Konsolenfenster zurückgegeben wurden.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](sql-server-binary-and-large-value-data.md)
- [SQL Server-Datentypzuordnungen](../sql-server-data-type-mappings.md)
- [SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)](sql-server-data-operations.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
