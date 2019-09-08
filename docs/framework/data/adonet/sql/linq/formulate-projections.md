---
title: Formulieren von Projektionen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793826"
---
# <a name="formulate-projections"></a><span data-ttu-id="77316-102">Formulieren von Projektionen</span><span class="sxs-lookup"><span data-stu-id="77316-102">Formulate Projections</span></span>
<span data-ttu-id="77316-103">In den folgenden Beispielen wird veranschaulicht `select` , wie C# die `Select` -Anweisung in-und-Anweisung in Visual Basic mit anderen Funktionen kombiniert werden kann, um Abfrage Projektionen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="77316-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77316-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-104">Example</span></span>  
 <span data-ttu-id="77316-105">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic`select` (- C#Klausel in) verwendet, um eine Sequenz von `Customers`Kontaktnamen für zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="77316-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-106">Example</span></span>  
 <span data-ttu-id="77316-107">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic`select` (- C#Klausel in) und *anonymen Typen* verwendet, um eine Sequenz von Kontaktnamen und `Customers`Telefonnummern für zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="77316-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-108">Example</span></span>  
 <span data-ttu-id="77316-109">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic`select` (- C#Klausel in) und *anonymen Typen* verwendet, um eine Sequenz von Namen und Telefonnummern für Mitarbeiter zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="77316-110">Die `FirstName` Felder `LastName` und werden in einem einzelnen Feld (`Name` `Phone` ) kombiniert, und das `HomePhone` Feld wird in der resultierenden Sequenz in umbenannt.</span><span class="sxs-lookup"><span data-stu-id="77316-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="77316-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-111">Example</span></span>  
 <span data-ttu-id="77316-112">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic`select` (- C#Klausel in) und *anonymen Typen* verwendet, um eine `ProductID`Sequenz aller s und einen berechneten `HalfPrice`Wert mit dem Namen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="77316-113">Dieser Wert wird auf den `UnitPrice`, geteilt durch 2, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="77316-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="77316-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-114">Example</span></span>  
 <span data-ttu-id="77316-115">Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic`select` (- C#Klausel in) und eine *bedingte-Anweisung* verwendet, um eine Sequenz von Produktname und Produktverfügbarkeit zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="77316-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-116">Example</span></span>  
 <span data-ttu-id="77316-117">Im folgenden Beispiel wird eine Visual Basic `Select` -Klausel`select` (- C#Klausel in) und ein *bekannter Typ* (Name) verwendet, um eine Sequenz der Mitarbeiter Namen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="77316-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-118">Example</span></span>  
 <span data-ttu-id="77316-119">Im folgenden Beispiel wird `Select` und `Where` in Visual Basic (`select` und `where` in C#) verwendet, um eine *gefilterte Sequenz* von Kontaktnamen für Kunden in London zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="77316-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-120">Example</span></span>  
 <span data-ttu-id="77316-121">Im folgenden Beispiel wird eine `Select` -Klausel in Visual Basic`select` (- C#Klausel in) und *anonymen Typen* verwendet, um eine *geformte Teilmenge* der Daten zu Kunden zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77316-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="77316-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77316-122">Example</span></span>  
 <span data-ttu-id="77316-123">Im folgenden Beispiel werden geschachtelte Abfragen verwendet, um die folgenden Ergebnisse zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="77316-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="77316-124">Eine Sequenz aller Bestellungen und der entsprechenden `OrderID`s.</span><span class="sxs-lookup"><span data-stu-id="77316-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="77316-125">Eine Untersequenz der Elemente in der Bestellung, für die es einen Rabatt gibt.</span><span class="sxs-lookup"><span data-stu-id="77316-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="77316-126">Der gesparte Betrag, wenn die Lieferkosten nicht eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="77316-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="77316-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77316-127">See also</span></span>

- [<span data-ttu-id="77316-128">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="77316-128">Query Examples</span></span>](query-examples.md)
