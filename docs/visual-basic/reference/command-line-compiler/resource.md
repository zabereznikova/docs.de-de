---
title: -Ressource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab5593455546e65bdd760d9e60532031dc1f12a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654435"
---
# <a name="-resource-visual-basic"></a>-Ressource (Visual Basic)
Bettet eine verwaltete Ressource in eine Assembly ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich. Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden sollen. Standardmäßig `filename` in der Assembly öffentlich ist. Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.|  
|`identifier`|Dies ist optional. Der logische Name für die Ressource; der Name verwendet, um es zu laden. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Ressource öffentlich oder privat in das Assemblymanifest, wie mit den folgenden ist: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `-linkresource` auf eine Ressource mit einer Assembly verknüpft werden, ohne die Ressourcendatei in die Ausgabedatei platziert.  
  
 Wenn `filename` ist ein [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung können sie Zugriff mit Membern in der <xref:System.Resources> Namespace (siehe <xref:System.Resources.ResourceManager> für Weitere Informationen). Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Die Kurzform von `-resource` ist `-res`.  
  
 Informationen zum Festlegen von `-resource` in der Visual Studio-IDE finden Sie unter [verwalten Anwendung Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [-Linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [-Ziel (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
