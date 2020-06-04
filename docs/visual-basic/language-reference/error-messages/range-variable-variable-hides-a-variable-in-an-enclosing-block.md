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
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="da7fe-102">Die Bereichsvariable \<variable> verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit im Abfrageausdruck deklarierte Variable</span><span class="sxs-lookup"><span data-stu-id="da7fe-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="da7fe-103">Ein in einer-,-,-oder-Klausel angegebener Bereichs Variablenname `Select` `From` `Aggregate` `Let` dupliziert den Namen einer bereits zuvor in der Abfrage angegebenen Bereichs Variablen oder den Namen einer Variablen, die implizit von der Abfrage deklariert wird, z. b. ein Feldname oder der Name einer Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="da7fe-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="da7fe-104">**Fehler-ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="da7fe-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da7fe-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="da7fe-105">To correct this error</span></span>  
  
- <span data-ttu-id="da7fe-106">Stellen Sie sicher, dass alle Bereichs Variablen in einem bestimmten Abfrage Bereich eindeutige Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="da7fe-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="da7fe-107">Sie können eine Abfrage in Klammern einschließen, um sicherzustellen, dass geschachtelte Abfragen einen eindeutigen Bereich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="da7fe-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7fe-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da7fe-108">See also</span></span>

- [<span data-ttu-id="da7fe-109">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da7fe-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="da7fe-110">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="da7fe-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="da7fe-111">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="da7fe-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="da7fe-112">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="da7fe-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="da7fe-113">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="da7fe-113">Select Clause</span></span>](../queries/select-clause.md)
