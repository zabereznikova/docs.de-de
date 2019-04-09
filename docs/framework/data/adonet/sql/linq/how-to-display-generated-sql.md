---
title: 'Vorgehensweise: Anzeigen von generiertem SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 8a69b3ae83d7f701428b3183f2b80e0d44a06537
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103622"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="babfc-102">Vorgehensweise: Anzeigen von generiertem SQL</span><span class="sxs-lookup"><span data-stu-id="babfc-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="babfc-103">Sie können den für Abfragen und Änderungsverarbeitung erzeugten SQL-Code mithilfe der <xref:System.Data.Linq.DataContext.Log%2A>-Eigenschaft anzeigen.</span><span class="sxs-lookup"><span data-stu-id="babfc-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="babfc-104">Dieser Ansatz kann zum Verständnis der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Funktionalität und zum Debugging spezifischer Probleme beitragen.</span><span class="sxs-lookup"><span data-stu-id="babfc-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="babfc-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="babfc-105">Example</span></span>  
 <span data-ttu-id="babfc-106">Im folgenden Beispiel wird die <xref:System.Data.Linq.DataContext.Log%2A>-Eigenschaft verwendet, um SQL-Code im Konsolenfenster anzuzeigen, bevor der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="babfc-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="babfc-107">Sie können diese Eigenschaft mit den Abfrage-, Einfüge-, Update- und Löschbefehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="babfc-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="babfc-108">Die Zeilen im Konsolenfenster entsprechen der Ausgabe beim Ausführen von Visual Basic oder C# folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="babfc-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="babfc-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="babfc-109">See also</span></span>

- [<span data-ttu-id="babfc-110">Debugunterstützung</span><span class="sxs-lookup"><span data-stu-id="babfc-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
