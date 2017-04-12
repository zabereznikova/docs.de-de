---
title: LINQ to ADO.NET (Portal Seite) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5c71b304dbff960320b1a9f46e38259705b8dadc
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Portalseite)
[!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)]ermöglicht Ihnen, beliebige aufzählbare Objekte in der Abfrage [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] mithilfe der [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Programmiermodell.  
  
> [!NOTE]
>  Die [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] Dokumentation befindet sich im ADO.NET-Abschnitt im .NET Framework SDK: [LINQ und ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Es gibt drei separate ADO.NET-[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]-Technologien: [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] und [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]. [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]bietet umfangreichere, optimierte Abfragen der <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] können Sie direkt Abfragen [!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)] -Datenbankschemas, und [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] können Sie Abfragen eine [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)].</xref:System.Data.DataSet>  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 Die <xref:System.Data.DataSet>ist eine der am häufigsten verwendeten Komponenten in [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], und ist ein wichtiges Element des getrennten Programmiermodells modellieren, [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] basiert.</xref:System.Data.DataSet> Trotz dieser Abfragefunktionalität der <xref:System.Data.DataSet>beschränkte Abfragefunktionen.</xref:System.Data.DataSet>  
  
 [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]können Sie umfangreichere Abfragefunktionen in <xref:System.Data.DataSet>durch die gleiche Funktionalität verwenden, die für viele andere Datenquellen verfügbar ist.</xref:System.Data.DataSet>  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]Stellt eine Laufzeitinfrastruktur zum Verwalten relationaler Daten als Objekte bereit. In [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], ein in der Programmiersprache des Entwicklers ausgedrücktes Objektmodell das Datenmodell einer relationalen Datenbank zugeordnet ist. Beim Ausführen der Anwendung [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] übersetzt sprachintegrierte Abfragen im Objektmodell in SQL und sendet diese zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] übersetzt diese zurück in Objekte, die Sie bearbeiten können.  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]bietet Unterstützung für gespeicherte Prozeduren und benutzerdefinierte Funktionen in der Datenbank und für die Vererbung im Objektmodell.  
  
 Weitere Informationen finden Sie unter [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Durch das [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)] werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Dies wird als [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] bezeichnet. Finden Sie unter [LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d) Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)   
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
