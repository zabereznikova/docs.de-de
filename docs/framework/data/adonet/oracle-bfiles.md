---
title: Oracle-BFILEs
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 825cb9eb4bdb54509c8ca3c20db4dade8b3ece73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677237"
---
# <a name="oracle-bfiles"></a>Oracle-BFILEs
Der .NET Framework-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die für das Arbeiten mit dem Oracle-<xref:System.Data.OracleClient.OracleType.BFile>-Datentyp verwendet wird.  
  
 Die Oracle **BFILE** -Datentyp ist ein Oracle **LOB** -Datentyp, der einen Verweis auf binäre Daten mit einer maximalen Größe von 4 Gigabyte enthält. Ein Oracle **BFILE** unterscheidet sich von anderen Oracle- **LOB** -Datentypen darin, dass ihre Daten in einer physischen Datei im Betriebssystem statt auf dem Server gespeichert ist. Beachten Sie, dass die **BFILE** Datentyp bietet schreibgeschützten Zugriff auf Daten.  
  
 Andere Eigenschaften des eine **BFILE** -Datentyp, der Unterscheidung von einer **LOB** -Datentyp sind, dass die It:  
  
-   Er enthält unstrukturierte Daten.  
  
-   Er unterstützt das serverseitige Aufteilen in kleine Blöcke.  
  
-   Er verwendet die Semantik zum Kopieren von Verweisen. Angenommen, Sie für einen Kopiervorgang Ausführen einer **BFILE**, wird nur die **BFILE** Locator (Dies ist ein Verweis auf die Datei ist) wird kopiert. Die Daten in der Datei werden nicht kopiert.  
  
 Die **BFILE** Datentyp sollte verwendet werden, zum Verweisen auf LOBs, die in der Größe groß sind und daher nicht praktikabel ist, in der Datenbank gespeichert. Mehr Aufwand für Clients, Servern und Kommunikation beteiligt ist, bei Verwendung einer **BFILE** Datentyp im Vergleich mit der **LOB** -Datentyp. Es ist jedoch effizienter, den Zugriff auf eine **BFILE** Wenn Sie nur eine kleine Menge Daten zu erhalten müssen. Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.  
  
 Jedem von NULL **OracleBFile** Objekt bezieht sich auf zwei Entitäten, die den Speicherort der zugrunde liegenden physischen Datei definieren:  
  
1.  Ein Oracle-DIRECTORY-Objekt, das als Datenbank-Alias für ein Verzeichnis im Dateisystem fungiert.  
  
2.  Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY-Objekt zugeordneten Verzeichnis befindet.  
  
## <a name="example"></a>Beispiel  
 Im folgende C#-Beispiel wird veranschaulicht, wie Sie erstellen eine **BFILE** in einer Oracle-Tabelle, und rufen Sie ihn in der Form einer **OracleBFile** Objekt. Das Beispiel veranschaulicht die Verwendung der <xref:System.Data.OracleClient.OracleDataReader> Objekt und die **OracleBFile** **Seek** und **lesen** Methoden. Beachten Sie, um die Verwendung dieses Beispiels Sie zunächst ein Verzeichnis namens erstellen müssen "c:\\\bfiles" und die Datei "MyFile.jpg" auf dem Oracle-Server.  
  
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
  
## <a name="see-also"></a>Siehe auch
- [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
