---
title: Ungültige Datensatzlänge.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935251"
---
# <a name="bad-record-length"></a>Ungültige Datensatzlänge.
Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- Die Länge einer Datensatz-Variablen, die im angegebenen ein `FileGet`, `FileGetObject`, `FilePut` oder `FilePutObject` Anweisung unterscheidet sich von der entsprechenden angegebene Länge `FileOpen` Anweisung.  
  
- Die Variable in einem `FilePut` oder `FilePutObject` Anweisung oder eine Zeichenfolge variabler Länge enthält.  
  
- Die Variable in einem `FilePut` oder `FilePutObject` ist oder enthält ein `Variant` Typ.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass die Summe der Größen der Variablen im Datensatz den Typ der Variable definieren den benutzerdefinierten Typ fester Länge ist identisch, wie der Wert in der angegeben die `FileOpen` Anweisung `Len` Klausel.  
  
2. Wenn die Variable in einer `FilePut` oder `FilePutObject` Anweisung oder eine Zeichenfolge variabler Länge enthält, stellen Sie sicher, dass die Zeichenfolge variabler Länge, die kürzer als die Datensätze in angegebene Länge von mindestens 2 Zeichen der `Len` -Klausel der `FileOpen` -Anweisung.  
  
3. Wenn die Variable in einer `FilePut` oder `FilePutObject` ist oder enthält ein `Variant` sicherzustellen, dass die Zeichenfolge variabler Länge ist kürzer als die Datensatzlänge mindestens 4 Bytes der `Len` -Klausel der `FileOpen` Anweisung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
