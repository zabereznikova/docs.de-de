---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319543"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Navigiert durch die zwischen Entitäten eingerichteten Beziehungen.

## <a name="syntax"></a>Syntax

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Argumente

`instance-expression` eine Instanz einer Entität.

`relationship-type` den Typnamen der Beziehung aus der CSDL-Datei (konzeptionelle Schema Definitions Sprache). Der `relationship-type` wird als \<Namespace > qualifiziert.\<Beziehungstyp Name >.

`to` das Ende der Beziehung.

`from` den Anfang der Beziehung ab.

## <a name="return-value"></a>Rückgabewert

Wenn die Kardinalität des "to"-Endes "1" beträgt, ist der Rückgabewert `Ref<T>`. Wenn die Kardinalität des "to"-Endes "n" beträgt, ist der Rückgabewert `Collection<Ref<T>>`.

## <a name="remarks"></a>Hinweise

Beziehungen sind erstmalig Konstrukte im Entity Data Model (EDM). Beziehungen können zwischen zwei oder mehr Entitätstypen festgelegt werden, und Benutzer können über die Beziehung von einem Ende (Entität) zu einem anderen navigieren. `from` und `to` sind bedingt optional, wenn es keine Mehrdeutigkeit in der Namensauflösung innerhalb der Beziehung gibt.

NAVIGATE ist im O- und im C-Raum gültig.

Ein Navigationskonstrukt hat die folgende allgemeine Form:

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Beispiel:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Dabei ist "OrderCustomer" die `relationship`, und "Customer" und "Order" sind das `to-end` bzw. das `from-end` der Beziehung. Wenn "OrderCustomer" eine n:1-Beziehung war, ist der Ergebnistyp des Navigations Ausdrucks Ref\<Kunden >.

Eine einfachere Form dieses Ausdrucks ist die Folgende:

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Entsprechend erzeugt der Navigate-Ausdruck in einer Abfrage der folgenden Form eine Auflistung < Ref\<Order > >.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

Der Instanzausdruck muss ein Entitäts-/Verweistyp sein.

## <a name="example"></a>Beispiel

In der folgenden Entity SQL-Abfrage wird mithilfe des NAVIGATE-Operators die zwischen den Entitätstypen "Address" und "SalesOrderHeader" bestehende Beziehung navigiert. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:

1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Gewusst wie: Navigieren in Beziehungen mit dem Navigate-Operator](navigate-entity-sql.md)
