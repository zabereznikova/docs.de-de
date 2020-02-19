---
title: Bekannte Probleme in SqlClient für Entity Framework
ms.date: 03/30/2017
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
ms.openlocfilehash: 32a1dd22111498ab5b3b75940f5485b2957367e8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452499"
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Bekannte Probleme in SqlClient für Entity Framework
In diesem Abschnitt werden bekannte Probleme im Zusammenhang mit dem .NET Framework-Datenanbieter für SQL Server (SqlClient) beschrieben.  
  
## <a name="trailing-spaces-in-string-functions"></a>Nachfolgende Leerzeichen in Zeichenfolgenfunktionen  
 SQL Server ignoriert nachfolgende Leerzeichen in Zeichen folgen Werten. Deshalb kann die Übergabe von nachfolgenden Leerzeichen in der Zeichenfolge zu unvorhersehbaren Ergebnissen und sogar zu Fehlern führen.  
  
 Wenn die Zeichenfolge nachfolgende Leerzeichen enthalten muss, empfiehlt es sich, am Ende ein Leerstellen Zeichen zu anhängen, damit SQL Server die Zeichenfolge nicht schneidet. Wenn die nachfolgenden Leerzeichen nicht benötigt werden, sollten sie vor der Übergabe an die Abfragepipeline abgetrennt werden.  
  
## <a name="right-function"></a>RIGHT-Funktion  
 Wenn ein Wert, der nicht `null` ist, als erstes Argument und 0 als zweites Argument an `RIGHT(nvarchar(max)`, 0`)` oder `RIGHT(varchar(max)`, 0`)` übergeben wird, wird der Wert `NULL` anstelle einer Zeichenfolge, die `empty` ist, zurückgegeben.  
  
## <a name="cross-and-outer-apply-operators"></a>CROSS- und OUTER APPLY-Operatoren  
 Cross-und OUTER APPLY-Operatoren wurden in SQL Server 2005 eingeführt. In einigen Fällen liefert die Abfragepipeline möglicherweise eine Transact-SQL-Anweisung, die CROSS APPLY- und/oder OUTER APPLY-Operatoren enthält. Da einige Back-End-Anbieter, einschließlich Versionen von SQL Server vor SQL Server 2005, diese Operatoren nicht unterstützen, können solche Abfragen auf diesen Back-End-Anbietern nicht ausgeführt werden.  
  
 Dies sind einige typische Szenarios, die möglicherweise zum Auftreten von CROSS APPLY- und/oder OUTER APPLY-Operatoren in der Ausgabeabfrage führen:  
  
- Eine korrelierte Unterabfrage mit Paging.  
  
- Ein `AnyElement` über einer korrelierten Unterabfrage oder über einer von der Navigation erzeugten Auflistung.  
  
- LINQ-Abfragen, in denen Gruppierungsmethoden verwendet werden, die einen Elementselektor akzeptieren.  
  
- Eine Abfrage, in der ein CROSS APPLY oder ein OUTER APPLY explizit angegeben wird  
  
- Eine Abfrage, die über ein DEREF-Konstrukt über einem REF-Konstrukt verfügt.  
  
## <a name="skip-operator"></a>SKIP-Operator  
 Wenn Sie SQL Server 2000 verwenden, werden bei Verwendung von Skip mit Order by für nicht Schlüssel Spalten möglicherweise falsche Ergebnisse zurückgegeben. Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält. Dies liegt daran, wie Skip für SQL Server 2000 übersetzt wird. In der folgenden Abfrage können z. b. mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` über doppelte Werte verfügt:  
  
```sql  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>Verwenden der richtigen SQL Server-Version  
 Der Entity Framework auf die Transact-SQL-Abfrage basiert, die auf der SQL Server-Version basiert, die im `ProviderManifestToken`-Attribut des Schema-Elements in der Speichermodell Datei (SSDL) angegeben ist. Diese Version unterscheidet sich möglicherweise von der tatsächlichen SQL Server-Version, mit der Sie verbunden sind. Wenn Sie z. b. SQL Server 2005 verwenden, Ihr `ProviderManifestToken`-Attribut jedoch auf 2008 festgelegt ist, wird die generierte Transact-SQL-Abfrage möglicherweise nicht auf dem Server ausgeführt. Beispielsweise wird eine Abfrage, in der die in SQL Server 2008 eingeführten neuen Datums-/Zeittypen verwendet werden, nicht auf früheren Versionen von SQL Server ausgeführt. Wenn Sie SQL Server 2005 verwenden, Ihr `ProviderManifestToken`-Attribut jedoch auf 2000 festgelegt ist, ist die generierte Transact-SQL-Abfrage möglicherweise weniger optimiert, oder Sie erhalten eine Ausnahme, die besagt, dass die Abfrage nicht unterstützt wird. Weitere Informationen finden Sie oben im Abschnitt über die CROSS- und OUTER APPLY-Operatoren.  
  
 Bestimmte Datenbankverhaltensweisen hängen vom festgelegten Kompatibilitätsgrad der Datenbank ab. Wenn Ihr `ProviderManifestToken`-Attribut auf 2005 festgelegt ist und die SQL Server Version 2005 ist, aber der Kompatibilitäts Grad einer Datenbank auf "80" (SQL Server 2000) festgelegt ist, wird die generierte Transact-SQL-Datenbank auf SQL Server 2005 festgelegt, kann jedoch aufgrund der Einstellung für den Kompatibilitäts Grad nicht erwartungsgemäß ausgeführt werden. Zum Beispiel geht möglicherweise die Sortierung verloren, wenn ein Spaltenname in der ORDER BY-Liste einem Spaltennamen im Selektor entspricht.  
  
## <a name="nested-queries-in-projection"></a>Geschachtelte Abfragen in Projektion  
 Geschachtelte Abfragen in einer Projektionsklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden. Auf einigen Back-End-Servern, einschließlich SQL Server, kann dies dazu führen, dass die tempdb-Tabelle sehr groß wird. Dies kann die Serverleistung beeinträchtigen.  
  
 Im Folgenden sehen Sie ein Beispiel für eine geschachtelte Abfrage in einer Projektionsklausel:  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>Servergenerierte GUID-Identitätswerte  
 Der Entity Framework unterstützt vom Server generierte GUID-typidentitäts Werte, aber der Anbieter muss die Rückgabe des vom Server generierten Identitäts Werts unterstützen, nachdem eine Zeile eingefügt wurde. Ab SQL Server 2005 können Sie den vom Server generierten GUID-Typ in einer SQL Server-Datenbank über die [OUTPUT-Klausel](/sql/t-sql/queries/output-clause-transact-sql)zurückgeben.
  
## <a name="see-also"></a>Siehe auch

- [SqlClient für Entity Framework](sqlclient-for-the-entity-framework.md)
- [Bekannte Probleme von und Überlegungen zu LINQ to Entities](./language-reference/known-issues-and-considerations-in-linq-to-entities.md)
