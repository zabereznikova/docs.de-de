---
title: Die Bereichsvariable <variable> verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit im Abfrageausdruck deklarierte Variable
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 290ca81dea500558ed73956c91bdf7bfec312014
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400395"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Die Bereichsvariable \<variable> verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit im Abfrageausdruck deklarierte Variable
Ein in einer-,-,-oder-Klausel angegebener Bereichs Variablenname `Select` `From` `Aggregate` `Let` dupliziert den Namen einer bereits zuvor in der Abfrage angegebenen Bereichs Variablen oder den Namen einer Variablen, die implizit von der Abfrage deklariert wird, z. b. ein Feldname oder der Name einer Aggregatfunktion.  
  
 **Fehler-ID:** BC36633  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie sicher, dass alle Bereichs Variablen in einem bestimmten Abfrage Bereich eindeutige Namen aufweisen. Sie können eine Abfrage in Klammern einschließen, um sicherzustellen, dass geschachtelte Abfragen einen eindeutigen Bereich aufweisen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [From-Klausel](../queries/from-clause.md)
- [Let-Klausel](../queries/let-clause.md)
- [Aggregate Clause](../queries/aggregate-clause.md)
- [SELECT-Klausel](../queries/select-clause.md)
