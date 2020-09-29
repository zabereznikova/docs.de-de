---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 8c4f753f94aedaf0a4f997a3f9b99fb3f417abf8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065683"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)

Erstellt einen Link zu einer verwalteten Ressource.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

oder  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  

 `filename`  
 Erforderlich. Die Ressourcendatei, die mit der Assembly verknüpft werden soll. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.  
  
 `identifier`  
 Dies ist optional. Der logische Name der Ressource. Der Name, der zum Laden der Ressource verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie folgendermaßen angeben, ob die Datei im Assemblymanifest öffentlich oder privat ist: `-linkres:filename.res,myname.res,public`. Standardmäßig ist `filename` in der Assembly öffentlich.  
  
## <a name="remarks"></a>Hinweise  

 Mit der Option `-linkresource` wird die Ressourcendatei nicht in die Ausgabedatei eingebettet. Verwenden Sie hierfür die Option `-resource`.  
  
 Die Option `-linkresource` erfordert eine der `-target`-Optionen (außer `-target:module`).  
  
 Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise durch den Resource File Generator ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>. Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden der Klasse <xref:System.Reflection.Assembly>, die mit `GetManifestResource` beginnen.  
  
 Der Dateiname kann ein beliebiges Dateiformat aufweisen. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Die Kurzform von `-linkresource` ist `-linkres`.  
  
> [!NOTE]
> Die Option `-linkresource` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  

 Mit dem folgenden Code werden `in.vb` kompiliert und eine Verknüpfung mit der Ressourcendatei `rf.resource` generiert.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-target (Visual Basic)](target.md)
- [-resource (Visual Basic)](resource.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
