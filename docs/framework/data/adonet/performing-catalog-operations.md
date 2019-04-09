---
title: Ausführen von Katalogoperationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: beb5d2db898df1c98662d53190ac1432acc746e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141452"
---
# <a name="performing-catalog-operations"></a>Ausführen von Katalogoperationen
Erstellen Sie zum Ausführen eines Befehls zum Ändern einer Datenbank oder der Katalog, z. B. der CREATE TABLE- oder CREATE PROCEDURE-Anweisung, eine **Befehl** -Objekt unter Verwendung der entsprechenden SQL-Anweisungen und ein **Verbindung** Objekt. Führen Sie den Befehl mit der **ExecuteNonQuery** Methode der **Befehl** Objekt.  
  
 Im folgenden Codebeispiel wird eine gespeicherte Prozedur in einer Microsoft SQL Server-Datenbank erstellt.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +   
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +   
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +   
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Befehlen zum Ändern von Daten](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
