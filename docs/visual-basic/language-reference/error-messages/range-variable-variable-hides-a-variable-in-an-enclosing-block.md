---
title: Die Bereichsvariable <variable> verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit im Abfrageausdruck deklarierte Variable
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 90fed3dd27f18fe87c326cc36dfb774822fc4b21
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162348"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>BC36633: die Bereichs Variable \<variable> verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichs Variable oder eine implizit deklarierte Variable in einem Abfrage Ausdruck.

Ein in einer-,-,-oder-Klausel angegebener Bereichs Variablenname `Select` `From` `Aggregate` `Let` dupliziert den Namen einer bereits zuvor in der Abfrage angegebenen Bereichs Variablen oder den Namen einer Variablen, die implizit von der Abfrage deklariert wird, z. b. ein Feldname oder der Name einer Aggregatfunktion.

 **Fehler-ID:** BC36633

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Stellen Sie sicher, dass alle Bereichs Variablen in einem bestimmten Abfrage Bereich eindeutige Namen aufweisen. Sie können eine Abfrage in Klammern einschließen, um sicherzustellen, dass geschachtelte Abfragen einen eindeutigen Bereich aufweisen.

## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [From-Klausel](../queries/from-clause.md)
- [Let-Klausel](../queries/let-clause.md)
- [Aggregate Clause](../queries/aggregate-clause.md)
- [SELECT-Klausel](../queries/select-clause.md)
