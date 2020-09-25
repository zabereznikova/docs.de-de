---
title: N-Schicht-LINQ to SQL mit ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: a184c9dcb29e7994aefa4062be2b30484539c4e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175316"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="9eec6-102">N-Schicht-LINQ to SQL mit ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9eec6-102">LINQ to SQL N-Tier with ASP.NET</span></span>

<span data-ttu-id="9eec6-103">In ASP.NET-Anwendungen, die verwenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , verwenden Sie das- <xref:System.Web.UI.WebControls.LinqDataSource> Webserver Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9eec6-103">In ASP.NET applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="9eec6-104">Das Steuerelement behandelt den größten Teil der Logik, die für die Abfrage erforderlich [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist, übergibt die Daten an den Browser, ruft Sie ab und sendet Sie an die, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> die dann die Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9eec6-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="9eec6-105">Sie konfigurieren das Steuerelement einfach im Markup, und das Steuerelement verarbeitet alle Datenübertragungen zwischen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Browser.</span><span class="sxs-lookup"><span data-stu-id="9eec6-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="9eec6-106">Da das Steuerelement die Interaktionen mit der Präsentationsebene behandelt und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenebene behandelt, liegt der Hauptfokus in ASP.NET Anwendungen mit mehreren Ebenen auf dem Schreiben der benutzerdefinierten Geschäftslogik.</span><span class="sxs-lookup"><span data-stu-id="9eec6-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in ASP.NET multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="9eec6-107">Weitere Informationen zu `LINQDataSource` finden Sie unter [Übersicht über das LinqDataSource-Webserver Steuer](/previous-versions/aspnet/bb547113(v=vs.100))Element.</span><span class="sxs-lookup"><span data-stu-id="9eec6-107">For more information about `LINQDataSource`, see [LinqDataSource Web Server Control Overview](/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eec6-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9eec6-108">See also</span></span>

- [<span data-ttu-id="9eec6-109">N-Tier-und Remote Anwendungen mit LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9eec6-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](n-tier-and-remote-applications-with-linq-to-sql.md)
