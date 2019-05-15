---
title: Namespaces (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7bcd7a72df8afbd598a15ccd9a259ed11b5b9ef7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583812"
---
# <a name="namespaces-entity-sql"></a>Namespaces (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] vermeidet Namenskonflikte bei globalen Bezeichnern wie Typnamen, Entitätenmengen, Funktionen usw. mithilfe von Namespaces. Unterstützung von Namespaces in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist vergleichbar mit der Unterstützung von Namespaces in .NET Framework.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt, wie in folgendem Beispiel veranschaulicht, zwei Arten der USING-Klausel zur Verfügung: qualifizierte Namespaces (wobei ein kürzerer Alias für den Namespace bereitgestellt wird) und unqualifizierte Namespaces:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regeln zur Namensauflösung  
 Wenn ein Bezeichner in den lokalen Bereichen aufgelöst werden kann [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Namen in den globalen Bereichen (den Namespaces) zu finden. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vergleicht zunächst den Bezeichner (Präfix) mit einem der qualifizierten Namespaces. Wenn eine Übereinstimmung vorliegt, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Rest des Bezeichners im angegebenen Namespace aufzulösen. Wenn keine Übereinstimmung festgestellt werden kann, wird eine Ausnahme ausgelöst.  
  
 Als Nächstes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, die allen unqualifizierten Namespaces (angegeben im Prolog) für den Bezeichner zu suchen. Wird der Bezeichner in genau einem Namespace gefunden, wird dieser Bereich zurückgegeben. Wenn dem Bezeichner mehrere Namespaces entsprechen, wird eine Ausnahme ausgelöst. Wenn für den Bezeichner kein Namespace gefunden werden kann [!INCLUDE[esql](../../../../../../includes/esql-md.md)] übergibt den Namen an den nächsten äußeren Bereich (das <xref:System.Data.Common.DbCommand> oder <xref:System.Data.Common.DbConnection> Objekt), wie im folgenden Beispiel dargestellt:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Unterschiede zum .NET Framework  
 In .NET Framework können Sie teilweise qualifizierte Namespaces verwenden. Mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist dies nicht zulässig.  
  
## <a name="adonet-usage"></a>Verwendung von ADO.NET  
 Abfragen werden mit ADO.NET-<xref:System.Data.Common.DbCommand>-Objekten ausgedrückt. <xref:System.Data.Common.DbCommand>-Objekte werden über <xref:System.Data.Common.DbConnection>-Objekte erstellt. Namespaces können außerdem als Teil der <xref:System.Data.Common.DbCommand>- und <xref:System.Data.Common.DbConnection>-Objekte spezifiziert werden. Wenn [!INCLUDE[esql](../../../../../../includes/esql-md.md)] einen Bezeichner kann nicht aufgelöst werden in der Abfrage selbst, werden die externen Namespaces (basierend auf ähnlichen Regeln) überprüft.  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
