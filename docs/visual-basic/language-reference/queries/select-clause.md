---
title: Select-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d8cabcbd8554ca2aee639eaac8a52f0485a266
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="select-clause-visual-basic"></a>Select-Klausel (Visual Basic)
Definiert das Ergebnis einer Abfrage an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Teile  
 `var1`  
 Dies ist optional. Ein Alias, der verwendet werden kann, um die Ergebnisse des Spaltenausdrucks verweisen.  
  
 `fieldName1`  
 Erforderlich. Der Name des Felds in den Abfrageergebnissen zurückgegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Select` -Klausel, um die Ergebnisse von einer Abfrage zurückzugebenden definieren. So können Sie entweder die Member des ein neuer anonymer Typ definieren, die von einer Abfrage erstellt wird, oder für die Member eines benannten Typs gelten, die von einer Abfrage zurückgegeben wird. Die `Select` -Klausel ist nicht für eine Abfrage erforderlich. Wenn kein `Select` -Klausel angegeben ist, die Abfrage gibt einen Typ basierend auf alle Mitglieder der Bereichsvariablen für den aktuellen Bereich zurück. Weitere Informationen finden Sie unter [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Wenn eine Abfrage einen benannten Typ erstellt, wird ein Ergebnis vom Typ zurückgegeben <xref:System.Collections.Generic.IEnumerable%601> , in dem `T` der erstellte Typ ist.  
  
 Die `Select` -Klausel kann alle Variablen im aktuellen Bereich verweisen. Dies schließt Bereichsvariablen der `From` -Klausel (oder `From` Klauseln). Es enthält auch neue Variablen mit einem Alias erstellt die `Aggregate`, `Let`, `Group By`, oder `Group Join` Klauseln oder Variablen von einer früheren `Select` -Klausel in der Abfrageausdruck. Die `Select` -Klausel kann auch statische Werte enthalten. Z. B. das folgende Codebeispiel enthält einen Abfrageausdruck, in dem die `Select` -Klausel definiert das Abfrageergebnis als ein neuer anonymer Typ mit vier Mitglieder: `ProductName`, `Price`, `Discount`, und `DiscountedPrice`. Die `ProductName` und `Price` Elementwerten stammen aus der Produkt-Bereichsvariablen, die in definiert ist die `From` Klausel. Die `DiscountedPrice` Elementwert wird berechnet, der `Let` Klausel. Die `Discount` angehört, einen statischen Wert.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 Die `Select` -Klausel führt einen neuen Satz von Bereichsvariablen für nachfolgende Abfrageklauseln und vorherigen Bereichsvariablen sind nicht mehr im Gültigkeitsbereich. Der letzte `Select` -Klausel in einem Abfrageausdruck bestimmt den Rückgabewert der Abfrage. Die folgende Abfrage gibt z. B. das Unternehmen Name "und" Order ID für jede kundenbestellung für die die Summe 500 übersteigt. Die erste `Select` -Klausel kennzeichnet die Bereichsvariablen für die `Where` -Klausel und das zweite `Select` Klausel. Die zweite `Select` -Klausel kennzeichnet die Werte, die von der Abfrage als ein neuer anonymer Typ zurückgegeben.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 Wenn die `Select` -Klausel kennzeichnet ein einzelnes Element zurückgeben, der Abfrageausdruck gibt eine Auflistung des Typs dieses einzelnen Elements zurück. Wenn die `Select` -Klausel kennzeichnet mehrere Elemente zurückgegeben, der Abfrageausdruck gibt eine Auflistung ein neuer anonymer Typ, der auf Basis der ausgewählten Elemente zurück. Beispielsweise die folgenden beiden Abfragen zurückgeben Auflistungen von zwei verschiedenen Typen auf Grundlage der `Select` Klausel. Die erste Abfrage gibt eine Auflistung von Firmennamen als Zeichenfolgen zurück. Die zweite Abfrage gibt eine Auflistung von `Customer` Objekte, die mit den Firmennamen und Adressinformationen aufgefüllt.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage Ausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für die `customers` Auflistung. Die `Select` -Klausel wählt die Kundennamen- und ID-Wert, und füllt die `CompanyName` und `CustomerID` Spalten der neuen Bereichsvariablen. Die `For Each` -Anweisung durchläuft alle zurückgegebenen Objekte und zeigt die `CompanyName` und `CustomerID` Spalten für jeden Datensatz.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
