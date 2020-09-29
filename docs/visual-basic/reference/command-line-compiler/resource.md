---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 726f3dd179aedb39b578c8580c9632182af2d5e0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085125"
---
# <a name="-resource-visual-basic"></a>-resource (Visual Basic)

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
|`filename`|Erforderlich. Der Name der Ressourcendatei, die in die Ausgabedatei eingebettet werden soll. Standardmäßig ist `filename` in der Assembly öffentlich. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.|  
|`identifier`|Dies ist optional. Der logische Name der Ressource, der zum Laden derselben verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie folgendermaßen angeben, ob die Ressource im Assemblymanifest öffentlich oder privat ist: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie `-linkresource`, um eine Ressource mit einer Assembly zu verknüpfen, ohne die Ressourcendatei zur Ausgabedatei hinzuzufügen.  
  
 Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise durch den Resource File Generator ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff über Member im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>. Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Die Kurzform von `-resource` ist `-res`.  
  
 Weitere Informationen zum Festlegen von `-resource` in der Visual Studio-IDE finden Sie unter [Verwalten von Anwendungsressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Beispiel  

 Mit dem folgenden Code werden `In.vb` kompiliert und die Ressourcendatei `Rf.resource` angefügt.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-win32resource](win32resource.md)
- [-linkresource (Visual Basic)](linkresource.md)
- [-target (Visual Basic)](target.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
