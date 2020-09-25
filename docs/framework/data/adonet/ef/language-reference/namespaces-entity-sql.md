---
title: Namespaces (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7a53f8e7e70dbc9fa505f7f8619af10a0e44c331
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197806"
---
# <a name="namespaces-entity-sql"></a>Namespaces (Entity SQL)

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] vermeidet Namenskonflikte bei globalen Bezeichnern wie Typnamen, Entitätenmengen, Funktionen usw. mithilfe von Namespaces. Die Namespace Unterstützung in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt der Namespace Unterstützung in der .NET Framework.  
  
  stellt, wie in folgendem Beispiel veranschaulicht, zwei Arten der USING-Klausel zur Verfügung: qualifizierte Namespaces (wobei ein kürzerer Alias für den Namespace bereitgestellt wird) und unqualifizierte Namespaces:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regeln zur Namensauflösung  

 Wenn ein Bezeichner nicht in den lokalen Bereichen aufgelöst werden kann, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Namen in den globalen Bereichen (den Namespaces) zu finden. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vergleicht zunächst den Bezeichner (Präfix) mit einem der qualifizierten Namespaces. Wenn eine Entsprechung vorliegt, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Rest des Bezeichners im angegebenen Namespace aufzulösen. Wenn keine Übereinstimmung festgestellt werden kann, wird eine Ausnahme ausgelöst.  
  
 Anschließend [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, alle nicht qualifizierten Namespaces (die im Prolog angegeben sind) für den Bezeichner zu durchsuchen. Wird der Bezeichner in genau einem Namespace gefunden, wird dieser Bereich zurückgegeben. Wenn dem Bezeichner mehrere Namespaces entsprechen, wird eine Ausnahme ausgelöst. Wenn für den Bezeichner kein Namespace identifiziert werden kann, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] übergibt den Namen an den nächsten äußeren Bereich (das- <xref:System.Data.Common.DbCommand> Objekt oder das- <xref:System.Data.Common.DbConnection> Objekt), wie im folgenden Beispiel veranschaulicht:  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Unterschiede zum .NET Framework  

 In der .NET Framework können Sie teilweise qualifizierte Namespaces verwenden. Mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist dies nicht zulässig.  
  
## <a name="adonet-usage"></a>Verwendung von ADO.NET  

 Abfragen werden mit ADO.NET-<xref:System.Data.Common.DbCommand>-Objekten ausgedrückt. <xref:System.Data.Common.DbCommand>-Objekte werden über <xref:System.Data.Common.DbConnection>-Objekte erstellt. Namespaces können außerdem als Teil der <xref:System.Data.Common.DbCommand>- und <xref:System.Data.Common.DbConnection>-Objekte spezifiziert werden. Wenn [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ein Bezeichner in der Abfrage nicht auflösen kann, werden die externen Namespaces (basierend auf ähnlichen Regeln) geprüft.  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
