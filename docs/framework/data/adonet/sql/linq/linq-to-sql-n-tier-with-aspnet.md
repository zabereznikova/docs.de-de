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
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-Schicht-LINQ to SQL mit ASP.NET

In ASP.NET-Anwendungen, die verwenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , verwenden Sie das- <xref:System.Web.UI.WebControls.LinqDataSource> Webserver Steuerelement. Das Steuerelement behandelt den größten Teil der Logik, die für die Abfrage erforderlich [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist, übergibt die Daten an den Browser, ruft Sie ab und sendet Sie an die, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> die dann die Datenbank aktualisiert. Sie konfigurieren das Steuerelement einfach im Markup, und das Steuerelement verarbeitet alle Datenübertragungen zwischen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Browser. Da das Steuerelement die Interaktionen mit der Präsentationsebene behandelt und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenebene behandelt, liegt der Hauptfokus in ASP.NET Anwendungen mit mehreren Ebenen auf dem Schreiben der benutzerdefinierten Geschäftslogik.  
  
 Weitere Informationen zu `LINQDataSource` finden Sie unter [Übersicht über das LinqDataSource-Webserver Steuer](/previous-versions/aspnet/bb547113(v=vs.100))Element.  
  
## <a name="see-also"></a>Weitere Informationen

- [N-Tier-und Remote Anwendungen mit LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
