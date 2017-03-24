---
title: / linkresource (Visual Basic) | Microsoft-Dokumentation
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
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fafde6563340189108a879b82e7e880aca690b39
ms.lasthandoff: 03/13/2017

---
# <a name="linkresource-visual-basic"></a>/linkresource (Visual Basic)
Erstellt einen Link zu einer verwalteten Ressource.  
  
## <a name="syntax"></a>Syntax  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Erforderlich. Die Ressourcendatei, die mit der Assembly zu verknüpfen. Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").  
  
 `identifier`  
 Optional. Der logische Name der Ressource. Der Name, der zum Laden der Ressource verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Datei im Assemblymanifest öffentlich oder privat beispielsweise ist: `/linkres:filename.res,myname.res,public`. In der Standardeinstellung `filename` ist in der Assembly öffentlich.  
  
## <a name="remarks"></a>Hinweise  
 Die `/linkresource` Option bettet die Ressourcendatei in der Ausgabedatei nicht; verwenden Sie die `/resource` Option hierfür.  
  
 Die `/linkresource` -Option erfordert eine der der `/target` -Optionen `/target:module`.  
  
 Wenn `filename` ist ein [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei erstellt, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung darauf zugreifen können mit Mitgliedern der <xref:System.Resources>Namespace.</xref:System.Resources> (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.)</xref:System.Resources.ResourceManager> Zugriff auf alle anderen Ressourcen zur Laufzeit verwenden Sie die Methoden, die mit `GetManifestResource` in der <xref:System.Reflection.Assembly>Klasse.</xref:System.Reflection.Assembly>  
  
 Der Dateiname kann jedes Dateiformat sein. Beispielsweise empfiehlt es sich um eine systemeigene DLL Teil der Assembly, sodass im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly zugegriffen werden kann.  
  
 Die Kurzform der `/linkresource` ist `/linkres`.  
  
> [!NOTE]
>  Die `/linkresource` Option ist nicht verfügbar in der Visual Studio-Entwicklungsumgebung; es kann nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und Links zu Ressourcen-Datei `Rf.resource`.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/ Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
