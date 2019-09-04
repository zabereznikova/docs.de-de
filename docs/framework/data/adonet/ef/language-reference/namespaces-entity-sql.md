---
title: Namespaces (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 395ffb23859be27b4897dfc352f6e44d52286b26
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249993"
---
# <a name="namespaces-entity-sql"></a>Namespaces (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] vermeidet Namenskonflikte bei globalen Bezeichnern wie Typnamen, Entitätenmengen, Funktionen usw. mithilfe von Namespaces. Die Namespace Unterstützung in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt der Namespace Unterstützung in der .NET Framework.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt, wie in folgendem Beispiel veranschaulicht, zwei Arten der USING-Klausel zur Verfügung: qualifizierte Namespaces (wobei ein kürzerer Alias für den Namespace bereitgestellt wird) und unqualifizierte Namespaces:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regeln zur Namensauflösung  
 Wenn ein Bezeichner nicht in den lokalen Bereichen aufgelöst werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kann, versucht, den Namen in den globalen Bereichen (den Namespaces) zu finden. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vergleicht zunächst den Bezeichner (Präfix) mit einem der qualifizierten Namespaces. Wenn eine Entsprechung vorliegt, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Rest des Bezeichners im angegebenen Namespace aufzulösen. Wenn keine Übereinstimmung festgestellt werden kann, wird eine Ausnahme ausgelöst.  
  
 Anschließend versucht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , alle nicht qualifizierten Namespaces (die im Prolog angegeben sind) für den Bezeichner zu durchsuchen. Wird der Bezeichner in genau einem Namespace gefunden, wird dieser Bereich zurückgegeben. Wenn dem Bezeichner mehrere Namespaces entsprechen, wird eine Ausnahme ausgelöst. Wenn für den Bezeichner kein Namespace identifiziert werden kann [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , übergibt den Namen an den nächsten äußeren Bereich ( <xref:System.Data.Common.DbCommand> das <xref:System.Data.Common.DbConnection> -Objekt oder das-Objekt), wie im folgenden Beispiel veranschaulicht:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Unterschiede zum .NET Framework  
 In der .NET Framework können Sie teilweise qualifizierte Namespaces verwenden. Mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist dies nicht zulässig.  
  
## <a name="adonet-usage"></a>Verwendung von ADO.NET  
 Abfragen werden mit ADO.NET-<xref:System.Data.Common.DbCommand>-Objekten ausgedrückt. <xref:System.Data.Common.DbCommand>-Objekte werden über <xref:System.Data.Common.DbConnection>-Objekte erstellt. Namespaces können außerdem als Teil der <xref:System.Data.Common.DbCommand>- und <xref:System.Data.Common.DbConnection>-Objekte spezifiziert werden. Wenn [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ein Bezeichner in der Abfrage nicht auflösen kann, werden die externen Namespaces (basierend auf ähnlichen Regeln) geprüft.  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
