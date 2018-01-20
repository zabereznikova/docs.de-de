---
title: N-Schicht-LINQ to SQL mit ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5069c518998ca1d93f6e1ce94d76c8d0c7da07bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="b98e4-102">N-Schicht-LINQ to SQL mit ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b98e4-102">LINQ to SQL N-Tier with ASP.NET</span></span>
<span data-ttu-id="b98e4-103">In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] -Anwendungen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]verwenden, setzen Sie das <xref:System.Web.UI.WebControls.LinqDataSource> -Webserversteuerelement ein.</span><span class="sxs-lookup"><span data-stu-id="b98e4-103">In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="b98e4-104">Das Steuerelement behandelt den größten Teil der Logik, die benötigt wird, um Abfragen gegen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]auszuführen, Daten an den Browser zu übergeben, abzurufen und zum Update der Datenbank an [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> zu senden.</span><span class="sxs-lookup"><span data-stu-id="b98e4-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="b98e4-105">Sie konfigurieren das Steuerelement einfach im Markup, und das Steuerelement verarbeitet alle Datenübertragungen zwischen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Browser.</span><span class="sxs-lookup"><span data-stu-id="b98e4-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="b98e4-106">Da das Steuerelement die Interaktionen mit der Präsentationsebene und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenebene behandelt, liegt der Hauptfokus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] -Anwendungen mit mehreren Ebenen auf dem Schreiben einer benutzerdefinierten Geschäftslogik.</span><span class="sxs-lookup"><span data-stu-id="b98e4-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="b98e4-107">Weitere Informationen zu `LINQDataSource`, finden Sie unter [NIB: Übersicht über das LinqDataSource-Steuerelement](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).</span><span class="sxs-lookup"><span data-stu-id="b98e4-107">For more information about `LINQDataSource`, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98e4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b98e4-108">See Also</span></span>  
 [<span data-ttu-id="b98e4-109">N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b98e4-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
