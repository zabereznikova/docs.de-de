---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 075eeccc7d80943d2757a97b9a355bbea3ef9d4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663244"
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
Importiert Namespaces aus einer angegebenen Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`namespaceList`|Erforderlich. Durch Trennzeichen getrennte Liste von Namespaces importiert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-imports` Option importiert alle Namespaces, die in den aktuellen Satz von Quelldateien oder einer referenzierten Assembly definiert.  
  
 Die Elemente in einem Namespace, der mit angegebenen `-imports` stehen für alle Quellcodedateien in der Kompilierung. Verwenden Sie die [Imports-Anweisung (.NET-Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) um einen Namespace in einer einzelnen Quellcodedatei zu verwenden.  
  
|Festlegen/imports in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport hinzufügen** Schaltfläche.<br />4.  Klicken Sie auf die **Benutzerimport hinzufügen** Schaltfläche.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code wird kompiliert, wenn `/imports:system.globalization` angegeben ist. Ohne diese eine erfolgreiche Kompilierung erfordert entweder, dass ein `Imports System.Globalization` Anweisung eingeschlossen werden, am Anfang der Quellcodedatei, oder die Eigenschaft als voll qualifiziert werden `System.Globalization.CultureInfo.CurrentCulture.Name`.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
