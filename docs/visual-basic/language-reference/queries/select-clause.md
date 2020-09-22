---
title: Select-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: d96423efbee075a7ad257df72471c71e38e09b63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875746"
---
# <a name="select-clause-visual-basic"></a>Select-Klausel (Visual Basic)

Definiert das Ergebnis einer Abfrage.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Bestandteile  

 `var1`  
 Dies ist optional. Ein Alias, der zum Verweisen auf die Ergebnisse des Spalten Ausdrucks verwendet werden kann.  
  
 `fieldName1`  
 Erforderlich. Der Name des Felds, das im Abfrageergebnis zurückgegeben werden soll.  
  
## <a name="remarks"></a>Bemerkungen  

 Sie können die- `Select` Klausel verwenden, um die Ergebnisse zu definieren, die von einer Abfrage zurückgegeben werden sollen. Dies ermöglicht es Ihnen, entweder die Member eines neuen anonymen Typs zu definieren, der von einer Abfrage erstellt wird, oder die Member eines benannten Typs als Ziel festzulegen, der von einer Abfrage zurückgegeben wird. Die- `Select` Klausel ist für eine Abfrage nicht erforderlich. Wenn keine- `Select` Klausel angegeben wird, gibt die Abfrage einen Typ zurück, der auf allen Elementen der Bereichs Variablen basiert, die für den aktuellen Gültigkeitsbereich identifiziert werden. Weitere Informationen finden Sie unter [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md). Wenn eine Abfrage einen benannten Typ erstellt, wird ein Ergebnis vom Typ zurückgegeben, <xref:System.Collections.Generic.IEnumerable%601> wobei `T` der erstellte Typ ist.  
  
 Die- `Select` Klausel kann auf beliebige Variablen im aktuellen Gültigkeitsbereich verweisen. Dies schließt Bereichs Variablen ein, die in der- `From` Klausel (or- `From` Klauseln) identifiziert werden. Sie enthält auch alle neuen Variablen, die mit einem Alias durch die- `Aggregate` ,-,-oder-Klauseln erstellt `Let` `Group By` `Group Join` wurden, oder Variablen aus einer vorherigen `Select` Klausel im Abfrage Ausdruck. Die- `Select` Klausel kann auch statische Werte enthalten. Das folgende Codebeispiel zeigt beispielsweise einen Abfrage Ausdruck, in dem die- `Select` Klausel das Abfrageergebnis als neuen anonymen Typ mit vier Membern definiert: `ProductName` , `Price` , `Discount` und `DiscountedPrice` . Die `ProductName` -und- `Price` Member-Werte werden aus der in der-Klausel definierten Product Range-Variablen entnommen `From` . Der Element `DiscountedPrice` Wert wird in der- `Let` Klausel berechnet. Der- `Discount` Member ist ein statischer Wert.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 Die `Select` -Klausel führt einen neuen Satz von Bereichs Variablen für nachfolgende Abfrage Klauseln ein, und vorherige Bereichs Variablen befinden sich nicht mehr im Gültigkeitsbereich. Die letzte `Select` Klausel in einem Abfrage Ausdruck bestimmt den Rückgabewert der Abfrage. Die folgende Abfrage gibt z. b. den Firmennamen und die Auftrags-ID für jede Kundenbestellung zurück, für die der Gesamtwert 500 überschreitet. Die erste `Select` Klausel identifiziert die Bereichs Variablen für die `Where` -Klausel und die zweite- `Select` Klausel. Die zweite `Select` Klausel identifiziert die von der Abfrage zurückgegebenen Werte als neuen anonymen Typ.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Wenn die- `Select` Klausel ein einzelnes Element identifiziert, das zurückgegeben werden soll, gibt der Abfrage Ausdruck eine Auflistung des Typs dieses einzelnen Elements zurück. Wenn die- `Select` Klausel mehrere zurück zugebende Elemente identifiziert, gibt der Abfrage Ausdruck eine Auflistung eines neuen anonymen Typs zurück, basierend auf den ausgewählten Elementen. Beispielsweise geben die folgenden beiden Abfragen Auflistungen von zwei verschiedenen Typen basierend auf der- `Select` Klausel zurück. Die erste Abfrage gibt eine Auflistung von Firmennamen als Zeichen folgen zurück. Die zweite Abfrage gibt eine Auflistung von `Customer` -Objekten zurück, die mit den Firmennamen und Adressinformationen aufgefüllt werden.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Beispiel  

 Der folgende Abfrage Ausdruck verwendet eine- `From` Klausel, um eine Bereichs Variable für die Auflistung zu deklarieren `cust` `customers` . Die `Select` -Klausel wählt den Kundennamen und ID-Wert aus und füllt die `CompanyName` -Spalte und die- `CustomerID` Spalte der neuen Bereichs Variablen auf. Die `For Each` -Anweisung durchläuft jedes zurückgegebene Objekt und zeigt die `CompanyName` `CustomerID` Spalten und für jeden Datensatz an.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [From-Klausel](from-clause.md)
- [WHERE-Klausel](where-clause.md)
- [Order By-Klausel](order-by-clause.md)
- [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
