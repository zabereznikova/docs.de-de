---
title: Kontextverbindungen
ms.date: 03/30/2017
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.openlocfilehash: 7a2ac8e09b0c108780eb1972d7185ddbfe11b78f
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093995"
---
# <a name="the-context-connection"></a>Kontextverbindungen
Das Problem des internen Datenzugriffs ist ein gängiges Szenario. Dabei möchten Sie auf denselben Server zugreifen, auf dem die gespeicherte CLR-Prozedur oder CLR-Funktion (Common Language Runtime) ausgeführt wird. Eine Option liegt darin, mithilfe von <xref:System.Data.SqlClient.SqlConnection> eine Verbindung zu erstellen, eine Verbindungszeichenfolge anzugeben, die auf den lokalen Server zeigt, und die Verbindung zu öffnen. Dabei müssen Anmeldeinformationen für die Anmeldung angegeben werden. Die Verbindung befindet sich in einer anderen Datenbanksitzung als die gespeicherte Prozedur oder Funktion, sie kann über andere `SET`-Optionen verfügen, sie gehört zu einer separaten Transaktion, verfügt nicht über die temporären Tabellen usw. Wenn der verwaltete gespeicherte Prozedur- oder Funktionscode im SQL Server-Prozess ausgeführt wird, liegt dies daran, dass eine Verbindung mit diesem Server hergestellt und eine SQL-Anweisung ausgeführt wurde, die den Code aufruft. Möglicherweise möchten Sie die gespeicherte Prozedur oder Funktion im Kontext dieser Verbindung ausführen, zusammen mit ihrer Transaktion, den `SET`-Optionen usw. Dies wird als Kontextverbindung bezeichnet.  
  
 Mit der Kontextverbindung können Sie Transact-SQL-Anweisungen in demselben Kontext ausführen, der für den Code beim ersten Aufruf galt. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1.  [Kontextverbindungen](https://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a>Siehe auch
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
