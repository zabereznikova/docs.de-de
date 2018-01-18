---
title: Formulieren von Projektionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 67c196b5c693e36e45d4cad4fa75e08145dd699d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="formulate-projections"></a><span data-ttu-id="eefa0-102">Formulieren von Projektionen</span><span class="sxs-lookup"><span data-stu-id="eefa0-102">Formulate Projections</span></span>
<span data-ttu-id="eefa0-103">Das folgende Beispiel zeigt, wie die `select`-Anweisung in C# und die `Select`-Anweisung in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] mit anderen Funktionen kombiniert werden können, um Abfrageprojektionen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="eefa0-103">The following examples show how the `select` statement in C# and `Select` statement in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eefa0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-104">Example</span></span>  
 <span data-ttu-id="eefa0-105">Im folgenden Beispiel wird die `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) um eine Sequenz mit Kontaktnamen von zurückzugeben `Customers`.</span><span class="sxs-lookup"><span data-stu-id="eefa0-105">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-106">Example</span></span>  
 <span data-ttu-id="eefa0-107">Im folgenden Beispiel wird die `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) und *anonyme Typen* gibt eine Sequenz von Kontaktnamen und Telefonnummern für `Customers`.</span><span class="sxs-lookup"><span data-stu-id="eefa0-107">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-108">Example</span></span>  
 <span data-ttu-id="eefa0-109">Im folgenden Beispiel wird die `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) und *anonyme Typen* gibt eine Sequenz von Namen und Telefonnummern für Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="eefa0-109">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="eefa0-110">Die `FirstName` und `LastName` Felder werden in einem einzelnen Feld kombiniert (`Name`), und die `HomePhone` Feld wird umbenannt, um `Phone` in der resultierenden Sequenz.</span><span class="sxs-lookup"><span data-stu-id="eefa0-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-111">Example</span></span>  
 <span data-ttu-id="eefa0-112">Im folgenden Beispiel wird die `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) und *anonyme Typen* zurückzugebenden eine Sequenz aller `ProductID`s und einen berechneten Wert namens `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="eefa0-112">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="eefa0-113">Dieser Wert wird auf den `UnitPrice`, geteilt durch 2, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eefa0-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-114">Example</span></span>  
 <span data-ttu-id="eefa0-115">Im folgenden Beispiel wird die `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) und ein *bedingungsanweisung* um eine Sequenz von Produktnamen und produktverfügbarkeit zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="eefa0-115">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-116">Example</span></span>  
 <span data-ttu-id="eefa0-117">Im folgenden Beispiel wird eine [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` -Klausel (`select` -Klausel in c#) und ein *bekannten Typ* (Name), um eine Sequenz mit den Namen der Mitarbeiter zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="eefa0-117">The following example uses a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-118">Example</span></span>  
 <span data-ttu-id="eefa0-119">Im folgenden Beispiel wird `Select` und `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` und `where` in c#) zum Zurückgeben einer *gefilterte Sequenz* mit Kontaktnamen von Kunden in London.</span><span class="sxs-lookup"><span data-stu-id="eefa0-119">The following example uses `Select` and `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-120">Example</span></span>  
 <span data-ttu-id="eefa0-121">Im folgenden Beispiel wird eine `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) und *anonyme Typen* zurückzugebenden eine *geformte Teilmenge* der Daten über Kunden.</span><span class="sxs-lookup"><span data-stu-id="eefa0-121">The following example uses a `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="eefa0-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefa0-122">Example</span></span>  
 <span data-ttu-id="eefa0-123">Im folgenden Beispiel werden geschachtelte Abfragen verwendet, um die folgenden Ergebnisse zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="eefa0-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="eefa0-124">Eine Sequenz aller Bestellungen und der entsprechenden `OrderID`s.</span><span class="sxs-lookup"><span data-stu-id="eefa0-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="eefa0-125">Eine Untersequenz der Elemente in der Bestellung, für die es einen Rabatt gibt.</span><span class="sxs-lookup"><span data-stu-id="eefa0-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="eefa0-126">Der gesparte Betrag, wenn die Lieferkosten nicht eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="eefa0-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="eefa0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eefa0-127">See Also</span></span>  
 [<span data-ttu-id="eefa0-128">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="eefa0-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
