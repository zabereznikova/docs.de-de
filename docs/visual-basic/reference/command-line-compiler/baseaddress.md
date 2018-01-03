---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1ad39acdec92667fbb0848a1c64c567b504dcb67
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="baseaddress"></a>/baseaddress
Gibt eine Standard-Basisadresse an, beim Erstellen einer DLL.  
  
## <a name="syntax"></a>Syntax  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`address`|Erforderlich. Die Basisadresse für die DLL. Diese Adresse muss als eine hexadezimale Zahl angegeben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Standard-Basisadresse für eine DLL wird durch Festlegen der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird. Wenn Sie 0 x 11110001 angeben, wird es beispielsweise auf 0 x 11110000 gerundet.  
  
 Zum Ausführen des signierungsprozesses für eine DLL verwenden die `–R` Möglichkeit, das Strong Name-Tool (Sn.exe).  
  
 Diese Option wird ignoriert, wenn das Ziel keine DLL ist.  
  
|/ Baseaddress in der Visual Studio-IDE festlegen|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **erweiterte**.<br />4.  Ändern Sie den Wert in der **Basisadresse der DLL:** Feld. **Hinweis:** der **Basisadresse der DLL:** Feld ist schreibgeschützt, es sei denn, das Ziel eine DLL ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sn.exe (Strong Name-Tool)] [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))
