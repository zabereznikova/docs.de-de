---
title: LINQ to ADO.NET (Portalseite) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f1c70901d5c2e5f5d709ec3c10821fbd1aa9dee6
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Portalseite)
Mit [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] können Sie in [!INCLUDE[vstecado](~/includes/vstecado_md.md)] mithilfe des Programmiermodells [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] jedes aufzählbare Objekt abfragen.  
  
> [!NOTE]
>  Die [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)]-Dokumentation befindet sich im Abschnitt „ADO.NET“ des .NET Framework SDK: [LINQ und ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Es gibt drei separate ADO.NET-[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]-Technologien: [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] und [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]. [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)] stellt umfangreichere, optimierte Abfragen gegenüber dem <xref:System.Data.DataSet> bereit. Mit [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] können Sie direkt [!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)]-Datenbankschemas abfragen, und mit [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] können Sie [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)] abfragen.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> ist eine der am häufigsten verwendeten Komponenten in [!INCLUDE[vstecado](~/includes/vstecado_md.md)] und ein Schlüsselelement des getrennten Programmiermodells, auf dem [!INCLUDE[vstecado](~/includes/vstecado_md.md)] aufgebaut ist. Jedoch verfügt das <xref:System.Data.DataSet> trotz seiner häufigen Verwendung über eingeschränkte Abfragefunktionen.  
  
 Mit [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)] können Sie umfangreichere Abfragefunktionen in <xref:System.Data.DataSet> integrieren, indem Sie die gleiche Abfragefunktionalität verwenden, die für viele andere Datenquellen verfügbar ist.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] stellt eine Laufzeitinfrastruktur zum Verwalten relationaler Daten als Objekte bereit. In [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist. Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] die Ergebnisse zurück in Objekte, die Sie bearbeiten können.  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] bietet Unterstützung für gespeicherte Prozeduren und benutzerdefinierte Funktionen in der Datenbank sowie für die Vererbung im Objektmodell.  
  
 Weitere Informationen finden Sie unter [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Durch das [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)] werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Dies wird als [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] bezeichnet. Weitere Informationen Sie unter [LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d).  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)   
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
