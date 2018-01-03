---
title: Sicherheit (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2f67ad1947d421a5221a34ad8392242e4d18039f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-linq-to-dataset"></a>Sicherheit (LINQ to DataSet)
In diesem Thema werden Fragen der Sicherheit in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] behandelt.  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>Übergeben einer Abfrage an eine nicht vertrauenswürdige Komponente  
 Ein [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage formuliert an einem Punkt eines Programms und in einen anderen PC ausgeführt werden kann. An dem Punkt, an dem die Abfrage formuliert wird, kann die Abfrage auf jedes beliebige Element verweisen, das an diesem Punkt sichtbar ist, z. B. private Member der Klasse, zu der die aufrufende Methode gehört, oder Symbole, die lokale Variablen/Argumente darstellen. Zum Zeitpunkt der Ausführung ist die Abfrage wirksam in der Lage, auf die Member zuzugreifen, auf die von der Abfrage bei der Formulierung verwiesen wurde, selbst wenn der aufrufende Code diese gar nicht einsehen kann. Der Code, der die Abfrage ausführt, besitzt insofern keine willkürlich hinzugefügte Sichtbarkeit, als dass er nicht wählen kann, worauf er zugreift. Er kann nur auf die Elemente zugreifen, auf die die Abfrage zugreift, und dies auch nur über die Abfrage selbst.  
  
 Das bedeutet, wenn ein Verweis auf eine Abfrage an ein anderes Stück Code übergeben wird, wird der Komponente, die die Abfrage empfängt, so vertraut, dass sie auf alle öffentlichen und privaten Member zugreifen darf, auf die die Abfrage verweist. Im allgemeinen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen darf nicht für nicht vertrauenswürdige Komponenten übergeben werden, es sei denn, die Abfrage sehr sorgfältig konstruiert wurde, sodass keine Informationen verfügbar macht, die privat bleiben sollten.  
  
## <a name="external-input"></a>Externe Eingabe  
 Anwendungen verwenden häufig externe Eingaben (eines Benutzers oder eines anderen externen Agenten) und führen entsprechend dieser Eingabe Aktionen aus.  Im Fall von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], eine Abfrage in einer bestimmten Art, basierend auf externe Eingabe oder die externe Eingabe in der Abfrage möglicherweise durch die Anwendung erstellt. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen akzeptieren Parameter an allen Stellen, an denen Literale akzeptiert werden. Anwendungsentwicklern wird empfohlen, parametrisierte Abfragen zu verwenden, anstatt Literale aus einem externen Agent direkt in die Abfrage einzuschleusen.  
  
 Jede direkt oder indirekt vom Benutzer oder einem externen Agenten abgeleitete Eingabe kann Inhalt besitzen, der die Syntax der Zielsprache nutzt, um nicht genehmigte Aktionen auszuführen. Dieses Verhalten wird als SQL Injection-Angriff bezeichnet. Diese Bezeichnung leitet sich aus einem Angriffsmuster ab, bei dem die Zielsprache Transact-SQL ist. Das Einschleusen von Benutzereingaben direkt in die Abfrage führt zum Löschen einer Datenbanktabelle oder zur Dienstverweigerung (Denial of Service) oder ändert auf andere Art und Weise die auszuführende Operation. Obwohl das Zusammensetzen von Abfragen in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] möglich ist, wird dieser Vorgang über die Objektmodell-API ausgeführt. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen werden nicht mit Zeichenfolgen manipuliert oder verkettet, wie sie in Transact-SQL sind und sind nicht anfällig für SQL Injection-Angriffe im herkömmlichen Sinne erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
