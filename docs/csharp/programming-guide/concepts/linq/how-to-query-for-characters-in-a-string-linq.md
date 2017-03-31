---
title: 'Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#) | Microsoft-Dokumentation'
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
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 537a46e918ad9613f01d0c8997bbdc8589c00dab
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)
Da die <xref:System.String>-Klasse die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, kann jede Zeichenfolge als Zeichensequenz abgefragt werden. Dies ist allerdings kein üblicher Einsatz von LINQ. Verwenden Sie für komplexe Musterabgleichsvorgänge die <xref:System.Text.RegularExpressions.Regex>-Klasse.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen. Beachten Sie, dass die Abfrage „wieder verwendet“ wird, nachdem sie zum ersten Mal ausgeführt wurde. Dies ist möglich, da die Abfrage selbst keine Ergebnisse speichert.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein Projekt, dass das .NET Framework Version 3.5 oder höher zum Ziel setzt, mit einem Verweis auf „System.Core.dll“ und `using`-Verzeichnissen für die Namespaces „System.Linq“ und „System.IO“.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)   
 [Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
