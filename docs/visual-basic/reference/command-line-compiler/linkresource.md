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
ms.openlocfilehash: 0315645eccdc899ac9cf4d0be105297e1fa2a4c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335478"
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
 Erforderlich Die Ressourcen Datei, die mit der Assembly verknüpft werden soll. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.  
  
 `identifier`  
 Optional. Der logische Name der Ressource. Der Name, der zum Laden der Ressource verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Datei im Assemblymanifest öffentlich oder privat ist, z. b.: `-linkres:filename.res,myname.res,public`. Standardmäßig ist `filename` in der Assembly öffentlich.  
  
## <a name="remarks"></a>Hinweise  
 Mit der Option `-linkresource` wird die Ressourcen Datei nicht in die Ausgabedatei eingebettet. Verwenden Sie hierfür die Option `-resource`.  
  
 Die Option `-linkresource` erfordert eine der `-target` Optionen außer `-target:module`.  
  
 Wenn `filename` eine .NET Framework Ressourcen Datei ist, die beispielsweise von [Resgen. exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich. (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden, die mit `GetManifestResource` beginnen, in der <xref:System.Reflection.Assembly>-Klasse.  
  
 Der Dateiname kann ein beliebiges Dateiformat aufweisen. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Die Kurzform von `-linkresource` ist `-linkres`.  
  
> [!NOTE]
> Die `-linkresource`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `in.vb` und Links zu Ressourcen Datei `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
