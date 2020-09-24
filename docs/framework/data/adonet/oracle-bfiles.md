---
title: Oracle-BFILEs
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: d43dfccd9735ce1ab822d7b14de2abaa0940c77b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166598"
---
# <a name="oracle-bfiles"></a>Oracle-BFILEs

Der .NET Framework-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die für das Arbeiten mit dem Oracle-<xref:System.Data.OracleClient.OracleType.BFile>-Datentyp verwendet wird.  
  
 Der Oracle **BFILE** -Datentyp ist ein Oracle- **LOB** -Datentyp, der einen Verweis auf Binärdaten mit einer maximalen Größe von 4 Gigabyte enthält. Eine Oracle **BFILE** unterscheidet sich von anderen Oracle- **LOB** -Datentypen darin, dass die Daten in einer physischen Datei im Betriebssystem und nicht auf dem Server gespeichert werden. Beachten Sie, dass der **BFILE** -Datentyp schreibgeschützten Zugriff auf Daten bereitstellt.  
  
 Andere Merkmale eines **BFILE** -Datentyps, die ihn von einem **LOB** -Datentyp unterscheiden, sind folgende:  
  
- Er enthält unstrukturierte Daten.  
  
- Er unterstützt das serverseitige Aufteilen in kleine Blöcke.  
  
- Er verwendet die Semantik zum Kopieren von Verweisen. Wenn Sie z. b. einen Kopiervorgang für eine **BFILE**ausführen, wird nur der **BFILE** -Serverlocatorpunkt (ein Verweis auf die Datei) kopiert. Die Daten in der Datei werden nicht kopiert.  
  
 Der **BFILE** -Datentyp sollte verwendet werden, um auf Lob zu verweisen, die groß sind und daher nicht in der Datenbank gespeichert werden können. Bei Verwendung eines **BFILE** -Datentyps im Vergleich zum **LOB** -Datentyp ist mehr Client-, Server-und Kommunikationsaufwand betroffen. Es ist effizienter, auf eine **BFILE** zuzugreifen, wenn Sie nur eine kleine Datenmenge abrufen müssen. Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.  
  
 Jedes **OracleBFile** -Objekt, das nicht NULL ist, ist zwei Entitäten zugeordnet, die den Speicherort der zugrunde liegenden physischen Datei definieren:  
  
1. Ein Oracle-DIRECTORY-Objekt, das als Datenbank-Alias für ein Verzeichnis im Dateisystem fungiert.  
  
2. Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY-Objekt zugeordneten Verzeichnis befindet.  
  
## <a name="example"></a>Beispiel  

 Im folgenden c#-Beispiel wird veranschaulicht, wie Sie eine **BFILE** in einer Oracle-Tabelle erstellen und dann in Form eines **OracleBFile** -Objekts abrufen können. Das Beispiel veranschaulicht die Verwendung des <xref:System.Data.OracleClient.OracleDataReader> -Objekts und der **OracleBFile** -Methode zum **Suchen** und **Lesen** . Beachten Sie Folgendes: um dieses Beispiel zu verwenden, müssen Sie zuerst ein Verzeichnis mit dem Namen "c: \\ \bfiles" und eine Datei mit dem Namen "MyFile.jpg" auf dem Oracle-Server erstellen.  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
