---
title: /win32resource
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d839b1100b1ae76fbd4653ebc60c79db11b77685
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="win32resource"></a>/win32resource
Fügt eine Win32-Ressourcendatei in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name der Ressourcendatei für die Ausgabedatei hinzufügen. Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine Win32-Ressourcendatei mit der Microsoft Windows Resource-Compiler (RC) erstellen.  
  
 Eine Win32-Ressource kann Versions- oder enthalten Bitmap (Symbol) Informationen bieten, identifizieren Sie Ihre Anwendung in **Datei-Explorer**. Wenn Sie keinen angeben `/win32resource`, generiert der Compiler Versionsinformationen basierend auf der Assemblyversion. Die `/win32resource` und `/win32icon` Optionen schließen sich gegenseitig.  
  
 Finden Sie unter [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei.  
  
> [!NOTE]
>  Die `/win32resource` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und fügt eine Win32-Ressourcendatei `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
