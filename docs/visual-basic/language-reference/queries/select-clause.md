---
title: Select-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 367d810c2358963bfe2f092a390443eccdc66941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945261"
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
 Sie können die `Select` -Klausel, um zu definieren, die aus einer Abfrage zurückzugebenden Ergebnisse auf. Dadurch können Sie entweder die Mitglieder der neuen anonymen Typ definieren, die von einer Abfrage erstellt wird, oder die Member eines benannten Typs als Ziel, die von einer Abfrage zurückgegeben wird. Die `Select` Klausel ist nicht für eine Abfrage erforderlich. Wenn kein `Select` -Klausel angegeben ist, gibt die Abfrage einen Typ basierend auf alle Mitglieder der Bereichsvariablen für den aktuellen Bereich zurück. Weitere Informationen finden Sie unter [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Wenn eine Abfrage einen benannten Typ erstellt wird, gibt es ein Ergebnis vom Typ <xref:System.Collections.Generic.IEnumerable%601> , in denen `T` der erstellte Typ ist.  
  
 Die `Select` -Klausel kann auf alle Variablen im aktuellen Bereich verweisen. Dies schließt Bereichsvariablen, die der `From` Klausel (oder `From` Klauseln). Es enthält auch neuen Variablen mit einem Alias erstellt die `Aggregate`, `Let`, `Group By`, oder `Group Join` -Klauseln oder Variablen aus einer vorherigen `Select` -Klausel in der Abfrageausdruck. Die `Select` -Klausel kann auch statische Werte enthalten. Z. B. das folgende Codebeispiel enthält einen Abfrageausdruck, in dem die `Select` -Klausel definiert das Abfrageergebnis als ein neuer anonymer Typ mit vier Mitglieder: `ProductName`, `Price`, `Discount`, und `DiscountedPrice`. Die `ProductName` und `Price` Werte stammen aus der Product-Range-Variable, die in definiert ist die `From` Klausel. Die `DiscountedPrice` Memberwert wird berechnet, der `Let` Klausel. Die `Discount` Member ist ein statischer Wert.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 Die `Select` Klausel führt einen neuen Satz von Bereichsvariablen für nachfolgende Abfrageklauseln und vorherigen Bereichsvariablen sind nicht mehr im Gültigkeitsbereich. Die letzte `Select` -Klausel in einem Abfrageausdruck bestimmt den Rückgabewert der Abfrage. Z. B. gibt die folgende Abfrage das Unternehmen und Order-ID für jede kundenbestellung für die die Summe 500 übersteigt. Die erste `Select` -Klausel kennzeichnet die Bereichsvariablen für die `Where` -Klausel und das zweite `Select` Klausel. Die zweite `Select` -Klausel gibt die Werte, die von der Abfrage als ein neuer anonymer Typ zurückgegeben.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Wenn die `Select` -Klausel kennzeichnet ein einzelnes Element zurückgeben, der Abfrageausdruck gibt eine Auflistung vom Typ des einzelnen Elements zurück. Wenn die `Select` -Klausel kennzeichnet die mehrere Elemente zurückgegeben, der Abfrageausdruck gibt eine Auflistung ein neuer anonymer Typ, der auf Basis der ausgewählten Elemente zurück. Beispielsweise die folgenden beiden Abfragen zurück Auflistungen von zwei unterschiedliche Typen auf Grundlage der `Select` Klausel. Die erste Abfrage gibt eine Auflistung von Firmennamen einfügen als Zeichenfolgen zurück. Die zweite Abfrage gibt eine Auflistung von `Customer` Objekte, die mit dem Firmennamen und Informationen zur Adresse aufgefüllt.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für die `customers` Auflistung. Die `Select` -Klausel wählt das Customer Name und ID-Wert, und füllt die `CompanyName` und `CustomerID` Spalten der neuen Bereichsvariablen. Die `For Each` -Anweisung durchläuft alle zurückgegebenen Objekte und zeigt die `CompanyName` und `CustomerID` Spalten für jeden Datensatz.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
