---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: cc9fc222843bdfe8e49d2d291dc36ff3e0c63fc2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408594"
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
Die Option -imports importiert Namespaces aus einer angegebenen Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`namespaceList`|Erforderlich. Liste der zu importierenden Namespaces mit Kommas als Trennzeichen|  
  
## <a name="remarks"></a>Hinweise  
 Mit der Option `-imports` werden alle Namespaces importiert, die in den aktuellen Quelldateien oder einer beliebigen Assembly, auf die verwiesen wird, definiert sind.  
  
 Die Member eines Namespace, der mit `-imports` angegeben wird, sind für alle Quellcodedateien in der Kompilierung verfügbar. Verwenden Sie die [Imports-Anweisung (.NET-Namespace und -Typ)](../../language-reference/statements/imports-statement-net-namespace-and-type.md), um einen Namespace in einer einzelnen Quellcodedatei zu verwenden.  
  
|So legen Sie -imports in der integrierten Visual Studio-Entwicklungsumgebung fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Geben Sie den Namespacenamen in das Feld neben der Schaltfläche **Benutzerimport hinzufügen** ein.<br />4.  Klicken Sie auf die Schaltfläche **Benutzerimport hinzufügen**.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code wird kompiliert, wenn `-imports:system.globalization` angegeben wird. Ohne diese Angabe ist für eine erfolgreiche Kompilierung entweder erforderlich, dass eine `Imports System.Globalization`-Anweisung am Anfang der Quellcodedatei enthalten ist oder dass die Eigenschaft als `System.Globalization.CultureInfo.CurrentCulture.Name` vollqualifiziert ist.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Verweise und die Imports-Anweisung](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
