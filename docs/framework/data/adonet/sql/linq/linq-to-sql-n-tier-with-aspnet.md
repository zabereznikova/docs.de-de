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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 477af694874ada4ae24fda0f1dbfac824a5aadbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-Schicht-LINQ to SQL mit ASP.NET
In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] -Anwendungen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]verwenden, setzen Sie das <xref:System.Web.UI.WebControls.LinqDataSource> -Webserversteuerelement ein. Das Steuerelement behandelt den größten Teil der Logik, die benötigt wird, um Abfragen gegen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]auszuführen, Daten an den Browser zu übergeben, abzurufen und zum Update der Datenbank an [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> zu senden. Sie konfigurieren das Steuerelement einfach im Markup, und das Steuerelement verarbeitet alle Datenübertragungen zwischen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] und dem Browser. Da das Steuerelement die Interaktionen mit der Präsentationsebene und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenebene behandelt, liegt der Hauptfokus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] -Anwendungen mit mehreren Ebenen auf dem Schreiben einer benutzerdefinierten Geschäftslogik.  
  
 Weitere Informationen zu `LINQDataSource`finden Sie unter [NIB: Übersicht über das LinqDataSource Webserver-Steuerelement](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>Siehe auch  
 [N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
