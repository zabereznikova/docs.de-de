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
ms.openlocfilehash: 38740ed7ab7904feb2ca95eb70c916fbdbaef71e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654342"
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
 Erforderlich. Die Ressourcendatei mit der Assembly verknüpfen. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").  
  
 `identifier`  
 Dies ist optional. Der logische Name für die Ressource. Der Name, der verwendet wird, um die Ressource zu laden. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Datei öffentlich oder privat in das Assemblymanifest, z. B.: `-linkres:filename.res,myname.res,public`. Standardmäßig `filename` in der Assembly öffentlich ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `-linkresource` Option bettet die Ressourcendatei in der Ausgabedatei nicht; verwenden Sie die `-resource` Option aus, um dies zu tun.  
  
 Die `-linkresource` Option muss eine von der `-target` Optionen außer `-target:module`.  
  
 Wenn `filename` ist ein [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung können sie Zugriff mit Membern in der <xref:System.Resources> Namespace. (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit die Methoden, die mit `GetManifestResource` in die <xref:System.Reflection.Assembly> Klasse.  
  
 Der Dateiname kann ein beliebiges Dateiformat aufweisen. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Die Kurzform von `-linkresource` ist `-linkres`.  
  
> [!NOTE]
>  Die `-linkresource` Option ist nicht verfügbar in der Visual Studio-Entwicklungsumgebung, steht er nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `in.vb` und Links zu Ressourcendatei `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-Ziel (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
