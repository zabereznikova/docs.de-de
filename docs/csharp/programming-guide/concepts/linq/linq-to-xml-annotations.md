---
title: LINQ to XML-Anmerkungen3 | Microsoft-Dokumentation
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
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 13718f509eee46853020cfe1dd27ee85437d2e6d
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-annotations"></a>LINQ to XML-Anmerkungen
Mit Anmerkungen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie Objekte eines beliebigen Typs mit jeder beliebigen XML-Komponente in einer XML-Struktur verknüpfen.  
  
 Zum Hinzufügen einer Anmerkung zu einer XML-Komponente, z.B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute>, rufen Sie die Methode <xref:System.Xml.Linq.XObject.AddAnnotation%2A> auf. Anmerkungen werden nach Typ abgerufen.  
  
 Beachten Sie, dass Anmerkungen nicht Teil des XML-Infosets sind; sie werden nicht serialisiert oder deserialisiert.  
  
## <a name="methods"></a>Methoden  
 Beim Arbeiten mit Anmerkungen können Sie die folgenden Methoden verwenden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Fügt ein Objekt in die Anmerkungsliste eines <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> ein.|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Ruft das erste Anmerkungsobjekt des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject> ab.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Ruft eine Auflistung von Anmerkungen des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject> ab.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Entfernt die Anmerkungen eines angegebenen Typs von einem <xref:System.Xml.Linq.XObject>.|  
  
## <a name="see-also"></a>Siehe auch  
 [Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
