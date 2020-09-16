---
title: N-Schicht-LINQ to SQL mit ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 1af7f0d78f16e25c1ae7bf563c6abfb3b77f6183
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559225"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-Schicht-LINQ to SQL mit ASP.NET
In ASP.NET-Anwendungen, die verwenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , verwenden Sie das- <xref:System.Web.UI.WebControls.LinqDataSource> Webserver Steuerelement. Das Steuerelement behandelt den größten Teil der Logik, die für die Abfrage erforderlich [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist, übergibt die Daten an den Browser, ruft Sie ab und sendet Sie an die, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> die dann die Datenbank aktualisiert. Sie konfigurieren das Steuerelement einfach im Markup, und das Steuerelement verarbeitet alle Datenübertragungen zwischen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Browser. Da das Steuerelement die Interaktionen mit der Präsentationsebene behandelt und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenebene behandelt, liegt der Hauptfokus in ASP.NET Anwendungen mit mehreren Ebenen auf dem Schreiben der benutzerdefinierten Geschäftslogik.  
  
 Weitere Informationen zu `LINQDataSource` finden Sie unter [Übersicht über das LinqDataSource-Webserver Steuer](/previous-versions/aspnet/bb547113(v=vs.100))Element.  
  
## <a name="see-also"></a>Siehe auch

- [N-Tier-und Remote Anwendungen mit LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
