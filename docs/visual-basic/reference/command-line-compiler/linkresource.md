---
title: -Linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 97e0ccd46f413cc05b659731436bb141ee178419
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45596624"
---
# <a name="-linkresource-visual-basic"></a>-Linkresource (Visual Basic)
Erstellt einen Link zu einer verwalteten Ressource.  
  
## <a name="syntax"></a>Syntax  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Erforderlich. Die Ressourcendatei der Assembly zu verknüpfen. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").  
  
 `identifier`  
 Dies ist optional. Der logische Name für die Ressource. Der Name, die zum Laden der Ressource verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Datei öffentlich oder privat ist, in das Assemblymanifest, z. B.: `-linkres:filename.res,myname.res,public`. In der Standardeinstellung `filename` in der Assembly öffentlich ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `-linkresource` Option bettet die Ressourcendatei in die Ausgabedatei nicht; verwenden Sie die `-resource` Option aus, um dies zu tun.  
  
 Die `-linkresource` -Option erfordert eine von der `-target` Optionen, die nicht `-target:module`.  
  
 Wenn `filename` ist eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der <xref:System.Resources> Namespace. (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit die Methoden, die mit beginnen `GetManifestResource` in die <xref:System.Reflection.Assembly> Klasse.  
  
 Der Dateiname kann jedes Dateiformat sein. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Die Kurzform von `-linkresource` ist `-linkres`.  
  
> [!NOTE]
>  Die `-linkresource` Option ist nicht verfügbar ist, aus der Visual Studio-Entwicklungsumgebung, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `in.vb` und Links zu Ressourcen `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)  
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
