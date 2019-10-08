---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002388"
---
# <a name="-baseaddress"></a>-baseaddress
Gibt beim Erstellen einer DLL eine Standardbasis Adresse an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`address`|Erforderlich. Die Basisadresse für die DLL. Diese Adresse muss als hexadezimal Zahl angegeben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Standard-Basisadresse für eine DLL wird vom-.NET Framework festgelegt.  
  
 Beachten Sie, dass das niedrigere Wort in dieser Adresse gerundet wird. Wenn Sie z. b. 0x11110001 angeben, wird es auf 0x11110000 gerundet.  
  
 Verwenden Sie die Option `–R` des Strong Naming Tool (Sn. exe), um den Signatur Vorgang für eine DLL abzuschließen.  
  
 Diese Option wird ignoriert, wenn das Ziel keine dll ist.  
  
|To Set-BaseAddress in der Visual Studio-IDE|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweitert**.<br />4.  Ändern Sie den Wert im Feld **DLL-Basisadresse:** . **Hinweis**:      Das Feld **DLL-Basisadresse:** ist schreibgeschützt, es sei denn, das Ziel ist eine DLL.|  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))
