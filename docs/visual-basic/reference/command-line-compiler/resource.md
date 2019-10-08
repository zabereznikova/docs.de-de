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
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005190"
---
# <a name="-resource-visual-basic"></a>-Ressource (Visual Basic)
Bettet eine verwaltete Ressource in eine Assembly ein.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

oder  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich. Der Name der Ressourcen Datei, die in die Ausgabedatei eingebettet werden soll. Standardmäßig ist `filename` in der Assembly öffentlich. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.|  
|`identifier`|Optional. Der logische Name der Ressource. der Name, der verwendet wird, um ihn zu laden. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Ressource im Assemblymanifest öffentlich oder privat ist, wie im folgenden angegeben: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `-linkresource`, um eine Ressource mit einer Assembly zu verknüpfen, ohne die Ressourcen Datei in der Ausgabedatei zu platzieren.  
  
 Wenn `filename` eine .NET Framework Ressourcen Datei ist, die beispielsweise von [Resgen. exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>). Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Die Kurzform von `-resource` ist `-res`.  
  
 Informationen dazu, wie Sie `-resource` in der Visual Studio-IDE festlegen, finden Sie unter [Verwalten von Anwendungs Ressourcen (.net)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und die Ressourcen Datei `Rf.resource` angefügt.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
