---
title: -Langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 82a7114027451d1342e6dc0846799933ce44d968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-langversion-visual-basic"></a>-Langversion (Visual Basic)
Bewirkt, dass der Compiler nur Syntax akzeptiert, die in der angegebenen Version der Visual Basic-Sprache enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumente  
 `version`  
 Erforderlich. Die Sprachversion, die während der Kompilierung verwendet werden. Gültige Werte sind `9`, `9.0`, `10`, und `10.0`.  
  
## <a name="remarks"></a>Hinweise  
 Die `-langversion` Option gibt an, welche Syntax der Compiler akzeptiert. Wenn Sie angeben, dass die Sprachversion 9.0 ist, generiert der Compiler z. B. Fehler für die Syntax, die nur in Version 10.0 gültig und höher ist.  
  
 Sie können diese Option verwenden, wenn Sie Anwendungen, die auf verschiedenen Versionen von .NET Framework entwickeln. Wenn Sie .NET Framework 3.5 abzielen, konnte Sie z. B. diese Option verwenden, um sicherzustellen, dass Sie die Syntax von, Sprachversion 10.0 nicht verwenden.  
  
 Sie können festlegen, `-langversion` direkt nur mithilfe der Befehlszeile. Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `sample.vb` für Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Festlegen einer bestimmten .NET-Framework-Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
