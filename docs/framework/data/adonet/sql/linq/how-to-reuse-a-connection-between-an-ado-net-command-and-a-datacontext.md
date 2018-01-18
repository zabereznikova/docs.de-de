---
title: 'Gewusst wie: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"'
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
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 196b3c8735168ea935aa1a0d3917dd34b2aa390f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="d1992-102">Gewusst wie: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"</span><span class="sxs-lookup"><span data-stu-id="d1992-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="d1992-103">Da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist ein Teil der [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Technologiefamilie und basiert auf Dienste von [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], können Sie eine Verbindung zwischen Wiederverwenden einer [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Befehl und einem <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="d1992-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1992-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1992-104">Example</span></span>  
 <span data-ttu-id="d1992-105">Im folgenden Beispiel wird gezeigt, wie die gleiche Verbindung zwischen einem [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]-Befehl und dem <xref:System.Data.Linq.DataContext> wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d1992-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d1992-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1992-106">See Also</span></span>  
 [<span data-ttu-id="d1992-107">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="d1992-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="d1992-108">ADO.NET und LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d1992-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [<span data-ttu-id="d1992-109">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="d1992-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
