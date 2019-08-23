---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924860"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Erstellt einen Link zu einer verwalteten Ressource.  
  
## <a name="syntax"></a>Syntax  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Erforderlich. Die Ressourcen Datei, die mit der Assembly verknüpft werden soll. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.  
  
 `identifier`  
 Optional. Der logische Name der Ressource. Der Name, der zum Laden der Ressource verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Datei im Assemblymanifest öffentlich oder privat ist, z. `-linkres:filename.res,myname.res,public`b.:. Standardmäßig `filename` ist in der Assembly öffentlich.  
  
## <a name="remarks"></a>Hinweise  
 Die `-linkresource` -Option bettet die Ressourcen Datei nicht in die Ausgabedatei ein. `-resource` verwenden Sie hierfür die-Option.  
  
 Die `-linkresource` Option erfordert eine `-target` der anderen Optionen als `-target:module`.  
  
 Wenn `filename` eine .NET Framework Ressourcen Datei ist, die beispielsweise von [Resgen. exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, kann <xref:System.Resources> mit Membern im-Namespace darauf zugegriffen werden. (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden `GetManifestResource` , die <xref:System.Reflection.Assembly> mit in der-Klasse beginnen.  
  
 Der Dateiname kann ein beliebiges Dateiformat aufweisen. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Die Kurzform von `-linkresource` ist `-linkres`.  
  
> [!NOTE]
> Die `-linkresource` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `in.vb` und verknüpft die Ressourcen Datei. `rf.resource`  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
