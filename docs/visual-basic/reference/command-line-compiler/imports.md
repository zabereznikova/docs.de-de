---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 9e5adcce85c4ca4863d28784a7d7f61c441a06c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588443"
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
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
