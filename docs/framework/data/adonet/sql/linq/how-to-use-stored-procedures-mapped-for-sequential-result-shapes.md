---
title: 'Gewusst wie: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet sind'
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
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a110cf2f321915ef65c571a30a19c5a29bdb8af2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="1f0e9-102">Gewusst wie: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="1f0e9-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="1f0e9-103">Diese Art von gespeicherten Prozeduren kann mehr als eine Ergebnisform erstellen. Sie wissen jedoch, in welcher Reihenfolge die Ergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="1f0e9-104">Stellen Sie dieses Szenario dem Szenario gegenüber, bei dem Sie die Rückgabereihenfolge nicht kennen.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="1f0e9-105">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden gespeicherte Prozeduren für die mehrere Ergebnisformen zugeordnet](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e9-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f0e9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f0e9-106">Example</span></span>  
 <span data-ttu-id="1f0e9-107">Es folgt das T-SQL einer gespeicherten Prozedur, die mehrere Ergebnisformen sequenziell zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="1f0e9-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="1f0e9-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f0e9-108">Example</span></span>  
 <span data-ttu-id="1f0e9-109">Um die gespeicherte Prozedur auszuführen, wird in etwa der folgende Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="1f0e9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f0e9-110">See Also</span></span>  
 [<span data-ttu-id="1f0e9-111">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1f0e9-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
