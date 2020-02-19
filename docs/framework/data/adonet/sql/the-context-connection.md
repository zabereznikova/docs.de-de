---
title: Die Kontextverbindung
ms.date: 03/30/2017
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.openlocfilehash: e237bb53c699fd4bf051876a378c31b73a038502
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451810"
---
# <a name="the-context-connection"></a>Die Kontextverbindung
Der interne Datenzugriff ist ein verbreitetes Problem. Es tritt auf, wenn Sie auf denselben Server zugreifen möchten, auf dem auch die CLR-gespeicherte Prozedur (Common Language Runtime, CLR) oder -Funktion ausgeführt wird. Eine der Optionen besteht darin, mithilfe von <xref:System.Data.SqlClient.SqlConnection> eine Verbindung zu erstellen, eine Verbindungszeichenfolge anzugeben, die auf den lokalen Server zeigt, und die Verbindung anschließend zu öffnen. Dies erfordert die Angabe von Anmeldeinformationen für die Anmeldung. Die Verbindung wurde in einer anderen Datenbanksitzung als die gespeicherte Prozedur oder Funktion hergestellt, sie verwendet möglicherweise andere `SET`-Optionen, befindet sich in einer separaten Transaktion, hat keinen Zugriff auf die temporären Tabellen usw. Wenn der Code Ihrer verwalteten gespeicherten Prozedur oder Funktion im SQL Serverprozess ausgeführt wird, liegt das daran, dass jemand eine Verbindung mit diesem Server hergestellt und eine SQL-Anweisung ausgeführt hat, um den Code aufzurufen. Nun möchten Sie eventuell die gespeicherte Prozedur oder Funktion im Kontext dieser Verbindung ausführen, zusammen mit deren Transaktion, `SET`-Optionen und so weiter. Dies wird als Kontextverbindung bezeichnet.  
  
 Die Kontextverbindung ermöglicht, Transact-SQL-Anweisungen im selben Kontext auszuführen wie den Code, der anfänglich aufgerufen wurde. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
1. [Kontextverbindungen](/sql/relational-databases/clr-integration/data-access/context-connection)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../ado-net-overview.md)
