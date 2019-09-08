---
title: N-Schicht-LINQ to SQL mit ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 1770d84053b57e05d1a4e41919a3eb4122dc73a3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793033"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-Schicht-LINQ to SQL mit ASP.NET
In ASP.NET-Anwendungen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]die verwenden, verwenden <xref:System.Web.UI.WebControls.LinqDataSource> Sie das-Webserver Steuerelement. Das Steuerelement behandelt den größten Teil der Logik, die benötigt wird, um Abfragen gegen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]auszuführen, Daten an den Browser zu übergeben, abzurufen und zum Update der Datenbank an [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> zu senden. Sie konfigurieren das Steuerelement einfach im Markup, und das Steuerelement verarbeitet alle Datenübertragungen zwischen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Browser. Da das Steuerelement die Interaktionen mit der Präsentationsebene behandelt und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenebene behandelt, liegt der Hauptfokus in ASP.NET Anwendungen mit mehreren Ebenen auf dem Schreiben der benutzerdefinierten Geschäftslogik.  
  
 Weitere Informationen zu finden `LINQDataSource`Sie unter [Übersicht über das LinqDataSource-Webserver Steuer](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))Element.  
  
## <a name="see-also"></a>Siehe auch

- [N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
