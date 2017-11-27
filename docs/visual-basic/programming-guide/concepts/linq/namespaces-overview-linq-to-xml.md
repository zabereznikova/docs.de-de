---
title: "Übersicht über Namespaces (LINQ to XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 082172720abd39634f7183367d4d7b8d53d2bb7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="namespaces-overview-linq-to-xml"></a>Übersicht über Namespaces (LINQ to XML)
Dieses Thema enthält eine Einführung in die Namespaces, die <xref:System.Xml.Linq.XName>-Klasse und die <xref:System.Xml.Linq.XNamespace>-Klasse.  
  
## <a name="xml-names"></a>XML-Namen  
 XML-Namen sind häufig die Ursache für komplexe Konstruktionen bei der XML-Programmierung. Ein XML-Name besteht aus einem XML-Namespace (auch als XML-Namespace-URI bezeichnet) und einem lokalen Namen. Ein XML-Namespace ähnelt einem Namespace in einem auf [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] basierenden Programm. Er ermöglicht die eindeutige Qualifizierung von Element- und Attributnamen. Auf diese Weise lassen sich Namenskonflikte zwischen verschiedenen Teilen eines XML-Dokuments besser vermeiden. Wenn Sie einen XML-Namespace deklariert haben, können Sie einen lokalen Namen auswählen, der nur innerhalb dieses Namespaces eindeutig sein muss.  
  
 Ein anderer Aspekt von XML-Namen sind die XML-*Namespacepräfixe*. XML-Präfixe sind die Hauptursache für die Komplexität von XML-Namen. Diese Präfixe ermöglichen es Ihnen, eine Kurzform eines XML-Namespace zu erstellen, wodurch das XML-Dokument kompakter und verständlicher wird. Die Bedeutung der XML-Präfixe ist jedoch kontextabhängig, was zur erhöhten Komplexität beiträgt. Das XML-Präfix `aw` kann z. B. in unterschiedlichen Teilen einer XML-Struktur unterschiedlichen XML-Namespaces zugeordnet sein.  
  
 Bei Verwendung [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit Visual Basic und XML-Literalen müssen Sie Namespacepräfixe verwenden, wenn mit Dokumenten in Namespaces arbeiten.  
  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] werden die XML-Namen in der <xref:System.Xml.Linq.XName>-Klasse dargestellt. XML-Namen treten in der gesamten [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-API häufig auf, und immer dann, wenn ein XML-Name erforderlich ist, treffen Sie auf einen <xref:System.Xml.Linq.XName>-Parameter. Sie arbeiten jedoch selten direkt mit einem <xref:System.Xml.Linq.XName>-Objekt. <xref:System.Xml.Linq.XName> enthält eine implizite Umwandlung aus einer Zeichenfolge.  
  
 Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNamespace> und <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
