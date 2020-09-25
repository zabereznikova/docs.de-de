---
title: Formulieren von Projektionen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f0bc6dfcff7778ebc7156cbb039e13570c90467b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194400"
---
# <a name="formulate-projections"></a><span data-ttu-id="91871-102">Formulieren von Projektionen</span><span class="sxs-lookup"><span data-stu-id="91871-102">Formulate Projections</span></span>

<span data-ttu-id="91871-103">In den folgenden Beispielen wird gezeigt `select` , wie die-Anweisung in c# und die- `Select` Anweisung in Visual Basic mit anderen Funktionen kombiniert werden können, um Abfrage Projektionen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="91871-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91871-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-104">Example</span></span>  

 <span data-ttu-id="91871-105">Im folgenden Beispiel wird die- `Select` Klausel in Visual Basic (- `select` Klausel in c#) verwendet, um eine Sequenz von Kontaktnamen für zurückzugeben `Customers` .</span><span class="sxs-lookup"><span data-stu-id="91871-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="91871-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-106">Example</span></span>  

 <span data-ttu-id="91871-107">Im folgenden Beispiel wird die- `Select` Klausel in Visual Basic ( `select` -Klausel in c#) und *Anonyme Typen* verwendet, um eine Sequenz von Kontaktnamen und Telefonnummern für zurückzugeben `Customers` .</span><span class="sxs-lookup"><span data-stu-id="91871-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="91871-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-108">Example</span></span>  

 <span data-ttu-id="91871-109">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic ( `select` -Klausel in c#) und *Anonyme Typen* verwendet, um eine Sequenz von Namen und Telefonnummern für Mitarbeiter zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="91871-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="91871-110">Die `FirstName` `LastName` Felder und werden in einem einzelnen Feld ( `Name` ) kombiniert, und das `HomePhone` Feld wird `Phone` in der resultierenden Sequenz in umbenannt.</span><span class="sxs-lookup"><span data-stu-id="91871-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="91871-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-111">Example</span></span>  

 <span data-ttu-id="91871-112">Im folgenden Beispiel wird die- `Select` Klausel in Visual Basic ( `select` -Klausel in c#) und *Anonyme Typen* verwendet, um eine Sequenz aller `ProductID` s und einen berechneten Wert mit dem Namen zurückzugeben `HalfPrice` .</span><span class="sxs-lookup"><span data-stu-id="91871-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="91871-113">Dieser Wert wird auf den `UnitPrice`, geteilt durch 2, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="91871-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="91871-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-114">Example</span></span>  

 <span data-ttu-id="91871-115">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic ( `select` -Klausel in c#) und eine *bedingte-Anweisung* verwendet, um eine Sequenz von Produktname und Produktverfügbarkeit zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="91871-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="91871-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-116">Example</span></span>  

 <span data-ttu-id="91871-117">Im folgenden Beispiel wird eine Visual Basic `Select` -Klausel ( `select` -Klausel in c#) und ein *bekannter Typ* (Name) verwendet, um eine Sequenz der Mitarbeiter Namen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="91871-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="91871-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-118">Example</span></span>  

 <span data-ttu-id="91871-119">Im folgenden Beispiel wird `Select` und `Where` in Visual Basic ( `select` und `where` in c#) verwendet, um eine *gefilterte Sequenz* von Kontaktnamen für Kunden in London zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="91871-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="91871-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-120">Example</span></span>  

 <span data-ttu-id="91871-121">Im folgenden Beispiel wird eine `Select` -Klausel in Visual Basic ( `select` -Klausel in c#) und *Anonyme Typen* verwendet, um eine *geformte Teilmenge* der Daten zu Kunden zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="91871-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="91871-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91871-122">Example</span></span>  

 <span data-ttu-id="91871-123">Im folgenden Beispiel werden geschachtelte Abfragen verwendet, um die folgenden Ergebnisse zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="91871-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="91871-124">Eine Sequenz aller Bestellungen und der entsprechenden `OrderID`s.</span><span class="sxs-lookup"><span data-stu-id="91871-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="91871-125">Eine Untersequenz der Elemente in der Bestellung, für die es einen Rabatt gibt.</span><span class="sxs-lookup"><span data-stu-id="91871-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="91871-126">Der gesparte Betrag, wenn die Lieferkosten nicht eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="91871-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="91871-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91871-127">See also</span></span>

- [<span data-ttu-id="91871-128">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="91871-128">Query Examples</span></span>](query-examples.md)
