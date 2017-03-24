---
title: "Übersicht über Namespaces (LINQ to XML) | Microsoft-Dokumentation"
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
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cec2efd31c96af17ad717abaa8f4359210e99a78
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-overview-linq-to-xml"></a>Übersicht über Namespaces (LINQ to XML)
In diesem Thema werden die Namespaces, die <xref:System.Xml.Linq.XName>Klasse, und die <xref:System.Xml.Linq.XNamespace>Klasse.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName>  
  
## <a name="xml-names"></a>XML-Namen  
 XML-Namen sind häufig die Ursache für komplexe Konstruktionen bei der XML-Programmierung. Ein XML-Name besteht aus einem XML-Namespace (auch als XML-Namespace-URI bezeichnet) und einem lokalen Namen. Ein XML-Namespace ähnelt einem Namespace in einem auf [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] basierenden Programm. Er ermöglicht die eindeutige Qualifizierung von Element- und Attributnamen. Auf diese Weise lassen sich Namenskonflikte zwischen verschiedenen Teilen eines XML-Dokuments besser vermeiden. Wenn Sie einen XML-Namespace deklariert haben, können Sie einen lokalen Namen auswählen, der nur innerhalb dieses Namespaces eindeutig sein muss.  
  
 Ein anderer Aspekt von XML-Namen sind XML *Namespacepräfixe*. XML-Präfixe sind die Hauptursache für die Komplexität von XML-Namen. Diese Präfixe ermöglichen es Ihnen, eine Kurzform eines XML-Namespace zu erstellen, wodurch das XML-Dokument kompakter und verständlicher wird. Die Bedeutung der XML-Präfixe ist jedoch kontextabhängig, was zur erhöhten Komplexität beiträgt. Das XML-Präfix `aw` kann z. B. in unterschiedlichen Teilen einer XML-Struktur unterschiedlichen XML-Namespaces zugeordnet sein.  
  
 Verwendung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] mit Visual Basic und XML-Literalen müssen Sie Namespacepräfixe verwenden, wenn Sie mit Dokumenten in Namespaces arbeiten.  
  
 In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], die Klasse, die XML-Namen ist <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> XML-Namen treten häufig in der gesamten der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -API, und wo ein XML-Name erforderlich ist, wird Ihnen ein <xref:System.Xml.Linq.XName>Parameter.</xref:System.Xml.Linq.XName> Arbeiten Sie jedoch nur selten direkt mit einer <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> <xref:System.Xml.Linq.XName>enthält eine implizite Konvertierung aus einer Zeichenfolge.</xref:System.Xml.Linq.XName>  
  
 Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNamespace>und <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace>  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
