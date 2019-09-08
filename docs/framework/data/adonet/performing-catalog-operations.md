---
title: Ausführen von Katalogoperationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 0291b6684092ec15fc672c39c909caf7781194e3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783258"
---
# <a name="performing-catalog-operations"></a>Ausführen von Katalogoperationen
Zum Ausführen eines Befehls zum Ändern einer Datenbank oder eines Katalogs, wie z. b. der CREATE TABLE oder der CREATE PROCEDURE-Anweisung, erstellen Sie ein **Command** -Objekt mit den entsprechenden SQL-Anweisungen und einem **Verbindungs** Objekt. Führen Sie den Befehl mit der **ExecuteNonQuery** -Methode des **Command** -Objekts aus.  
  
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

- [Verwenden von Befehlen zum Ändern von Daten](using-commands-to-modify-data.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
