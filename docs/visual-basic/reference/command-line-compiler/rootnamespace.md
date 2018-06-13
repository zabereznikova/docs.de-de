---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60cd661fe321c7bc3346f4d20e373240d6c35b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653159"
---
# <a name="-rootnamespace"></a>-rootnamespace
Gibt einen Namespace für alle Typdeklarationen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`namespace`|Der Name des Namespace, in dem alle Typdeklarationen für das aktuelle Projekt zu schließen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie die ausführbare Datei (Devenv.exe) von Visual Studio verwenden, um ein erstelltes Projekt kompilieren in der Visual Studio integrierten Entwicklungsumgebung verwenden `-rootnamespace` zum Angeben des Werts, der die <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Eigenschaft. Finden Sie unter [Devenv-Befehlszeilenschalter](/visualstudio/ide/reference/devenv-command-line-switches) für Weitere Informationen.  
  
 Verwenden Sie die common Language Runtime MSIL-Disassembler (`Ildasm.exe`) die Namespacenamen in der Ausgabedatei an.  
  
|In der integrierten Entwicklungsumgebung von Visual Studio - Rootnamespace festlegen|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert in der **Stamm-Namespace** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` eingeschlossen sind alle Deklarationen von Typen im Namespace `mynamespace`.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Ildasm.exe (IL-Disassembler)](https://msdn.microsoft.com/library/f7dy01k1)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
