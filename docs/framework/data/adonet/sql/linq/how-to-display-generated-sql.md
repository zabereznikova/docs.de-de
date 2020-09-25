---
title: 'Vorgehensweise: Anzeigen von generiertem SQL'
description: Erfahren Sie, wie Sie den für Abfragen generierten SQL-Code anzeigen, indem Sie die Log-Eigenschaft verwenden, um LINQ to SQL Funktionalität und Debuggen besser zu verstehen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 81f6b9603cc7f8b7863f787272ce6a1af920fa75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169491"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="04cdd-103">Vorgehensweise: Anzeigen von generiertem SQL</span><span class="sxs-lookup"><span data-stu-id="04cdd-103">How to: Display Generated SQL</span></span>

<span data-ttu-id="04cdd-104">Sie können den für Abfragen und Änderungsverarbeitung erzeugten SQL-Code mithilfe der <xref:System.Data.Linq.DataContext.Log%2A>-Eigenschaft anzeigen.</span><span class="sxs-lookup"><span data-stu-id="04cdd-104">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="04cdd-105">Dieser Ansatz kann zum Verständnis der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Funktionalität und zum Debugging spezifischer Probleme beitragen.</span><span class="sxs-lookup"><span data-stu-id="04cdd-105">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04cdd-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04cdd-106">Example</span></span>  

 <span data-ttu-id="04cdd-107">Im folgenden Beispiel wird die <xref:System.Data.Linq.DataContext.Log%2A>-Eigenschaft verwendet, um SQL-Code im Konsolenfenster anzuzeigen, bevor der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="04cdd-107">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="04cdd-108">Sie können diese Eigenschaft mit den Abfrage-, Einfüge-, Update- und Löschbefehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="04cdd-108">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="04cdd-109">Die Zeilen aus dem Konsolenfenster werden angezeigt, wenn Sie den folgenden Visual Basic oder c#-Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="04cdd-109">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="04cdd-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04cdd-110">See also</span></span>

- [<span data-ttu-id="04cdd-111">Debugunterstützung</span><span class="sxs-lookup"><span data-stu-id="04cdd-111">Debugging Support</span></span>](debugging-support.md)
