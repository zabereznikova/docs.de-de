---
title: Sicherheit (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
ms.openlocfilehash: 03a5f562cb6dda8579d7cbdca56a60c6da34a576
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186925"
---
# <a name="security-linq-to-dataset"></a>Sicherheit (LINQ to DataSet)

In diesem Thema werden Sicherheitsprobleme in LINQ to DataSet erläutert.  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>Übergeben einer Abfrage an eine nicht vertrauenswürdige Komponente  

 Eine LINQ to DataSet Abfrage kann an einem bestimmten Punkt eines Programms formuliert und in einem anderen Programm ausgeführt werden. An dem Punkt, an dem die Abfrage formuliert wird, kann die Abfrage auf jedes beliebige Element verweisen, das an diesem Punkt sichtbar ist, z. B. private Member der Klasse, zu der die aufrufende Methode gehört, oder Symbole, die lokale Variablen/Argumente darstellen. Zum Zeitpunkt der Ausführung ist die Abfrage wirksam in der Lage, auf die Member zuzugreifen, auf die von der Abfrage bei der Formulierung verwiesen wurde, selbst wenn der aufrufende Code diese gar nicht einsehen kann. Der Code, der die Abfrage ausführt, besitzt insofern keine willkürlich hinzugefügte Sichtbarkeit, als dass er nicht wählen kann, worauf er zugreift. Er kann nur auf die Elemente zugreifen, auf die die Abfrage zugreift, und dies auch nur über die Abfrage selbst.  
  
 Das bedeutet, wenn ein Verweis auf eine Abfrage an ein anderes Stück Code übergeben wird, wird der Komponente, die die Abfrage empfängt, so vertraut, dass sie auf alle öffentlichen und privaten Member zugreifen darf, auf die die Abfrage verweist. Im Allgemeinen sollten LINQ to DataSet Abfragen nicht an nicht vertrauenswürdige Komponenten übermittelt werden, es sei denn, die Abfrage wurde sorgfältig erstellt, sodass keine Informationen verfügbar gemacht werden, die privat aufbewahrt werden sollten.  
  
## <a name="external-input"></a>Externe Eingabe  

 Anwendungen verwenden häufig externe Eingaben (eines Benutzers oder eines anderen externen Agenten) und führen entsprechend dieser Eingabe Aktionen aus.  Im Fall von LINQ to DataSet kann die Anwendung eine Abfrage auf eine bestimmte Weise auf der Grundlage externer Eingaben erstellen oder externe Eingaben in der Abfrage verwenden. LINQ to DataSet Abfragen akzeptieren Parameter überall, wo Literale akzeptiert werden. Anwendungsentwicklern wird empfohlen, parametrisierte Abfragen zu verwenden, anstatt Literale aus einem externen Agent direkt in die Abfrage einzuschleusen.  
  
 Jede direkt oder indirekt vom Benutzer oder einem externen Agenten abgeleitete Eingabe kann Inhalt besitzen, der die Syntax der Zielsprache nutzt, um nicht genehmigte Aktionen auszuführen. Dieses Verhalten wird als SQL Injection-Angriff bezeichnet. Diese Bezeichnung leitet sich aus einem Angriffsmuster ab, bei dem die Zielsprache Transact-SQL ist. Das Einschleusen von Benutzereingaben direkt in die Abfrage führt zum Löschen einer Datenbanktabelle oder zur Dienstverweigerung (Denial of Service) oder ändert auf andere Art und Weise die auszuführende Operation. Obwohl die Abfrage Komposition in LINQ to DataSet möglich ist, wird Sie über die Objektmodell-API ausgeführt. LINQ to DataSet Abfragen werden nicht mithilfe der Zeichen folgen Bearbeitung oder-Verkettung erstellt, wie Sie in Transact-SQL verwendet werden, und sind nicht anfällig für SQL Injection-Angriffe im herkömmlichen Sinne.  
  
## <a name="see-also"></a>Weitere Informationen

- [Programmierhandbuch](programming-guide-linq-to-dataset.md)
