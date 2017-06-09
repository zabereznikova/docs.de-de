---
title: "Sicherheit (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Sicherheit (LINQ to DataSet)
In diesem Thema werden Fragen der Sicherheit in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] behandelt.  
  
## Übergeben einer Abfrage an eine nicht vertrauenswürdige Komponente  
 Es ist möglich, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen an einem Punkt eines Programms zu formulieren und sie dann an einem anderen Punkt auszuführen.  An dem Punkt, an dem die Abfrage formuliert wird, kann die Abfrage auf jedes beliebige Element verweisen, das an diesem Punkt sichtbar ist, z. B. private Member der Klasse, zu der die aufrufende Methode gehört, oder Symbole, die lokale Variablen\/Argumente darstellen.  Zum Zeitpunkt der Ausführung ist die Abfrage wirksam in der Lage, auf die Member zuzugreifen, auf die von der Abfrage bei der Formulierung verwiesen wurde, selbst wenn der aufrufende Code diese gar nicht einsehen kann.  Der Code, der die Abfrage ausführt, besitzt insofern keine willkürlich hinzugefügte Sichtbarkeit, als dass er nicht wählen kann, worauf er zugreift.  Er kann nur auf die Elemente zugreifen, auf die die Abfrage zugreift, und dies auch nur über die Abfrage selbst.  
  
 Das bedeutet, wenn ein Verweis auf eine Abfrage an ein anderes Stück Code übergeben wird, wird der Komponente, die die Abfrage empfängt, so vertraut, dass sie auf alle öffentlichen und privaten Member zugreifen darf, auf die die Abfrage verweist.  Im Allgemeinen gilt: [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen sollten nur dann an nicht vertrauenswürdige Komponenten übergeben werden, wenn die Abfrage sehr sorgfältig konstruiert wurde und damit keine Informationen verfügbar macht, die privat bleiben sollten.  
  
## Externe Eingabe  
 Anwendungen verwenden häufig externe Eingaben \(eines Benutzers oder eines anderen externen Agenten\) und führen entsprechend dieser Eingabe Aktionen aus.  Bei [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] kann die Anwendung anhand der externen Eingabe eine Abfrage auf bestimmte Weise konstruieren oder die externe Eingabe in der Abfrage verwenden. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen akzeptieren Parameter überall dort, wo Literale akzeptiert werden.  Anwendungsentwicklern wird empfohlen, parametrisierte Abfragen zu verwenden, anstatt Literale aus einem externen Agent direkt in die Abfrage einzuschleusen.  
  
 Jede direkt oder indirekt vom Benutzer oder einem externen Agenten abgeleitete Eingabe kann Inhalt besitzen, der die Syntax der Zielsprache nutzt, um nicht genehmigte Aktionen auszuführen.  Dieses Verhalten wird als SQL Injection\-Angriff bezeichnet. Diese Bezeichnung leitet sich aus einem Angriffsmuster ab, bei dem die Zielsprache Transact\-SQL ist.  Das Einschleusen von Benutzereingaben direkt in die Abfrage führt zum Löschen einer Datenbanktabelle oder zur Dienstverweigerung \(Denial of Service\) oder ändert auf andere Art und Weise die auszuführende Operation.  Das Erstellen von Abfragen ist in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] zwar möglich, wird aber über die Objektmodell\-API ausgeführt. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen werden nicht erstellt, indem Zeichenfolgen manipuliert oder verkettet werden, wie dies in Transact\-SQL der Fall ist, und sie sind nicht anfällig für SQL Injection\-Angriffe im herkömmlichen Sinne.  
  
## Siehe auch  
 [Informationen zum Programmieren](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)