---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933050"
---
# <a name="-win32resource"></a>-win32resource
Fügt eine Win32-Ressourcendatei in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name der Ressourcendatei für die Ausgabedatei hinzufügen. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine Win32-Ressourcendatei mit dem Microsoft Windows Resource-Compiler (RC) erstellen.  
  
 Eine Win32-Ressource kann Versions- oder enthalten Bitmap (Symbol) Informationen ein, identifizieren Sie Ihre Anwendung in **Datei-Explorer**. Wenn Sie keinen angeben `-win32resource`, generiert der Compiler Versionsinformationen, die basierend auf die Version der Assembly. Die `-win32resource` und `-win32icon` Optionen schließen sich gegenseitig.  
  
 Finden Sie unter [- Linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) zum Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei.  
  
> [!NOTE]
>  Die `-win32resource` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und fügt eine Win32-Ressourcendatei `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
