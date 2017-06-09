---
title: "Oracle-BFILEs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Oracle-BFILEs
Der .NET Framework\-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>\-Klasse, die für das Arbeiten mit dem Oracle\-<xref:System.Data.OracleClient.OracleType>\-Datentyp verwendet wird.  
  
 Der Oracle\-**BFILE**\-Datentyp ist ein Oracle\-**LOB**\-Datentyp, der einen Verweis auf Binärdaten mit einer maximalen Größe von 4 Gigabyte enthält.  Eine Oracle\-**BFILE** unterscheidet sich von anderen Oracle\-**LOB**\-Datentypen darin, dass ihre Daten in einer physischen Datei im Betriebssystem statt auf dem Server gespeichert sind.  Beachten Sie, dass der **BFILE**\-Datentyp nur den Lesezugriff auf Daten ermöglicht.  
  
 Es folgen weitere Eigenschaften, die einen **BFILE**\-Datentyp von einem **LOB**\-Datentyp unterscheiden:  
  
-   Er enthält unstrukturierte Daten.  
  
-   Er unterstützt das serverseitige Aufteilen in kleine Blöcke.  
  
-   Er verwendet die Semantik zum Kopieren von Verweisen.  Wenn Sie z. B. einen Kopiervorgang für eine **BFILE** ausführen, wird nur der **BFILE**\-Locator \(dies ist der Verweis auf die Datei\) kopiert.  Die Daten in der Datei werden nicht kopiert.  
  
 Der **BFILE**\-Datentyp sollte zum Verweisen auf LOBs verwendet werden, die umfangreich und deshalb nicht unbedingt zum Speichern in der Datenbank geeignet sind.  Für das Verwenden eines **BFILE**\-Datentyps ist im Vergleich zum **LOB**\-Datentyp ein Mehraufwand an Client\-, Server\- und Kommunikationskapazitäten erforderlich.  Es ist effektiver, auf eine **BFILE** zuzugreifen, wenn nur eine kleine Menge Daten abgerufen werden muss.  Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.  
  
 Jedem von NULL verschiedenen **OracleBFile**\-Objekt werden zwei Entitäten zugeordnet, die den Speicherort der zugrunde liegenden physischen Datei definieren:  
  
1.  Ein Oracle\-DIRECTORY\-Objekt, das als Datenbank\-Alias für ein Verzeichnis im Dateisystem fungiert.  
  
2.  Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY\-Objekt zugeordneten Verzeichnis befindet.  
  
## Beispiel  
 Im folgenden C\#\-Beispiel wird veranschaulicht, wie eine **BFILE** in einer Oracle\-Tabelle erstellt und anschließend in Form eines **OracleBFile**\-Objekts abgerufen wird.  In dem Beispiel wird die Verwendung des <xref:System.Data.OracleClient.OracleDataReader>\-Objekts und der **OracleBFile**\-**Seek**\-Methode und der **Read**\-Methode veranschaulicht.  Beachten Sie, dass Sie, bevor Sie das Beispiel verwenden können, erst das Verzeichnis "c:\\\\bfiles" und die Datei "MyFile.jpg" auf dem Oracle\-Server erstellen müssen.  
  
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
  
## Siehe auch  
 [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)