---
title: / Resource (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b46800322fd03eb2578cc558cc1d9bb78550aa61
ms.lasthandoff: 03/13/2017

---
# <a name="resource-visual-basic"></a>/resource (Visual Basic)
Bettet eine verwaltete Ressource in eine Assembly ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich. Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden soll. In der Standardeinstellung `filename` ist in der Assembly öffentlich. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.|  
|`identifier`|Optional. Der logische Name der Ressource; der Name verwendet, um es zu laden. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Ressource im Assemblymanifest öffentlich oder privat wie mit den folgenden ist: `/res:``filename.res`,`myname.res`,`public`|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `/linkresource` auf eine Ressource mit einer Assembly zu verknüpfen, ohne dass die Ressourcendatei in der Ausgabedatei.  
  
 Wenn `filename` ist ein [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei erstellt, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung darauf zugreifen können mit Mitgliedern der <xref:System.Resources>Namespace (finden Sie unter <xref:System.Resources.ResourceManager>Weitere Informationen).</xref:System.Resources.ResourceManager> </xref:System.Resources> Zugriff auf alle anderen Ressourcen zur Laufzeit verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>  
  
 Die Kurzform der `/resource` ist `/res`.  
  
 Für Informationen zum Festlegen von `/resource` in der Visual Studio-IDE finden Sie unter [Verwalten von Ressourcen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [/ linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
