---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 993c07b824d30c89773c5cfea90c7c194c6b3869
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356876"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Navigiert durch die zwischen Entitäten eingerichteten Beziehungen.

## <a name="syntax"></a>Syntax

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Argumente

`instance-expression` Eine Instanz einer Entität.

`relationship-type` Der Typname der Beziehung aus der konzeptionellen Schema Definition Language (CSDL) Datei. Die `relationship-type` ist qualifiziert, als \<Namespace >.\< Beziehungstypname >.

`to` Das Ende der Beziehung.

`from` Der Anfang der Beziehung.

## <a name="return-value"></a>Rückgabewert

Wenn die Kardinalität des "to"-Endes "1" beträgt, ist der Rückgabewert `Ref<T>`. Wenn die Kardinalität des "to"-Endes "n" beträgt, ist der Rückgabewert `Collection<Ref<T>>`.

## <a name="remarks"></a>Hinweise

Beziehungen sind im [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM) Konstrukte der ersten Klasse. Beziehungen können zwischen zwei oder mehr Entitätstypen festgelegt werden, und Benutzer können über die Beziehung von einem Ende (Entität) zu einem anderen navigieren. `from` und `to` sind bedingt optional, wenn es keine Mehrdeutigkeit in der Namensauflösung innerhalb der Beziehung gibt.

NAVIGATE ist im O- und im C-Raum gültig.

Ein Navigationskonstrukt hat die folgende allgemeine Form:

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Beispiel:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Dabei ist "OrderCustomer" die `relationship`, und "Customer" und "Order" sind das `to-end` bzw. das `from-end` der Beziehung. Wenn "OrderCustomer" eine n: 1-Beziehung war, dann ist der Ergebnistyp des Navigationsausdrucks Ref\<Kunden >.

Eine einfachere Form dieses Ausdrucks ist die Folgende:

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Auf ähnliche Weise in einer Abfrage der folgenden Form Navigationsausdrucks ergibt eine Auflistung < Ref\<Reihenfolge >>.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

Der Instanzausdruck muss ein Entitäts-/Verweistyp sein.

## <a name="example"></a>Beispiel

In der folgenden Entity SQL-Abfrage wird mithilfe des NAVIGATE-Operators die zwischen den Entitätstypen "Address" und "SalesOrderHeader" bestehende Beziehung navigiert. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:

1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Vorgehensweise: Navigieren Sie Beziehungen mit Navigate-Operator](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
