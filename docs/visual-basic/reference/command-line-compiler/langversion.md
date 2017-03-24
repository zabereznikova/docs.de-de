---
title: / langversion (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9970df0c9babc368210169fae0490b423d77f40d
ms.lasthandoff: 03/13/2017

---
# <a name="langversion-visual-basic"></a>/langversion (Visual Basic)
Bewirkt, dass den Compiler nur Syntax akzeptiert, die in der angegebenen Version der Visual Basic-Sprache enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a>Argumente  
 `version`  
 Erforderlich. Die Sprachversion, die während der Kompilierung verwendet werden. Gültige Werte sind `9`, `9.0`, `10`, und `10.0`.  
  
## <a name="remarks"></a>Hinweise  
 Die `/langversion` Option gibt an, welche Syntax der Compiler akzeptiert. Wenn Sie angeben, dass die Version 9.0 ist, generiert der Compiler z. B. Fehler für Syntax, die nur in Version 10.0 oder höher ist.  
  
 Wenn Sie Anwendungen, die verschiedene Versionen von .NET Framework abzielen entwickeln, können Sie diese Option verwenden. Wenn Sie .NET Framework 3.5 abzielen, konnte Sie z. B. diese Option verwenden, um sicherzustellen, dass Sie keine Syntax aus der Sprachversion 10.0 verwenden.  
  
 Sie können festlegen, `/langversion` direkt nur in der Befehlszeile. Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `sample.vb` für Visual Basic 9.0.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Festlegen einer bestimmten .NET-Framework-Zielversion](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
