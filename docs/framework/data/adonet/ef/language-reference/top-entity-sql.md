---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 16be25336bac386c993eae7527c9377be1073d1e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319272"
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)

Der SELECT-Klausel kann hinter dem optionalen ALL/DISTINCT-Modifizierer eine TOP-Unterklausel angefügt werden. Die TOP-Unterklausel gibt an, dass nur der erste Zeilensatz aus dem Abfrageergebnis zurückgegeben wird.

## <a name="syntax"></a>Syntax

```sql
[ TOP (n) ]
```

## <a name="arguments"></a>Argumente

`n` der numerische Ausdruck, der die Anzahl der zurück zugegenden Zeilen angibt. `n` könnte ein einzelnes numerisches Literal oder ein einzelner Parameter sein.

## <a name="remarks"></a>Hinweise

Beim TOP-Ausdruck muss es sich entweder um ein einzelnes numerisches Literal oder um einen einzelnen Parameter handeln. Wenn ein konstantes Literal verwendet wird, muss der Literaltyp implizit zu „Edm.Int64“ heraufstufbar sein („byte“, „int16“, „int32“ oder „int64“ oder ein Anbietertyp, der einem zu „Edm.Int64“ heraufstufbaren Typ zugeordnet wird) und über einen Wert verfügen, der größer oder gleich null ist. Andernfalls wird eine Ausnahme ausgelöst. Wird ein Parameter als Ausdruck verwendet, muss der Parametertyp ebenfalls implizit zu „Edm.Int64“ heraufstufbar sein. Es wird jedoch während der Kompilierung keine Überprüfung des tatsächlichen Parameterwerts durchgeführt, da die Parameterwerte spät gebunden werden.

Im Folgenden finden Sie ein Beispiel für einen konstanten TOP-Ausdruck:

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

Im folgenden finden Sie ein Beispiel für einen parametrisierten Top-Ausdruck:

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

Wenn die Abfrage nicht sortiert ist, ist TOP nicht deterministisch. Wenn ein deterministisches Ergebnis benötigt wird, sollte die [SKIP](skip-entity-sql.md) -Unterklausel und die [LIMIT](limit-entity-sql.md) -Unterklausel in der [ORDER BY](order-by-entity-sql.md) -Klausel verwendet werden. TOP und SKIP/LIMIT schließen sich gegenseitig aus.

## <a name="example"></a>Beispiel

Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage verwendet TOP, um die oberste Zeile, die vom Abfrageergebnis zurückgegeben werden soll, anzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:

1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:

    [!code-sql[DP EntityServices Concepts#TOP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#top)]

## <a name="see-also"></a>Siehe auch

- [SELECT](select-entity-sql.md)
- [SKIP](skip-entity-sql.md)
- [LIMIT](limit-entity-sql.md)
- [ORDER BY](order-by-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
