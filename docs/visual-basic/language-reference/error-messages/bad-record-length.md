---
title: "Ungültige Datensatzlänge."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 747d62cb41ef841b4486e0c7108c37a86929683e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="bad-record-length"></a>Ungültige Datensatzlänge.
Zu den möglichen Ursachen für diesen Fehler gehören:  
  
-   Die Länge einer Datensatz-Variablen, die im angegebenen eine `FileGet`, `FileGetObject`, `FilePut` oder `FilePutObject` Anweisung unterscheidet sich von der entsprechenden angegebene Länge `FileOpen` Anweisung.  
  
-   Die Variable in einem `FilePut` oder `FilePutObject` -Anweisung ist, oder eine Zeichenfolge variabler Länge enthält.  
  
-   Die Variable in einem `FilePut` oder `FilePutObject` ist oder enthält ein `Variant` Typ.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Summe der Größen der Variablen in den benutzerdefinierten Typ definieren Datensatz den Typ der Variablen fester Länge entspricht dem Wert in der angegeben die `FileOpen` Anweisung `Len` Klausel.  
  
2.  Wenn die Variable in einer `FilePut` oder `FilePutObject` -Anweisung ist, oder eine Zeichenfolge variabler Länge enthält, stellen Sie sicher, dass die Zeichenfolge variabler Länge beträgt mindestens 2 Zeichen, die kürzer als die Länge des Datensatzes im angegebenen der `Len` -Klausel der `FileOpen` -Anweisung.  
  
3.  Wenn die Variable in einer `FilePut` oder `FilePutObject` ist oder enthält eine `Variant` stellen Sie sicher, dass die Zeichenfolge variabler Länge mindestens 4 Bytes kürzer als die Datensatzlänge der `Len` -Klausel der `FileOpen` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
