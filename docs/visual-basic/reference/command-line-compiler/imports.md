---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 330a5e6821c9c76f3503a35a5a5eabf24c686b42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
Importiert Namespaces aus der angegebenen Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`namespaceList`|Erforderlich. Durch Trennzeichen getrennte Liste der Namespaces importiert werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-imports` Option importiert alle Namespaces in die aktuelle Gruppe, der Quelldateien oder einer referenzierten Assembly definiert.  
  
 Die Elemente in einem Namespace mit angegebenen `-imports` stehen für alle Quellcodedateien in der Kompilierung. Verwenden Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf einen Namespace in einer einzelnen Quellcodedatei verwenden.  
  
|Festlegen/importiert Sie in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport** Schaltfläche.<br />4.  Klicken Sie auf die **Benutzerimport** Schaltfläche.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird kompiliert, wenn `/imports:system.globalization` angegeben ist. Ohne diese erfolgreicher Kompilierung erfordert entweder, dass ein `Imports System.Globalization` Anweisung am Anfang der Quellcodedatei eingeschlossen werden, oder die Eigenschaft als voll qualifiziert werden `System.Globalization.CultureInfo.CurrentCulture.Name`. 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
